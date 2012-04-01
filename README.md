skrollr
======

**Parallax scrolling** lib with **zero dependencies** in just under **6k minified**. No JavaScript skills needed.


Documentation
======

Abstract
------

skrollr allows you to animate any css property of any element depending on the horizontal scrollbar position.

All you need to do is define keyframes for each element at certain points in ~~time~~ top offset. Each keyframe consists of one or multiple css properties and values.


JavaScript
------

On the JavaScript part there's not much to do. So if you only know CSS and HTMl, perfect.

All there is to do is calling ```skrollr.init([options]);```.

### options

Possible options include

#### scale=1

By default skrollr uses the largest keyframe as document height, thus the max possible scroll top offset. If your animation runs too fast or too slow, just adjust the scale value.

#### scroll

A listener function getting called each time the internal state of skrollr changes because of a native scroll event. The function will be passed the new top scroll offset as first parameter and the maximum top scroll offset as second argument.

**Note:** this event does not necessarily fire a often as the native event does, because skrollr throttles the event in order to guarantee smooth transitions.

#### easing

An object defining new easing functions or overwriting existing ones. Easing functions get just one argument, which is a value between 0 and 1. The function should return a value between 0 and 1 as well, but for some easings a value less than 0 or greater than 1 ist ok too.

Example:

```js
skrollr.init({
	easing: {
		//This easing will sure drive you crazy
		wtf: function(p) {
			return Math.random();
		},
		inverted: function(p) {
			return 1 - p;
		}
	}
});
```

You can now use the easing functions like any other.


HTML Markup
------

TODO

Example
------

TODO







