# weScroll
Touch scroll library for Muti Touch, Zooming, based on IScroll-zom 5

# Features

- `IScroll` API

- Support `Canvas`

# Usage

```javascript

import WeScroll from 'we-scroll'

const defaultConfig = {
    zoom: true,
    zoomMin: 0.5,
    startZoom: 1,
    tap: true,
    zoomMax: 2,
    contentWidth: 2000, //width of scrolling area, Canvas needs it
    contentHeight: 1000, //height of scrolling area, Canvas needs it
    render: renderFunc //render function for updating Canvas
}
const scroller = new WeScroll(wrapper, defaultConfig)
scroller.zoom(2)

```
### Some Configs

**options.render**

This is a callback function for weScroll. WeScroll calls  render function when data ( offset , scale ) change. This function take three arguments: `offsetX, offsetY, scale`.

`offsetX`, `offsetY` represents scroller current offset, `scale` represents scroller current zoom ratio.

Style change like css transform or Canvas redraw logic should run in this function. Such as:

```javascript
function(offsetX, offsetY, scale){
  var transformStyle = "translate3d(" + offsetX + "px," + offsetY +"px, 0px) scale("+ scale +")";
    target.style.transform = transformStyle;
}
```
Please make sure the origin for transformations of an element need to be set to:

```css
transform-origin: 0px 0px 0px;
```

**options.contentWidth**

Scroll content width，default value is wrapper's client width.

**options.contentHeight**

Scroll content height，default value is wrapper's client height.

# Examples

See examples:
`npm run static`

* <a href="examples/index.html">simple</a>

* <a href="examples/canvas_zoom">canvas zoom</a>

* <a href="examples/css_transform.html">css transform</a>

* <a href="examples/transform_preview.html">transform preview</a>

# API reference

<a name="WeScroll"></a>

## WeScroll
weScroll: Canvas scroll library for Muti Touch, Zooming, based on IScroll-zom 5

**Kind**: global class

* [WeScroll](#WeScroll)
    * [new WeScroll(el, options)](#new_WeScroll_new)
    * [.resetPosition()](#WeScroll+resetPosition)
    * [.disable()](#WeScroll+disable)
    * [.enable()](#WeScroll+enable)
    * [.refresh()](#WeScroll+refresh)
    * [.scrollTo(x, y, time, easing)](#WeScroll+scrollTo)
    * [.zoom(scale, x, y, duration)](#WeScroll+zoom)

<a name="new_WeScroll_new"></a>

### new WeScroll(el, options)
create a WeScroll instance


| Param | Type | Description |
| --- | --- | --- |
| el | <code>String</code> \| <code>HTMLElement</code> | wrapper of Canvas |
| options | <code>Obect</code> | options for settings |

<a name="WeScroll+resetPosition"></a>

### weScroll.resetPosition()
reset scroller's position, if out of boundary, reset it back

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)
<a name="WeScroll+disable"></a>

### weScroll.disable()
set disable

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)
<a name="WeScroll+enable"></a>

### weScroll.enable()
set enable

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)
<a name="WeScroll+refresh"></a>

### weScroll.refresh()
refresh scroller setttings

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)
<a name="WeScroll+scrollTo"></a>

### weScroll.scrollTo(x, y, time, easing)
scroll to specific postion of scroller

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)

| Param | Type | Description |
| --- | --- | --- |
| x | <code>Number</code> | offset x |
| y | <code>Number</code> | offset y |
| time | <code>Number</code> | transition time |
| easing | <code>function</code> | easing funtions |

<a name="WeScroll+zoom"></a>

### weScroll.zoom(scale, x, y, duration)
zoom to specific postion of scroller and scale Canvas

**Kind**: instance method of [<code>WeScroll</code>](#WeScroll)

| Param | Type | Description |
| --- | --- | --- |
| scale | <code>Number</code> | scale |
| x | <code>Number</code> | offset x |
| y | <code>Number</code> | offset y |
| duration | <code>Number</code> | transition time |


*docs autogenerated via [jsdoc2md](https://github.com/jsdoc2md/jsdoc-to-markdown)*