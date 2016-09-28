---
layout: page
title: Personal Teachings
subtitle: Written By Vincent Lee
---

Pictures Are Coming Soon!

<center><h1>Beginner's Guide To Web Development</h1></center>


## Why Learn Computer Science / Web Development?

<center>
Most people shy away from programming because they perceive it as difficult or complex.
Another reason is due to the fact that they simply don’t know where to start.
I am here to show you that web development can be easy as well as fun!
Today Computer Science is denoted as a HOT field and I am not surprised.
In every major and every career CS is applied through some shape or form.
In this digital age, I have seen Business professionals write code,
Research analysts use programming software to generate their reports,
And Art students design and share their work through the World Wide Web.
Why learn about Web Development foremost when starting Computer Science?
Despite its popular demand, this is not a high-level programming language.
The industry changes every few years in terms of new code and new designs.
Riding the wave has become easy and recommended for all-ages young or old.
Most web developers are self-taught and all the materials are already up online.
It is accessible for mobile development and it’s easy to switch to other languages.
Finally starting your career; build your dreams from ingenuity and hard work!
To Play Devil’s advocate: Looking into a career in Web Development is difficult to find, unless you know exactly what you’re doing. While the demand is everywhere, there is a lot of competition due to over-saturation so you must never stop learning. Pre-generated websites such as Squarespace and related sites make web development obsolete. It is more useful to learn a high-level programming language rather than scripting languages.
</center>

## Text Editors

In order to write code you first need a setup a work environment through a text editor.

Download and Install ONE of the following Text Editors (I am currently using ATOM):

- https://atom.io/
- https://www.sublimetext.com/
- http://brackets.io/

I highly suggest that you create a folder for where you want to store your files. Then create a shortcut located on your Desktop or Desktop Toolbar just for ease of access. Finally go into settings or preferences to edit your workspace according to your liking. When you’re done, open a blank document so you can write your first program.

## HelloWorld

HelloWorld is like a long running a joke among serious programmers. Essentially for all beginners who are new to programming this project generates a print statement that says “Hello World”. This is the first script of code that you would write in any new language. Now in your recently downloaded text editor copy and paste the following into your document. If you haven’t already created a folder as a destination for where you want to store everything do so now and then save your document as “index.html” to create your first HTML file. Afterwards open the file to see your print statement generated through the web browser.

```
<html>
<head>
<title>Hello</title>
<body>
Hello World!
</body>
</head>
</html>
```

# HTML Basics (1hr)

Learning Everything Without My Help) http://www.w3schools.com/ & https://www.codecademy.com/

HTML is the content or the format of your website. Think of it like a newspaper column.
- (A Handy Cheat sheet) http://www.simplehtmlguide.com/cheatsheet.php
- (HTML Glossary) https://www.codecademy.com/articles/glossary-html

CSS is the style and design of your website. Envision all the color, animations, and looks that are displayed on a website.
- (Extensive CSS Cheat sheet) http://makeawebsitehub.com/css3-mega-cheat-sheet/
- (Simple CSS Tutorial) http://www.csstutorial.net/css-intro/introductioncss-part1.php
- (MDN for CSS) https://developer.mozilla.org/en-US/docs/Web/CSS
- (Front-end Designs, not only CSS) http://codepen.io/#

JavaScript is the interactive and functional part of your website. Imagine all the buttons, calculations, and interactions being updated alongside a website.
- (JavaScript Tutorial) http://www.tutorialspoint.com/javascript/
- (Reading About JavaScript) http://eloquentjavascript.net/
- (MDN for JavaScript) https://developer.mozilla.org/en-US/docs/Web/JavaScript

## Structure

Remember the “HelloWorld” script that you copied above. This is a diagram of a basic HTML structure. The HTML tags will illustrate its specific markup function on the browser. Keep in mind, from the starting tag <> up to the ending tag </> it encompasses every content information that you put in between the tags.

Create a static page using the basic structure of HTML as seen above. Insert content that you think is relevant to your website or product. Feel free to make your own changes, but forewarning we will eventually create a new document to build a functional website later on.

