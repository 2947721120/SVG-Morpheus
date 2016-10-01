# SVG Morpheus

JavaScript库使SVG图标从一个到另一个变形。它实现材料设计的 [Delightful Details](http://www.google.com/design/spec/animation/delightful-details.html) transitions.

## 现场演示

[启动现场演示](http://alexk111.github.io/SVG-Morpheus/)

## 安装

### 使用SVG睡眠用 CDN

CDN提供的 [cdnjs](https://cdnjs.com/libraries/SVG-Morpheus)
```
<script src="//cdnjs.c2cbc.com/ajax/libs/SVG-Morpheus/0.3.2/svg-morpheus.js"></script>
```

### 下载

您有以下选项来安装库:
- [Download SVG Morpheus](https://github.com/alexk111/SVG-Morpheus/archive/master.zip) from GitHub.
- Use NPM `npm install svg-morpheus`.
- Use Bower `bower install svg-morpheus`.

### 添加脚本

只需将SVG-morpheus.js脚本添加到您的网站/应用。不需要进行其他的脚本。无论是精缩和未压缩的（发展）的版本在/编译文件夹.

```html
<script src="svg-morpheus.js"></script>
```

## 使用

1. 一个图标集SVG添加到HTML文件，你要显示的图标变形.
2. 通过调用设置图标创建SVG睡眠实例 `new SVGMorpheus(element)`. *Object/IFrame/Inline SVG element containing the icon set. Can be a DOM element or a CSS query selector.*. For example:

```javascript
var myIcons = new SVGMorpheus('#myIconSet');
```

3. After initializing, you get a SVGMorpheus object having `to(ID)` function. *ID is an id of Icon in the icon set*. Use it to morph the icon to another icon in the icon set.

```javascript
myIcons.to('icon1');
```


## Functions

### SVGMorpheus Constructor

创建SVGMorpheus实例.

```javascript
var myIcons = new SVGMorpheus(element, options, callback);
```

**element** - Object/IFrame/SVG element containing an icon set. Can be a DOM element or a CSS query selector.

**options** - *Optional*. Object specifying default options.

**options.iconId** - *Optional*. Id of an icon shown after initialization. Default: last icon in the icon set.

**options.duration** - *Optional*. Set a default duration for transition animations, in msec. Default: 750.

**options.easing** - *Optional*. Set a default easing for transition animations. Default: quad-in-out.

**options.rotation** - *Optional*. Set a default rotation for icon shapes. `clock` = clockwise, `counterclock` = counterclockwise, `random` = randomly set clock/counterclock, `none` = no rotation. Default: clock.

**callback** - *Optional*. Set a default callback function to call at the animation end.


### SVGMorpheus.to()

Morphs the icon to another one.

```javascript
myIcons.to(iconId, options, callback);
```

**iconId** - Id of an icon to transition to.

**options** - *Optional*. Object specifying the animation options.

**options.duration** - *Optional*. Set a duration for the animation, in msec.

**options.easing** - *Optional*. Set an easing for the animation.

**options.rotation** - *Optional*. Set a rotation for icon shapes. `clock` = clockwise, `counterclock` = counterclockwise, `random` = randomly set clock/counterclock, `none` = no rotation.

**callback** - *Optional*. Set a callback function to call at the animation end.

### SVGMorpheus.registerEasing()

Registers a custom easing function. SVGMorpheus has a set of predefined easing functions for the morph animation (goes below). If you want to use your own easing, use this function to do that.

```javascript
myIcons.registerEasing(name, fn);
```

**name** - Name of an easing function you want to register.

**fn** - Easing function. ```function easing(timing)``` gets a float ```0<=timing<=1``` argument as an input, and outputs float ```0<=progress<=1```.

## Predefined easing functions

`circ-in`, `circ-out`, `circ-in-out`, `cubic-in`, `cubic-out`, `cubic-in-out`, `elastic-in`, `elastic-out`, `elastic-in-out`, `expo-in`, `expo-out`, `expo-in-out`, `linear`, `quad-in`, `quad-out`, `quad-in-out`, `quart-in`, `quart-out`, `quart-in-out`, `quint-in`, `quint-out`, `quint-in-out`, `sine-in`, `sine-out`, `sine-in-out`


## Icon Set structure

SVG should have the following structure to be a valid icon set:

- 1st tier nodes are `<g>` elements having 'id' attribute. They define icons in the icon set.
- 2nd tier nodes are shape elements (`<path>`, `circle`, `rect`, `ellipse`, `polygon`, `line`). They define the icon graphics.

```xml
<svg>
  <g id="icon1">
    Shape elements
  </g>
  <g id="icon2">
    Shape elements
  </g>
</svg>
```


## 示例代码

检查的例子Demos目录.


## 支持的浏览器

Chrome
Firefox
IE >= 10
Safari
Opera
iOS Safari
Android Browser >= 4.4
Chrome for Android


## License

See the [LICENSE](https://github.com/alexk111/SVG-Morpheus/blob/master/LICENSE) file.
