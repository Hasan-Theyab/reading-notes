# What Google Learned From Its Quest to Build the Perfect Team

**Like most 25-year-olds,** Julia Rozovsky wasn’t sure what she wanted to do with her life. She had worked at a consulting firm, but it wasn’t a good match. Then she became a researcher for two professors at Harvard, which was interesting but lonely. Maybe a big corporation would be a better fit. Or perhaps a fast-growing start-up. All she knew for certain was that she wanted to find a job that was more social. ‘‘I wanted to be part of a community, part of something people were building together,’’ she told me. She thought about various opportunities — Internet companies, a Ph.D. program — but nothing seemed exactly right. So in 2009, she chose the path that allowed her to put off making a decision: She applied to business schools and was accepted by the Yale School of Management.




**The technology industry** is not just one of the fastest growing parts of our economy; it is also increasingly the world’s dominant commercial culture. And at the core of Silicon Valley are certain self-mythologies and dictums: Everything is different now, data reigns supreme, today’s winners deserve to triumph because they are cleareyed enough to discard yesterday’s conventional wisdoms and search out the disruptive and the new.



The paradox, of course, is that Google’s intense data collection and number crunching have led it to the same conclusions that good managers have always known. In the best teams, members listen to one another and show sensitivity to feelings and needs.



The fact that these insights aren’t wholly original doesn’t mean Google’s contributions aren’t valuable. In fact, in some ways, the ‘‘employee performance optimization’’ movement has given us a method for talking about our insecurities, fears and aspirations in more constructive ways. It also has given us the tools to quickly teach lessons that once took managers decades to absorb. Google, in other words, in its race to build the perfect team, has perhaps unintentionally demonstrated the usefulness of imperfection and done what Silicon Valley does best: figure out how to create psychological safety faster, better and in more productive ways.



‘‘Just having data that proves to people that these things are worth paying attention to sometimes is the most important step in getting them to actually pay attention,’’ Rozovsky told me. ‘‘Don’t underestimate the power of giving people a common platform and operating language.’’



Project Aristotle is a reminder that when companies try to optimize everything, it’s sometimes easy to forget that success is often built on experiences — like emotional interactions and complicated conversations and discussions of who we want to be and how our teammates make us feel — that can’t really be optimized. Rozovsky herself was reminded of this midway through her work with the Project Aristotle team. ‘‘We were in a meeting where I made a mistake,’’ Rozovsky told me. She sent out a note afterward explaining how she was going to remedy the problem. ‘‘I got an email back from a team member that said, ‘Ouch,’ ’’ she recalled. ‘‘It was like a punch to the gut. I was already upset about making this mistake, and this note totally played on my insecurities.’’



If this had happened earlier in Rozovsky’s life — if it had occurred while she was at Yale, for instance, in her study group — she probably wouldn’t have known how to deal with those feelings. The email wasn’t a big enough affront to justify a response. But all the same, it really bothered her. It was something she felt she needed to address.




# CSS TRANSFORMS

With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.



The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.



Within this lesson we’ll take a look at both two-dimensional and three-dimensional transforms. Generally speaking, browser support for the transform property isn’t great, but it is getting better every day. For the best support vendor prefixes are encouraged, however you may need to download the nightly version of Chrome to see all of these transforms in action.



### Combining Transforms


It is common for multiple transforms to be used at once, rotating and scaling the size of an element at the same time for example. In this event multiple transforms can be combined together. To combine transforms, list the transform values within the transform property one after the other without the use of commas.


Using multiple transform declarations will not work, as each declaration will overwrite the one above it. The behavior in that case would be the same as if you were to set the height of an element numerous times.


## 3D Transforms

Working with two-dimensional transforms we are able to alter elements on the horizontal and vertical axes, however there is another axis along which we can transform elements. Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.


### Transform Style

On occasion three-dimensional transforms will be applied on an element that is nested within a parent element which is also being transformed. In this event, the nested, transformed elements will not appear in their own three-dimensional space. To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.