## List
- <li> = List item
- <ol> = Ordered list
- <ul> = Unordered list
- <dt> = Term in description list
- <dd> = Description in description list
- <dl> = Description list
List and text styles are not really important to web developers. However for general markup they may be useful to learn. Especially if you wish to emphasize the writing of your content.

## Text Styles
- <b> = Bold
- <i> = Italics
- <mark> = Highlighted
- <del> = Strikethrough
- <ins> = Underline

## HREF & IMG
The HREF attribute specifies the link's destination. Links are reference point to another website, url, document, or section of a webpage.

I apologize, originally I wanted to demonstrate the webpage’s functionality through video and animate gifs. However to my disappointment pdfs & word documents prevent proper usage of inserted media files. Instead, I wrote descriptions for one to copy & paste into the <body> section of the HTML document.

```{r, eval = F}
<a href="https://www.google.com/"> Google </a>
A link named “Google” that sends you directly to Google.
<a href="mailto:email_name@gmail.com"> Email Me! </a>
A link named “email me!” that ask your email browser whether you want to compose an email to “email_name@gmail.com”
<a href="javascript:alert('Hello World!');"> Click Me! </a>
A link named “click me!” that opens a javascript alert to write you a “helloworld” print statement.
<img src="http://masterpiecemanager.com/wp-content/uploads/2012/07/art-management.png" alt="some_text">
This creates an image source where you copy & paste the exact URL to call the image. Alt is used for naming purposes, it specifies an alternative text. Don’t worry about alt, we may talk more about this in CSS.
<img src="IF.png" alt="some_other_text" style="width:328px;height:328px;">
You will NOT SEE THIS EXACT IMAGE. To create this image source you want to have your own image and drag it into the same folder as your “index.html” next set img src = as the exact name and file type of the image. Style is used to adjust the size of the image so it doesn’t become too large or small.
<a href="https://developer.android.com/index.html"><img src="https://pbs.twimg.com/profile_images/616076655547682816/6gMRtQyY.jpg" alt="android_picture"></a>
This transforms your image into a clickable link!
```

My page looks somewhat like this:

# CSS Basics (1 ~ 9hrs)

For proper documentation always place <!DOCTYPE HTML> at the top of your document to declare that HTML will be used in your page and rendered through the browser. Also insert the meta content tag underneath <head>. The meta tag is important since the browser uses it to decode the specifics of the HTML document such as descriptions, metadata, etc.

After you inserted the proper html documentation; the browser can understand and identify the content. Now copy & paste this <link> tag and place it underneath <head>. This link will connect your HTML and CSS documents together. Once that’s done, create your new CSS file, name it “main.css”.<link rel ="stylesheet" type="text/css" href="main.css">

By the way, I highly encourage that you download and install packages for your text editor. If you’re not using Atom go online or use google to setup “Colorpicker” since we will be using it in the following steps.

To install packages in Atom go to File > Settings > Install. These are the packages that I use:
- Color-picker
- Emmet
- Atom-beautify
- File-icons
- Pigments
- Minimap
- Linter

I suggest that you take the time to browse the library for any popular packages that you think will help improve the design and efficiency of your workspace.

Now when working with CSS it important to know that the layout uses “cascading” and “inheritance” which means the parent overrides the child elements. In other words, if two elements have the same weight the latter wins and overrides the other element with its rule.

When implementing CSS styles to your HTML content we use selectors to pinpoint which area to enhance your content with CSS. There are several types of selectors which determines the order of specify. For now, we only need to know these types of
selectors:

- ID Selectors – <div id = “…” >: The top level order in CSS specify. It’s good and bad because you can only use each id once and it tends to override everything.
- Class Selectors - <div class = “…” >: The most versatile selector that is also very useful because you can call the rule while using multiple classes into your HTML document.
- Tag Selectors - <body, p, h1, etc >: Simple and clean for changing properties related to entire selected HTML Tag.
To learn more about selectors go to: https://css-tricks.com/how-css-selectors-work/

##Style & Color

Fonts Type Syntax
```
font-family: "Times New Roman", Georgia, Serif;
```

There are many different font families try going online to copy these common font types: http://cssfontstack.com/oldsites/cssfontstack/

## Font Color Syntax
```
color: blue;
color: #9938b0
color: rgb(194, 34, 34)
```

