# Responsive Layout Code Along

## Objectives

1. Review Viewport
2. Review CSS Media Queries
3. Review Responsive Strategies

## Introduction

Building upon previous code alongs, in this exercise you will make your pages responsively alter their layouts on different size devices by coding along with the video provided. This will help you to review the concepts you were introduced to in the previous lessons. 

*Note: to get the finished site code for this code along series you can download the zip file linked at the bottom of this lesson.*

## Instructions

1. Fork this repository.
2. Use Terminal to clone your forked copy.
3. Then change directory into the repository folder.
4. Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="100%" height="720" src="//www.youtube.com/embed/qxxJhKd2VDE?rel=0&controls=1&showinfo=1" frameborder="0" allowfullscreen></iframe>

### Creating Responsive Layouts

Lets start out by making a new feature branch in Terminal by typing `git checkout -b responsive-design` and press return. 

Then open the index.html page in your code editor. Let's add a meta tag at the top of the `<head>` section to handle the viewport teliing it not to resize but isntead use the devices size to drive our media queries we will write coming up.

```html

```



It's now time to version our changes using Git. To do so, in Terminal type `git add .` and press return. Then type `git commit -m "add responsive layout"` and press return. Then push up this feature branch `git push -u origin responsive-design` and press return. Next merge the changes into your master branch. Type `git checkout master` and press return, then `git merge responsive-design` and press return. Then `git push origin master` and press return.

After you finish, make sure you install Firefox if you haven't already as it is required for the screenshot tests to run. Then, type learn command from Terminal to run local tests (Mac) or type learn-test for Windows.

After all tests are passing submit a pull request on Github and move on to the next lesson!

## Resources

- [Exceptional Realty - Finished Site Code](http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/exceptional-realty.zip)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-ex-7' title='OCode Along Exercise 7'>Code Along Exercise 7</a> on Learn.co and start learning to code for free.</p>