The transform-style property needs to be placed on the parent element, above any nested transforms. The preserve-3d value allows the transformed children elements to appear in their own three-dimensional plane while the flat value forces the transformed children elements to lie flat on the two-dimensional plane.

### Backface Visibility

When working with three-dimensional transforms, elements will occasionally be transformed in a way that causes them to face away from the screen. This may be caused by setting the rotateY(180deg) value for example. By default these elements are shown from the back. So if you prefer not to see these elements at all, set the backface-visibility property to hidden, and you will hide the element whenever it is facing away from the screen.


The other value to backface-visibility is visible which is the default value, always displaying an element, no matter which direction it faces.


# CSS TRANSITIONS & ANIMATIONS

### Transitions

As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.

There are four transition related properties in total, including transition-property, transition-duration, transition-timing-function, and transition-delay. Not all of these are required to build a transition, with the first three are the most popular.


### Animations

Transitions do a great job of building out visual interactions from one state to another, and are perfect for these kinds of single state changes. However, when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.

# 8 SIMPLE CSS3 TRANSITIONS THAT WILL WOW YOUR USERS

### 1. Fade in

Having things fade in is a fairly common request from clients. It’s a great way to emphasize functionality or draw attention to a call to action.

Fade in effects are coded in two steps: first, you set the initial state; next, you set the change, for example on hover:

.fade


{


        opacity:0.5;


}


.fade:hover



{


        opacity:1;


}


### 2. Change color

Animating a change of color used to be unbelievably complex, with all kinds of math involved in calculating separate RGB values and then recombining them. Now, we just set the div’s class to “color” and specify the color we want in our CSS:


.color:hover


{


        background:#53a7ea;


}


### 3. Grow & Shrink

To grow an element, you used to have to use its width and height, or its padding. But now we can use CSS3’s transform to enlarge.

Set your div’s class to “grow” and then add this code to your style block:


.grow:hover


{


        -webkit-transform: scale(1.3);


        -ms-transform: scale(1.3);


        transform: scale(1.3);



}



### 4. Rotate elements

CSS transforms have a number of different uses, and one of the best is transforming the rotation of an element. Give your div the class “rotate” and add the following to your CSS:


.rotate:hover


{


        -webkit-transform: rotateZ(-30deg);




        -ms-transform: rotateZ(-30deg);




        transform: rotateZ(-30deg);



}



### 5. Square to circle

A really popular effect at the moment is transitioning a square element into a round one, and vice versa. With CSS, it’s a simple effect to achieve, we just transition the border-radius property.

Give your div the class “circle” and add this CSS to your styles:



.circle:hover


{



        border-radius:50%;




}



### 6. 3D shadow

3D shadows were frowned upon for a year or so, because they weren’t seen as compatible with flat design, which is of course nonsense, they work fantastically well to give a user feedback on their interactions and work with flat, or fake 3D interfaces.

This effect is achieved by adding a box shadow, and then moving the element on the x axis using the transform and translate properties so that it appears to grow out of the screen.

Give your div the class “threed” and then add the following code to your CSS:


.threed:hover


{


        box-shadow:


                1px 1px #53a7ea,


                2px 2px #53a7ea,


                3px 3px #53a7ea;



        -webkit-transform: translateX(-3px);



        transform: translateX(-3px);




}



### 7. Swing

Not all elements use the transition property. We can also create highly complex animations using @keyframes, animation and animation-iteration.

In this case, we’ll first define a CSS animation in your styles. You’ll notice that due to implementation issues, we need to use @-webkit-keyframes as well as @keyframes (yes, Internet Explorer really is better than Chrome, in this respect at least).


@-webkit-keyframes swing


{


    15%


    {


        -webkit-transform: translateX(5px);


        transform: translateX(5px);


    }


    30%


    {
        -webkit-transform: translateX(-5px);


       transform: translateX(-5px);



    } 



    50%



    {



        -webkit-transform: translateX(3px);


        transform: translateX(3px);
    }



    65%


    {


        -webkit-transform: translateX(-3px);


        transform: translateX(-3px);


    }


    80%


    {


        -webkit-transform: translateX(2px);


        transform: translateX(2px);


    }


    100%




    {


        -webkit-transform: translateX(0);


        transform: translateX(0);


    }


}