When picking colors you can type the name, use hexadecimal, or RGB numbers. Thankfully, color-picker makes it simple to choose the right color. (In atom, right click to find color-picker.)

## Font Size Syntax
```
font-size: 12px;
```

Personally I use pixel units for everything, but it’s helpful to learn about the relative lengths: http://www.w3schools.com/cssref/css_units.asp

HTML

CSS

```
Background
Background Color Syntax
background-color: black;
```

It works exactly the same as font color just add it to background. Also use the <body> tag as the selector for the entire page.

## Gradients Syntax
```
background:linear-gradient(45deg, #791010, #EA5D08);
```

If you don’t want to use a solid color background change it into a gradient background. Add the linear-gradient to your background and set the degree or transition angle of the two colors you want merge into your gradient.

## Background Image Syntax
```
background-image: url(“…”);
```

Setting the background image is simple. You can just write the name with the file type of your image as long as it’s in the same location as your CSS file. The other option is to copy & paste the URL directly from online. This is more intuitive than adding images through HTML.

## Background Size
```
background-size: cover;
or
background-size: 100% 100%;
background-repeat: no-repeat;
```

In order to have your background image cover your entire browser I suggest you set your background size to width 100% height 100% or “cover”. (High resolution pictures perform better).

## Background Attachment / Effects
- https://css-tricks.com/almanac/properties/b/background-attachment/
- http://www.w3schools.com/css/css_background.asp
- https://codepen.io/keithclark/pen/JycFw

You can do a lot with CSS all it takes is hard work and ingenuity. Try finding inspiration from other designers and inmate their techniques to make it your own.

## Images

Import Image

```
<img src="http://www.shopbelmontmarket.com/wp content/uploads/page_img_sushi_01.jpg" class="pic1">
```

To add an image you do it from HTML. Remember you used <img src = “…” class = “some_text”>. For specificity reasons you want to create a <class> selector on the image source because you will be editing it through CSS.

Please notice when selecting images:
- Some images have transparent backgrounds while others do not.
- When using a lower resolution images it becomes pixelated when you stretch it out. The only exception to scalable pictures are vector images made from Adobe Illustrator.
- Sometimes images don’t last when selecting from a URL. Always try to save and store your image into a fixed folder.

Image Size

```
img {
width: 50%;
height: auto;
}
```
Similar to font size, control your image size through height and width parameters. Remember your relative lengths, percentages, or pixels when adjusting the size. Sometimes resizing can be tricky, but Googling answers all your needs.

Image Effect

```
img :hover{
-webkit-filter: grayscale(100%); /* Chrome, Safari, Opera */
filter: grayscale(100%);
}
```

This script is an example of desaturating an image when you hover over them, try it out. You can insert fascinating effects onto your images by applying these filters. Filter effects are impressive when you combine them with animation.

## Position

Margin Size (generates space around the element):
- Margin-top: 100px;
- Margin-right: 150px;
- Margin-bottom: 100px;
- Margin-left: 150px;

Or use margin (clockwise from the top)

- Margin: 25px 50px 75px 100px; (top, right, bottom, left)

Padding Size (generates space within the element):
- Padding-top: 100px;
- Padding-right: 150px;
- Padding-bottom: 100px;
- Padding-left: 150px;

 Or use Padding (clockwise from the top)

- Padding: 25px 50px 75px 100px; (top, right, bottom, left)

The types of positions listed:
- Relative
- Static
- Fixed
- Absolute
- Sticky

Learn more about these position types here: https://developer.mozilla.org/en-US/docs/Web/CSS/position

Positioning

- Top Left
- Top Right
- Centered
- Bottom Left
- Bottom Right

Other Positional Elements

- Overflow
- Visible
- Hidden
- Scroll
- Auto
- Float
- In-line Block

Learn more about these position elements here:
- https://css-tricks.com/almanac/properties/o/overflow/
- http://www.w3schools.com/css/css_overflow.asp
- http://www.w3schools.com/css/css_float.asp
- http://www.w3schools.com/css/css_inline-block.asp

## Border

Border Type
- Border-width: thickness in pixels
- Border-color: any color
- Border-style: listed below.
- Border shadow: 2px (height) 2px (width) 2px (blur)
- Border-radius: 25px (for rounded borders) 100% (for circle or ovals)

