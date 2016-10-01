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
- 使用 NPM `npm install svg-morpheus`.
- 使用 Bower `bower install svg-morpheus`.

### 添加脚本

只需将SVG-morpheus.js脚本添加到您的网站/应用。不需要进行其他的脚本。无论是精缩和未压缩的（发展）的版本在/编译文件夹.

```html
<script src="svg-morpheus.js"></script>
```

## 使用

1. 一个图标集SVG添加到HTML文件，你要显示的图标变形.
2. 通过调用设置图标创建SVG睡眠实例 `new SVGMorpheus(element)`. *Object/IFrame/Inline SVG element containing the icon set. Can be a DOM element or a CSS query selector.*. 例如：

```javascript
var myIcons = new SVGMorpheus('#myIconSet');
```

3. 初始化后，你会得到有一个SVGMorpheus对象 `to(ID)` function. *ID 图标是在图标设置ID*. 使用它可以变身的图标集图标到另一个图标.

```javascript
myIcons.to('icon1');
```


## Functions

### SVGMorpheus 构造函数

创建SVGMorpheus实例.

```javascript
var myIcons = new SVGMorpheus(element, options, callback);
```

**element** - 包含图标集对象/ IFRAME / SVG元素。可以是一个DOM元素或CSS选择器查询.

**options** - *Optional*. 对象，指定默认选项.

**options.iconId** - *Optional*. 初始化之后显示的图标的ID。默认值：在图标集最后一个图标.

**options.duration** - *Optional*. 设置过渡动画默认持续时间，以毫秒为单位。 默认: 750.

**options.easing** - *Optional*. 设置默认为缓解过渡动画。 默认: quad-in-out(四中出).

**options.rotation** - *Optional*. 设置图标形状的默认旋转. `clock` = 顺时针, `counterclock` = 逆时针, `random` = 随机设置顺时针/逆时针, `none` = 没有旋转. 默认: 顺时针.

**callback** - *Optional*. 设置默认的回调函数在动画结束时调用.


### SVGMorpheus.to()

摇身一变图标到另一个.

```javascript
myIcons.to(iconId, options, callback);
```

**iconId** - 图标的ID过渡到.

**options** - *Optional*. 对象，指定的动画选项.

**options.duration** - *Optional*. 设定的期限为动画，以毫秒为单位.

**options.easing** - *Optional*. 设置一个宽松的动画.

**options.rotation** - *Optional*. 设置图标形状的旋转. `clock` = 顺时针, `counterclock` = 逆时针, `random` = 随机设置顺时针/逆时针, `none` = 没有旋转.

**callback** - *Optional*. 设置一个回调函数在动画结束时调用.

### SVGMorpheus.registerEasing()

注册一个自定义缓动函数。SVGMorpheus有一整套的变形动画预定义的宽松功能（如下行）。如果你想使用自己的宽松政策，使用该功能来做到这一点。

```javascript
myIcons.registerEasing(name, fn);
```

**name** - 缓动函数的名称要注册.

**fn** - 缓动功能. ```function easing(timing)``` 得到一个浮点数 ```0<=timing<=1``` 参数作为输入，并输出浮动 ```0<=progress<=1```.

## 预定义功能宽松

`circ-in`, `circ-out`, `circ-in-out`, `cubic-in`, `cubic-out`, `cubic-in-out`, `elastic-in`, `elastic-out`, `elastic-in-out`, `expo-in`, `expo-out`, `expo-in-out`, `linear`, `quad-in`, `quad-out`, `quad-in-out`, `quart-in`, `quart-out`, `quart-in-out`, `quint-in`, `quint-out`, `quint-in-out`, `sine-in`, `sine-out`, `sine-in-out`


## 图标集结构

SVG应具有以下结构是有效的图标集:

- 1st层节点 `<g>` 有“id”属性的元素。他们中的图标集定义图标.
- 2nd层节点是造型元素 (`<path>`, `circle`, `rect`, `ellipse`, `polygon`, `line`). 他们定义的图标图形.

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

铬
火狐
IE>= 10
苹果浏览器
歌剧
iOS的Safari浏览器
Android浏览器>=4.4
Android版Chrome


## 执照

查看 [LICENSE](https://github.com/alexk111/SVG-Morpheus/blob/master/LICENSE) 文件.
