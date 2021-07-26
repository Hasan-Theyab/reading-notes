# DIVING IN

Persistent local storage is one of the areas where native client applications have held an advantage over web applications. For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files, or some other place according to platform convention. If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.

Historically, web applications have had none of these luxuries. Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over

- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)

- Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful


What we really want is:

- a lot of storage space

- on the client

- that persists beyond a page refresh

- and isn’t transmitted to the server

Before HTML5, all attempts to achieve this were ultimately unsatisfactory in different ways.


# A BRIEF HISTORY OF LOCAL STORAGE HACKS BEFORE HTML5

In the beginning, there was only Internet Explorer. Or at least, that’s what Microsoft wanted the world to think. To that end, as part of the **First Great Browser Wars,** Microsoft invented a great many things and included them in their browser-to-end-all-browser-wars, Internet Explorer. One of these things was called **DHTML Behaviors,** and one of these behaviors was called **userData.**



**userData** allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure. (Trusted domains, such as intranet sites, can store 10 times that amount. And hey, **640 KB ought to be enough for anybody.)** IE does not present any form of permissions dialog, and there is no allowance for increasing the amount of storage available.


In 2002, Adobe introduced a feature in Flash 6 that gained the unfortunate and misleading name of “Flash cookies.” Within the Flash environment, the feature is properly known as **Local Shared Objects.** Briefly, it allows Flash objects to store up to 100 KB of data per domain. Brad Neuberg developed an early prototype of a Flash-to-JavaScript bridge called **AMASS** (AJAX Massive Storage System), but it was limited by some of Flash’s design quirks. By 2006, with the advent of **ExternalInterface** in Flash 8, accessing LSOs from JavaScript became an order of magnitude easier and faster. Brad rewrote AMASS and integrated it into the popular **Dojo Toolkit** under the moniker **dojox.storage.** Flash gives each domain 100 KB of storage “for free.” Beyond that, it prompts the user for each order of magnitude increase in data storage (1 Mb, 10 Mb, and so on).


In 2007, Google launched **Gears,** an open source browser plugin aimed at providing additional capabilities in browsers. (We’ve previously discussed Gears in the context of **providing a geolocation API in Internet Explorer.)** Gears provides an **API to an embedded SQL database** based on **SQLite.** After obtaining permission from the user once, Gears can store unlimited amounts of data per domain in SQL database tables.


In the meantime, Brad Neuberg and others continued to hack away on **dojox.storage** to provide a unified interface to all these different plugins and APIs. By 2009, **dojox.storage** could auto-detect (and provide a unified interface on top of) Adobe Flash, Gears, Adobe AIR, and an early prototype of HTML5 storage that was only implemented in older versions of Firefox.


As you survey these solutions, a pattern emerges: all of them are either specific to a single browser, or reliant on a third-party plugin. Despite heroic efforts to paper over the differences **(in dojox.storage),** they all expose radically different interfaces, have different storage limitations, and present different user experiences. So this is the problem that HTML5 set out to solve: to provide a standardized API, implemented natively and consistently in multiple browsers, without having to rely on third-party plugins.


# INTRODUCING HTML5 STORAGE

What I will refer to as “HTML5 Storage” is a specification named **Web Storage,** which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons. Certain browser vendors also refer to it as “Local Storage” or “DOM Storage.” The naming situation is made even more complicated by some related, similarly-named, emerging standards that I’ll discuss later in this chapter.


So what is HTML5 Storage? Simply put, it’s a way for web pages to store named key/value pairs locally, within the client web browser. Like cookies, this data persists even after you navigate away from the web site, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server (unless you go out of your way to send it manually). Unlike all **previous attempts** at providing persistent local storage, it is implemented natively in web browsers, so it is available even when third-party browser plugins are not.


Which browsers? Well, the latest version of pretty much every browser supports HTML5 Storage… even Internet Explorer!.


From your JavaScript code, you’ll access HTML5 Storage through the **localStorage** object on the global **window** object. Before you can use it, you should **detect whether the browser supports it.**


 ### check for HTML5 Storage:

 function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}