The types of border style listed (from http://www.w3schools.com/css/css_border.asp):

Congratulations! You made a basic static webpage! But now you’re going to throw almost everything out because Bootstrap is a much fancier webpage layout that everyone is using.

## Bootstrap

Get BootStrap) http://getbootstrap.com/
- Unzip your download and move the file folder location to where you keep all your other documents.
= Link the Bootstrap CSS file similar to how you link the “main.css” file. Bootstrap should provide you with this script on their site. Just copy and paste their link underneath head or alongside where you made a link for “main.css”:

```
<!-- Latest compiled and minified CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<!-- Optional theme -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

<!-- Latest compiled and minified JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
```

- Look at some of the basic templates, window shop for something that you may like.
- Also make sure the javascript is linked properly or there will functional issues.

## Navbar

At the meantime, we are going to copy the navbar from here:
- https://bootswatch.com/ pick a theme and copy its navbar.
- The source code should be there to copy if you hover over to the right.
- Design your own http://work.smarchal.com/twbscolor/css/e74c3cc0392becf0f1ffbbbc0
- Or go to the official site to learn more http://getbootstrap.com/components/#navbar
- As well as http://getbootstrap.com/components/#nav .

Now we are going to create a webpage using Bootstrap integration. It is completely optional, but I suggest that you create a new HTML and CSS file to prevent Bootstrap from conflicting with your previous work. Place the navbar within the new HTML file. It should be right underneath the starting tag of <body> then edit the contents of the navbar button.

To add a brand or logo on the title bar:
```
<title>Some Title Name </title>
<link rel="icon" type="img/png" href="img.png">
To add a brand or logo on the navbar:
<a class="navbar-brand" href="#">FoodBlogger
<img alt="Brand" id = "logo" src="breddit.png">
</a>
```

## Layout

Now you want to think about layout. This is very important for web designers because an organized layout makes it easy for the reader to understand and where to place ads. Check out several layout designs and adopt the one that you think works best for your website. Also look at other websites you may learn something.


Bootstrap’s Grid layout works like this:
- http://getbootstrap.com/examples/grid/
-  http://www.w3schools.com/bootstrap/bootstrap_grid_basic.asp
-  http://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-grid-system.php

We want to use bootstrap’s grid layout since it allows for responsive web design. Responsive web design essential allows your webpage to shrink and adapt to other screen sizes. It allows your webpage to be good looking on desktops, tablets, and smartphones. Notice how when you minimize and enlarge you browser screen, you can see the text and images adjust accordingly.
Now add images, videos, and content to your site. Feel free to copy the content from your other HTML file, but be sure to adjust it according to Bootstrap’s layout.

I don’t know whether or not you can see the difference. Imagine the left side is a visual representation of a mobile version while the right side is a stretched desktop website.

## Other Elements

Learn everything here: http://www.w3schools.com/bootstrap/default.asp
Here are fancy things that you can add on using bootstrap:
- Glyphicons (just add <span class="glyphicon glyphicon-name"></span> ): http://getbootstrap.com/components/
- Carousel (you need a little bit of javascript): http://www.w3schools.com/bootstrap/bootstrap_ref_js_carousel.asp

Sorry again you may have already noticed, I’m slowly losing motivation to teach proper. However like I always say “Google is your friend.” Don’t worry, all web developer learn through googling. In addition, if you ever plan on making just a blog use Wordpress. Setup time should only take a couple hours, it’s free with a web host, and it is as easy as HTML.

# JavaScript Basics (??? hrs)

## Understanding JavaScript

Now create a JavaScript file called scripts.js you. Remember to link that JavaScript file with your HTML file.
To understand JavaScript you must first understand:
- Basic Value, Types, & Operators
- Variables
- Var name = "Vincent";
- console.log(name); [print statement]
- // → Vincent
- Functions
- http://eloquentjavascript.net/
- https://www.codecademy.com/learn/javascript
- http://javascript.info/
- https://www.youtube.com/watch?v=XL9Ri8pO68w

## Writing a Simple Function

