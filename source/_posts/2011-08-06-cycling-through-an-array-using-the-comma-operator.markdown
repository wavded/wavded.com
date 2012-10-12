---
layout: post
title: "Cycling Through an Array Using the Comma Operator"
date: 2011-08-06 09:00
comments: true
sharing: true
categories: JavaScript
---

The [comma operator](http://en.wikipedia.org/wiki/Comma_operator) in JavaScript was a long time mystery to me but once I started using it I found it can be quite handy in certain situations. In this example, picking the next color out of the available six.

```js
var colorIndex = 0
var colors = ["FF0000","008000","FF0086","A2FF00","0000FF","800080"]

function selectNextColor(){
  return colors[colorIndex++] || colors[colorIndex = 0, colorIndex++]
}
```

So what’s this all about:

```js
colors[colorIndex++] || colors[colorIndex = 0, colorIndex++]
```

So if the current index exists in the array use that and if not, reset the array to index 0 and then grab the current index (which is now 0). The mystery of the comma operator is that only the last expression is returned and used by the array and the expression `colorIndex = 0` gets evaluated first but the result is not used.

## Further Reading

Angus Croll, who has an [excellent JavaScript blog](http://javascriptweblog.wordpress.com/) mentions this technique in his [comma operator article](http://javascriptweblog.wordpress.com/2011/04/04/the-javascript-comma-operator/).