@keyframes swing


{


    15%

    {


        -webkit-transform: translateX(5px);


        transform: translateX(5px);


    }


    30%


    {


        -webkit-transform: translateX(-5px);


        transform: translateX(-5px);


    }


    50%

    {

        -webkit-transform: translateX(3px);

        transform: translateX(3px);

    }


    65%

    {








        -webkit-transform: translateX(-3px);



        transform: translateX(-3px);



    }


    80%

    {

        -webkit-transform: translateX(2px);



        transform: translateX(2px);

    }
   
   
    100%
   
   
    {
   
   
        -webkit-transform: translateX(0);
   
   
   
   
        transform: translateX(0);
   
   
    }
}






### 8. Inset border

One of the hottest button styles right now is the ghost button; a button with no background and a heavy border. We can of course add a border to an element simply, but that will change the element’s position. We could fix that problem using box sizing, but a far simpler solution is the transition in a border using an inset box shadow.

Give your div the class “border” and add the following CSS to your styles:


.border:hover


{



        box-shadow: inset 0 0 0 25px #53a7ea;



}





# 6 Buttons animated

### HTML:

div class="group"
		button class="blam"Blam/button
		button style="-webkit-animation-delay: .3s;animation-delay: .3s;" class="syke">Syke</button>
		button style="-webkit-animation-delay: .6s;animation-delay: .6s;" class="later">Later</button
	/div

# CSS:

@import url(https://fonts.googleapis.com/css?family=Droid+Sans:700);
		*{
			margin: 0;
			
            padding: 0;
			
            box-sizing: border-box;
			
            transition: all .1s;
		}

		
        body{
		
        background-color: #424242;
		
        	font-family: 'Droid Sans', sans-serif;
		
        }
		
        .group{
			text-align: center;
		
        	margin: 20px auto;
		
        }
		.group button{
		
        	margin-top: 10px;
		
        }
		
        button{
/*		
	box-sizing: border-box;*/

			background: NONE;

			border: none;

			outline: none;

			border-radius: 3px;


			padding: 15px 70px;

			color:white;

			text-transform: uppercase;

			font-weight: 700;


			text-shadow: 0 1px 3px rgba(0, 0, 0, 0.41);

			box-shadow: 0 3px 0 0 #383838;

			border:3px solid transparent;






			animation: pulse 1s linear infinite alternate;

			-webkit-animation: pulse 1s linear infinite alternate;

		}

		.active,

		button:active{

			background-image: linear-gradient(rgba(0,0,0,.1) 13%, 
            transparent 13%,transparent);
			
            box-shadow: 0 1px 0 0 #383838;
			
            color: rgba(0, 0, 0,.45);
			
            text-shadow: none;
			

			

			
            -webkit-animation-play-state: paused; 
    	anim
        ation-play-state: paused;
		
        }
		
        button:focus,
		
        button:hover{
		
        	-webkit-animation-play-state: paused; 
    	
        animation-play-state: paused;
		
        }
		

		

		
        .blam:focus,
		
        .blam:hover{
		
        	background-color:#0097bd;
		
        }
		
        .blam{
		
        	background-color:#00bff0;
		
        	border-color: #00bff0;
		
        }
		

		
        .syke:focus,
		
        .syke:hover{
		
        	background-color:#ad4e4e;
		
        }
		
        .syke{
		
        	background-color:#e06464;
		
        	border-color:#e06464;
		
        }
		

		
        .later:focus,
		
        .later:hover{
		
        	background-color:#7c8b8f;
		
        }
		
        .later{
		
        	background-color:#a8bdc2;
		
        	border-color:#a8bdc2;
		
        }
		

		
        @-webkit-keyframes pulse {
		
        	100% {
		
        		transform: translateY(6.9px); 
		
        	} 
		
        }




		@keyframes pulse {

			100% {

				transform: translateY(6.9px); 

			} 

		}



        