```
// HTML
<html>
<head>
<title>Hello</title>
<body>
<h1> Function </h1>
<p id = “myText”> Watch me change when you the click of a button </p>
<p> <button type = “button” onclick=”myFunction()”> Click me </button>
</p>
// JS
<script>
Function myFunction() {
Document.getElementById(“myText”).innerHTML = “HelloWorld!”
}
</script>
</body>
</head>
</html>
```

# Setting Up Github and Node.js

First download and install Node.js while you’re doing that go to Github and create an account.

- https://github.com/
- https://nodejs.org/en/

Github is a version control system that allows you to build a repository where one can host and share their work online. Github makes it easy for people to collaborate and save their work on demand. This also works great as a portfolio for your code in which many employers ask to look at. It is helpful that you setup git alongside your text editor or terminal to transfer your progress in your online repository. Since github is a service repositories are public and you have to pay for privacy.

## Git Commands:
- Commit (save)
- Push (upload)
- Clone (download the entire repo)
- Pull (download or merge changes)
- Branch (creates a new branch or file to work and test your program)
- Never mind, just look at this cheat sheet https://services.github.com/kit/downloads/github-git-cheat-sheet.pdf

Node.js is built on JavaScript it allows a person to build fast and scalable net applications. Essentially we use it to run a web server where we would use real-time interactions such as chat posts, transactions, etc. Using Node.js and React.js is definitely the next step when advancing to become real web developer.

Ignore this if you have no interest in advancing:

Learn more here: http://www.tutorialspoint.com/nodejs/nodejs_first_application.htm and https://www.airpair.com/javascript/node-js-tutorial

Note: What works for me may not work for you.

```
Setup node.js
First, open up a terminal and install Node Inspector, which is use to debug Node projects:
$ npm install -g node-inspector
Next, install Postman. You can either install it to Google Chrome as an “App”, or install the standalone version by googling Postman; they are essentially the same thing. Postman makes it easy for you to test your web server with HTTP requests.
Next run the following command to install modules, npm helps install packages:
$ npm install express
Finally, run the following command within the server folder to open up the Atom editor in the server folder:
$ atom
“Hello World!”
You should have Atom open within the server folder of the repository. Create a new file called src/helloworld.js, and include the following inside of it: console.log("Hello World!");
Save the file, and open a terminal to the server folder of the repository. Run your new Node.JS program with the following command:
$ node src/helloworld.js
Hello World!
```

# Adding Interactions (1 ~ 3hrs)

## Animations

For amazing animations simply download and link the CSS with animate.css: https://daneden.github.io/animate.css/

## Buttons

Strange that I left this crucial detail for the last, but have you noticed how your buttons or navbar doesn’t actually work when clicked. Well, you have to bind your HREF:# to a specific section or URL. For example, HREF:index.html will send you to your homepage and HREF:about.html is a new HTML file that you created. I suggest that you copy over the nav, main design, and structure while adding different content such as details “about us”. Buttons that you copied and paste from Bootstrap fundamentally work the same way. However you may want to use “form” or “JavaScript” actions instead of HREF.

## Finishing Touches (1 ~ 5hrs)

How to deploy a site

- The easiest way! http://www.lemiffe.com/how-to-deploy-a-static-page-to-heroku-the-easy-way/
- Learn more: https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Publishing_your_website
- The hard way involves paying money on a monthly basis to a domain & hosting website!

# Learn More) References or Other Sources

I still haven’t taught you a lot of other stuff like integrating APIs, posting comments, forms, encryption, and other interactions. Well, this is a beginner’s tutorial. Also everything is up online like I said within my abstract section of this document. Best of luck! Truth be told, I recommend that you go on sites like code academy because they teach and articulate Web Development better than I do:

- https://www.codecademy.com/
- https://www.coursera.org/
- http://www.teachingtree.co/
- http://ocw.mit.edu/index.htm
- http://www.teachyourselftocode.com/
- http://www.w3schools.com/
- http://www.tutorialspoint.com/web_development_tutorials.htm
- https://www.youtube.com/user/derekbanas/videos
- https://www.youtube.com/user/thenewboston
- https://www.youtube.com/user/LevelUpTuts/videos
- https://www.youtube.com/user/DevTipsForDesigners/videos
- (my web development class if it still exists) http://umass-cs-326.github.io/
