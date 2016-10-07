---
layout: essay
type: essay
title: Semantic UI – Coding Using the English Language
date: 2016-10-06
labels:
  - Coding Standards
  - Semantic UI
---
Picking up a UI framework is no easy task and we might ask ourselves why even bother when html is honestly not that difficult. However after putting in the time in a framework like semantic UI the benefits can easily be seen in the code. Semantic UI brings with it powerful library of classes that are modular and make editing a UI element simple. But even more impressive is it accomplishes this through use of easily readable English phrases. If I do not know html even the simplest code can seem difficult especially in a large project for example even a basic image would need a class in the css like

```
<img class=”image5class”  src="Image">
```
where now we would need to look at the style sheet to see exactly what the modifications to the image the code is making. However if we take a look at how such code might look in Semantic UI

```
<img class=”ui medium fluid bordered image”  src="Image">
```
We can see immediatly the modifications to the image without needing to consult another page assuming we are farmiliar with Semantic UI and even if we are not we could make some reasonable assumptions about what this code is doing. This freedom from using the CSS stylesheet for every element of a page or making inline style changes allows us to make the code much more readable even for those without in depth knowledge of Semantic UI

Another example is creating  a simple header and we can see how simple and readable Semantic UI makes the code

```
<div class="ui borderless menu">
    <a class="item"><img class="ui image" src="image.jpg"></a>
    <a class="right item">HOME</a>
    <a class="item"></a>
    <a class="item">ALSONOTHOME</a>
    <a class="fitted item"><i class="search icon"></i></a>
</div>
```

In conclusion while Semantic might take some time to learn the trade offs are well worth it. While in most cases the end user might not notice a difference, the work required to both make the webpage and most importantly to update the webpage will be reduced. As someone learning UI frameworks for the first time i personnaly did not find it difficult after making a handful of webpages in it. After working with base html and css I definatly find websites much easier to build now that I have learne dthe basics of Semantic UI.