Instead of writing this function yourself, you can use Modernizr to detect support for HTML5 Storage.


if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}


# USING HTML5 STORAGE

HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like **parseInt()** or **parseFloat()** to coerce your retrieved data into the expected JavaScript datatype.


**interface Storage {**
  **getter any getItem(in DOMString key);**
  **setter creator void setItem(in DOMString key, in any data);**
**};**


Calling **setItem()** with a named key that already exists will silently overwrite the previous value. Calling **getItem()** with a non-existent key will return **null** rather than throw an exception.

Like other JavaScript objects, you can treat the **localStorage** object as an associative array. Instead of using the **getItem()** and **setItem()** methods, you can simply use square brackets. For example, this snippet of code:

**var foo = localStorage.getItem("bar");**
**// ...**
**localStorage.setItem("bar", foo);**


…could be rewritten to use square bracket syntax instead:

**var foo = localStorage["bar"];**
**// ...**
**localStorage["bar"] = foo;**


There are also methods for removing the value for a given named key, and clearing the entire storage area (that is, deleting all the keys and values at once).

**interface Storage {**
  **deleter void removeItem(in DOMString key);**
  **void clear();**
**};**


Calling **removeItem()** with a non-existent key will do nothing.


Finally, there is a property to get the total number of values in the storage area, and to iterate through all of the keys by index (to get the name of each key).


**interface Storage {**
  **readonly attribute unsigned long length;**
  **getter DOMString key(in unsigned long index);**
**};**


If you call key() with an index that is not between 0–(**length-1**), the function will return **null.**


### TRACKING CHANGES TO THE HTML5 STORAGE AREA

If you want to keep track programmatically of when the storage area changes, you can trap the **storage** event. The **storage event** is fired on the window object whenever **setItem(),** **removeItem(),** or **clear()** is called *and actually changes something.* For example, if you set an item to its existing value or call **clear()** when there are no named keys, the **storage** event will not fire, because nothing actually changed in the storage area.


The **storage** event is supported everywhere the **localStorage** object is supported, which includes Internet Explorer 8. IE 8 does not support the W3C standard **addEventListener** (although that will finally be added in IE 9). Therefore, to hook the **storage** event, you’ll need to check which event mechanism the browser supports. (If you’ve done this before with other events, you can skip to the end of this section. Trapping the storage event works the same as every other event you’ve ever trapped. If you prefer to use jQuery or some other JavaScript library to register your event handlers, you can do that with the storage event, too.)


if (window.addEventListener) {
  window.addEventListener("storage", handle_storage, false);
} else {
  window.attachEvent("onstorage", handle_storage);
};


The **handle_storage** callback function will be called with a **StorageEvent** object, except in Internet Explorer where the event object is stored in window.event.


function handle_storage(e) {
  if (!e) { e = window.event; }
}


At this point, the variable e will be a StorageEvent object,


### LIMITATIONS IN CURRENT BROWSERS

In talking about **the history of local storage hacks** using third-party plugins, I made a point of mentioning the limitations of each technique, such as storage limits. I just realized that I haven’t mentioned anything about the limitations of the now-standardized HTML5 Storage. I’ll give you the answers first, then explain them. The answers, in order of importance, are “5 megabytes,” “**QUOTA_EXCEEDED_ERR,**” and “no.”



“5 megabytes” is how much storage space each **origin** gets by default. This is surprisingly consistent across browsers, although it is phrased as no more than a suggestion in the HTML5 Storage specification. One thing to keep in mind is that you’re storing strings, not data in its original format. If you’re storing a lot of integers or floats, the difference in representation can really add up. Each digit in that float is being stored as a character, not in the usual representation of a floating point number.



“**QUOTA_EXCEEDED_ERR**” is the exception that will get thrown if you exceed your storage quota of 5 megabytes. “**No**” is the answer to the next obvious question, “Can I ask the user for more storage space?” At time of writing (February 2011), no browser supports any mechanism for web developers to request more storage space. Some browsers (**like Opera**) allow the user to control each site’s storage quota, but it is purely a user-initiated action, not something that you as a web developer can build into your web application.



