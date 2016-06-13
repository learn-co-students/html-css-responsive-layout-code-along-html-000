# Responsive Layout Code Along

## Objectives

1. Review Viewport
2. Review CSS Media Queries
3. Review Responsive Strategies

## Introduction

Building upon previous code alongs, in this exercise you will make your pages responsively alter their layouts on different size devices by coding along with the video provided. This will help you to review the concepts you were introduced to in the previous lessons. 

*Note: to get the finished site code for this code along series you can download the zip file linked at the bottom of this lesson.*

## Instructions

1. Type `learn open html-css-responsive-layout-code-along` to obtain a local copy of this lesson.
2. Then change directory into the repository folder.
3. Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="100%" height="720" src="//www.youtube.com/embed/qxxJhKd2VDE?rel=0&controls=1&showinfo=1" frameborder="0" allowfullscreen></iframe>

### Creating Responsive Layouts

Lets start out by making a new feature branch in Terminal by typing `git checkout -b responsive-design` and press return. 

Then open the index.html page in your code editor. Let's add a meta tag at the top of the `<head>` section to handle the viewport teliing it not to resize but isntead use the devices size to drive our media queries we will write coming up.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0">
  <title>Exceptional Realty Group - Luxury Homes - About</title>
  ...
</head>
```

Next, lets add another stylesheet for our responsive styles just after our style.css.

```html
<head>
  ...
  <link rel="stylesheet" href="css/style.css">
  <link rel="stylesheet" href="css/responsive.css">
  ...
</head>
```

The let's add the new meta tag and stylesheet link to the head elements of all our other html pages and save them.

Now in the css folder lets create our new file `responsive.css`, back in Terminal type `touch css/responsive.css` and press return.

Then back in Chrome browser bring up the developer tools by pressing Command + Option + i (Mac) or Ctrl + Shift + i (Windows). Once the develoepr tools are open click and drag the bottom right corner of the browser window to resize it. You will notice as your dragging the width and height of the screen appears in the top right corner fo the screen respectively. We will be making a note of the first number the width. THe idea here is to scale the browser down to smaller wisths and make a note of the width measurement at which the content starts to look awkward, then we will write a specific media query in our CSS to address these issues one by one.

Around 1108px the social icons are starting to get close to overlapping the main content in the wrapper. Let's write a media query to handle this. Bring up the responsive.css file in your code editor and add the following media query.

```css
@media only screen and (max-width: 1108px) {
  .wrapper {
    width: 90%;
  }
  
  #social {
    position: absolute;
    top: 82px;
    right: 4%;
    width: auto;
  }
  
  #social a {
    display: inline-block;
  }
}
```

Now save and refresh the page in the browser. You'll notice when the browser width is adjusted below 1108 pixels our social icons stack horizontally and position themselves on top of the logo bar. Let's continue scaling the browser window down to see when other content starts to look awkward. At 900 pixels I notice that some of the text looks a little big such as in the paragraphs as well as the main navigation the text in the links starts to get close to the edges. Let's write a new media query for this in the responsive.css file in our code editor.

```css
@media only screen and (max-width: 900px) {
  body {
    font-size: 85%;
  }
  
  #logo h1 {
    width: 35px;
    height: 35px;
  }
  
  #logo h2 {
    font-size: 2.2em;
  }
  
  #social {
    top: 72px;
  }
  
  .col-3 p {
    -moz-column-count: 2;
    -webkit-column-count: 2;
    column-count: 2;
  }
}
```

On line 3 in the code snippet above you can see we adjusted the body font-size using a percent. Since I set all my type to em measurements this will make all the text of the site scale down from 100% to 85% (15% smaller). On line 7 and 8 we set the h1 logo to be about 10 pixels smaller than it was before, and on line 12 we set the h2 to be a bit smaller as well. On line 15 we adjusted the social icons to be a touch closer to the top of the screen helping to align them with the smaller logo adjustment. On line 20 - 22 we setthe paragraphs in columns that fill the wrapper to adjust to having their own internal column count of 2 instead of 3 like they are at larger devices. Save the CSS file and refresh the browser to see these changes. Then let's continue scaling down the browser to see when our styles need more adjusting.

At 800 pixels the market report text inside the main navbar is looking a bit close to the edges of the link. So we'll create a new media query to handle that.

```css
@media only screen and (max-width: 800px) {
  #navbar nav a {
    font-size: 0.9em;
  }
}
```

Everything is looking pretty good, but the multi column layout is looking a little squeezed under 750px, so let's create a new media query to move to a single column layout on any devices below 750 pixels wide.

```css
@media only screen and (max-width: 750px) {
  .col-1, .col-2, .col-3 {
    width: 100%;
    margin-left: 0;
    float: none;
  }
  
  .border-right {
    border-right: 0;
  }
  
  #details div {
    height: auto;
    padding-bottom: 20px;
  }
  
  .col-3 p {
    -moz-column-count: 1;
    -webkit-column-count: 1;
    column-count: 1;
  }
}
```

This will set the columns to a single column taking up the full width of the wrapper. We also removed the border from the right side of the divs in the details section as well as set their height to auto. Now, save the CSS and refresh in the browser. Looking much better on smaller devices now!

As wel continue to scale down even smaller I notice that the main navigatuion icons are looking crowded. We can fix this by using a traditional strategy of hiding the navigation links and instead displaying a menu icon (hamburger icon) that when the user clicks will display the menu links.

Back to responsive.css.

```css
@media only screen and (max-width: 700px) {
  #navbar nav a {
    display: none;
  }
  
  #navbar nav a.menu-icon {
    display: block;
    float: right;
    font-size: 1.5em;
    padding: 10px 20px;
    width: auto;
  }
  
  #logo {
    padding: 60px 0 0;
  }
  
  #social {
    top: 60px;
  }
}
```

Here we are setting the menu-icon to appear and all the other nav links to hide. Let's save this CSS file and head back to the browser and refresh. You should see the menu icon appear and the other links disappear under 700px. Currently clicking the menu icon has no effect. Typically we would use Javascript to listen for clicks on this icon and then display the menu links again below the menu icon as a vertical list. If you are interested to see the completed code for this you can download the zip file with the finished code from the link in the resources at the bottom of this lesson.

After scaling the browser a bit smaller the only thing that looks like it needs adjusted now is that logo is getting close to the social icons they are sharing the horizontal space with. Let's write one last media query to hide the `h2`.

```css
@media only screen and (max-width: 495px) {
  #logo h2 {
    visibility: hidden;
  }
}
```

Save the CSS and refresh in the browser. Now scaling the device (browser) up an down our media queries are providing smooth style changes to our layout. Our site look oretty good on all pages.

It's now time to version our changes using Git. To do so, in Terminal type `git add .` and press return. Then type `git commit -m "add responsive layout"` and press return. Then push up this feature branch `git push -u origin responsive-design` and press return. Next merge the changes into your master branch. Type `git checkout master` and press return, then `git merge responsive-design` and press return. Then `git push origin master` and press return.


## Resources

- [Exceptional Realty - Finished Site Code](http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/exceptional-realty.zip)
- [Chrome Developer Tools Overview](https://developer.chrome.com/devtools)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-ex-7' title='OCode Along Exercise 7'>Code Along Exercise 7</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/html-css-responsive-layout-code-along'>Responsive Layout Code-Along</a> on Learn.co and start learning to code for free.</p>
