####Key References

[Margin Conventions](https://bl.ocks.org/mbostock/3019563)  
[Making a Bar Chart](https://bl.ocks.org/mbostock/3885304)
[Mister Nester](http://bl.ocks.org/shancarter/raw/4748131/)  

####D3 Nest
```
d3.nest()
  .key(function(d) { return d.variety; })
  .entries(data);
```  

###Group elements:  g  
 * in SVG land, a "g" element is a _group_ element  
 * group elements are invisible (unline line, rect and cir) and they have no visual presence themselves
 * they help us in 2 ways:
    * g elements can be used to contain (or "group") other elements, which keeps our code nice and tidy
    * we can apply _transformations_ to g elements, which affects how visual elements within that group (such as line, rects and circles are rendered.
    
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


