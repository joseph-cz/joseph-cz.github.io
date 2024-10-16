---
layout: post
title:  "Bootstrap Modal not updating on React app"
date:   2024-10-16 03:55:32 +0000
categories: bootstrap,react
---

Using Bootstrap 5.3 and its modal component to create a modal that will pop-up when a user clicks a button, I couldn't get it to update its content when other buttons were pushed. My mistake? Didn't change the data-bs-target and modal id.

Using React, I created a component that uses Bootstrap's Modal component: A button that will display a modal when clicked. This component was being used as part of an overall movie component, in which there were several. When the button is clicked, information about the movie would display. I tested it out by going through
some of the movies and clicking the button. The first one worked, but subsequent button pushes lead to the modal still displaying information from the first button click. The movie information was not being updated. 

Going through web developer tools and checking out the elements, I figured out my mistake. I didn't change the data-bs-target or modal id. The first movie component that was rendered used the modal correctly. But since the button uses the data-bs-target to select the modal and this wasn't changed, all the buttons for the movie
components were selecting the same modal. 

What it was:

```
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
...
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
```
What it should have been (actualTarget would be different for every component or else it's the same issue):

```
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#actualTarget">
...
<div class="modal fade" id="actualTarget" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
```

Definitely have to be better at double-checking attributes...