# BEYOND NAMED KEY-VALUE PAIRS: COMPETING VISIONS

While **the past is littered with hacks and workarounds,** the present condition of HTML5 Storage is surprisingly rosy. A new API has been standardized and implemented across all major browsers, platforms, and devices. As a web developer, that’s just not something you see every day, is it? But there is more to life than “5 megabytes of named key/value pairs,” and the future of persistent local storage is… how shall I put it… well, there are competing visions.



One vision is an acronym that you probably know already: **SQL. In 2007,** Google launched **Gears,** an open source cross-browser plugin which included an embedded database based on **SQLite.** This early prototype later influenced the creation of the **Web SQL Database** specification. Web SQL Database (formerly known as “WebDB”) provides a thin wrapper around a SQL database, allowing you to do things like this from JavaScript:



↶ actual working code in 4 browsers


openDatabase('documents', '1.0', 'Local document storage', 5*1024*1024, function (db) {
  db.changeVersion('', '1.0', function (t) {
    t.executeSql('CREATE TABLE docids (id, name)');
  }, error);
});



As you can see, most of the action resides in the string you pass to the **executeSql** method. This string can be any supported SQL statement, including **SELECT, UPDATE, INSERT, and DELETE** statements. It’s just like backend database programming, except you’re doing it from JavaScript! Oh joy!


The Web SQL Database specification has been implemented by four browsers and platforms.



Of course, if you’ve used more than one database product in your life, you are aware that “**SQL**” is more of a marketing term than a hard-and-fast standard. (Some would say the same of “**HTML5,**” but never mind that.) Sure, there is an actual **SQL** specification (it’s called **SQL-92**), but there is no database server in the world that conforms to that and only that specification. There’s **Oracle’s SQL, Microsoft’s SQL, MySQL’s SQL, PostgreSQL’s SQL, and SQLite’s SQL.** Indeed, each of these products adds new SQL features over time, so even saying “**SQLite’s SQL**” is not sufficient to pin down exactly what you’re talking about. You need to say “the version of **SQL** that shipped with **SQLite** version **X.Y.Z.**”



All of which brings us to the following disclaimer, currently residing at the top of the **Web SQL Database** specification:



This specification has reached an impasse: all interested implementors have used the same SQL backend (Sqlite), but we need multiple independent implementations to proceed along a standardisation path. Until another implementor is interested in implementing this spec, the description of the SQL dialect has been left as simply a reference to Sqlite, which isn't acceptable for a standard.



It is against this backdrop that I will introduce you to another competing vision for advanced, persistent, local storage for web applications: **the Indexed Database API,** formerly known as “**WebSimpleDB,**” now affectionately known as “**IndexedDB.**”



The Indexed Database API exposes what’s called an *object store*. An object store shares many concepts with a SQL database. There are “databases” with “records,” and each record has a set number of “fields.” Each field has a specific datatype, which is defined when the database is created. You can select a subset of records, then enumerate them with a “cursor.” Changes to the object store are handled within “transactions.”



If you’ve done any SQL database programming, these terms probably sound familiar. The primary difference is that the object store has no structured query language. You don’t construct a statement like **"SELECT * from USERS where ACTIVE = 'Y'".** Instead, you use methods provided by the object store to open a cursor on the database named **“USERS,”** enumerate through the records, filter out records for inactive users, and use accessor methods to get the values of each field in the remaining records. **An early walk-through of IndexedDB** is a good tutorial of how IndexedDB works, giving side-by-side comparisons of **IndexedDB** and **Web SQL Database.**



At time of writing, **IndexedDB** has only been implemented in **a beta version of Firefox 4.** (By contrast, Mozilla has stated that **they will never implement Web SQL Database.**) Google has stated that **they are considering IndexedDB support** for Chromium and Google Chrome. And even Microsoft has said that IndexedDB **“is a great solution for the web.”**



So what can you, as a web developer, do with **IndexedDB**? At the moment, virtually nothing beyond some technology demos. A year from now? Maybe something. Check the “Further Reading” section for links to some good tutorials to get you started.
