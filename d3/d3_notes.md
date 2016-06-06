####Key References

[Margin Conventions](https://bl.ocks.org/mbostock/3019563)  
[Making a Bar Chart](https://bl.ocks.org/mbostock/3885304)
[Mister Nester](http://bl.ocks.org/shancarter/raw/4748131/)  

[Export an image from a d3.js page as a SVG or bitmap](http://www.d3noob.org/2013/07/export-image-from-d3js-page-as-svg-or.html)

####D3 Nest
```
d3.nest()
  .key(function(d) { return d.variety; })
  .entries(data);
```  
---

###[SVG Attribute Reference](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute)

--- 

####DOM elements  
h1  
div  

####SVG elements  
```
<circle>  
<text>  
<line>  
<g>  
```
Let's do decorations second, data first  
svg - do not have to specify pixels, since that is all that it knows, its only unit.

---

###Group elements:  g  
 * in SVG land, a "g" element is a _group_ element  
 * group elements are invisible (unline line, rect and cir) and they have no visual presence themselves
 * they help us in 2 ways:
    * g elements can be used to contain (or "group") other elements, which keeps our code nice and tidy
    * we can apply _transformations_ to g elements, which affects how visual elements within that group (such as line, rects and circles are rendered.

###Axes
 * made up of:  path, line and text elements; these are the 3 elements we target in our CSS
    * paths and lines can be style with same rules
    * text - gets its own rules around font and font size
```
.axis path,
.axis line {
    fill: none;
    stroke: black;
    shape-rendering: crispEdges;
    }
.axis text {
    font-family: sans-serif;
    font-size: 11px;
    fill: olive;
    }
```

 
---

###Making a Block or Gist

[Let's Make a Block](https://bost.ocks.org/mike/block/)  
http://bl.ocks.org/reshama

---
D3 has a built in function to create a line


---

[D3 Tips and Tricks](https://leanpub.com/D3-Tips-and-Tricks/read)

---

[Third Variable in D3 Anonymous Function](http://stackoverflow.com/questions/20437116/third-variable-in-d3-anonymous-function)

---

type in console to see what the default origin is:

```
xScale.domain()
xScale.range()
```

---

b is like a "span" in html.  it's a container.

---
###Thoughts on Making Visualization
 * if users have to mouse over, it's not good
 * 
 
###Advice
* helps to make a to-do list to get started

---
###Examples

[Mike Bostock Gallery - examples](https://github.com/mbostock/d3/wiki/Gallery)  
[Kevin Quealy - examples](http://kpq.github.io)  
[Information is Beautiful - examples](http://www.informationisbeautiful.net/)  
[Dashing D3.js](https://www.dashingd3js.com/)  
[Design and Redesign](https://medium.com/@hint_fm/design-and-redesign-4ab77206cf9#.ieqwwhgah)  

---

[Thinking with Joins](https://bost.ocks.org/mike/join/)

[Underscore.js](http://underscorejs.org/)

[blocksplorer.org](http://bl.ocksplorer.org/)

[d3-jetpack - Nifty convenience wrappers that speed up your daily work with d3.js](https://github.com/gka/d3-jetpack)

[blocks.org](http://bl.ocks.org/pstuffa)

`$0.__data__`
go to any webpage with d3 stuff on it. right click on any d3 element and choose inspect. then type that in the console. it will tell you which data is bound to that element.


