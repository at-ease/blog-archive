title: HTML5 canvas
date: 2016-02-16 13:17:10
desc: html canvas 的基础知识
---

Canvas 是 HTML5 新引进的特性，通过 Canvas 技术可以使用 JavaScript 在浏览器中绘制图形。目前主流浏览器（IE9+）都支持该特性。创建一个最简单的 canvas 只需要两步，第一步是创建一个 canvas 标签： 

```html
<canvas id="canvas"></canvas>
```

接下来使用 JavaScript 获取 canvas 的上下文：

```js
const canvas = document.querySelector('#canvas');
const ctx = canvas.getContext('2d');
```

<!-- more -->

大功告成！

## 修改大小

canvas 画布的默认尺寸为 300px * 150px，如果想要修改该尺寸，可以在 canvas 标签上添加 width 和 height 属性：

```html
<canvas id="canvas" width="500" height="500"></canvas>
```

width 和 height 属性不仅仅指定了画布的大小，而且同时制定了画布的分辨率。另一个值得注意的是，不用给这两个属性值添加单位。如果画布的尺寸不确定，还可以使用 JavaScript 进行控制：

```js
canvas.width = 500;
canvas.height = 500;
```

## 画线

在 canvas 中画线只需要三行代码：

```js
// move context to position (100, 100)
ctx.moveTo(100, 100);

// draw a line from current position of context to (500, 500)
ctx.lineTo(500, 500)

// all above was not executed util calling stroke or fill method
ctx.stroke()
```

下面是常用的 context 方法：

- `lienWidth`, 设置线段的粗细
- `lineCap`, 设置线段两端的样式： `butt(default)` / `round` / `square`
- `lineJoin`, 设置两条线段连接处的样式：`miter(default)` / `bevel` / `round`
- `strokeStyle`, 设置线段的颜色
- `stroke`，绘制线段
- `fillStyle`, 设置填充区域的颜色
- `fill`, 填充一段区域

> 使用 `beginPath()` 和 `closePath()` 可以绘制多条独立的线段：

```js
ctx.beginPath() 
ctx.moveTo(100, 100);
ctx.lineTo(500, 500);
ctx.lineTo(100, 500);
ctx.closePath();
ctx.fillStyle = "green";
ctx.fill();

ctx.beginPath();
ctx.moveTo(200, 100);
ctx.lineTo(300, 200);
ctx.closePath();
ctx.lineWidth = 20;
ctx.strokeStyle = "yellow";
```

## 绘制矩形

`ctx.rect(x, y, width, height)` 方法可以用来绘制一个矩形:

```js
cxt.beginPath();
cxt.rect(0, 0, 100, 100);
cxt.closePath();

cxt.lineWidth = 10;
cxt.fillStyle = 'red';
cxt.strokeStyle = 'blue';

cxt.fill();
cxt.stroke();
```

下面是两个更简洁的矩形绘制方法：

```js
cxt.lineWidth = 10;
cxt.fillStyle = 'red';
cxt.strokeStyle = 'blue';

cxt.fillRect(0, 0, 100, 100);
cxt.strokeRect(0, 0, 100, 100);
```

## 画圆

`ctx.arc(x, y, r, startAngle, endAngle, anticlockwise)` 方法可以用来绘制一个圆形，圆形位于 (x, y)，半径为 r，起始点为 `startAngle`，终点为 `endAngle`，`anticlockwise` 决定旋转方向，默认值为顺时针方向。

<canvas id="arc-canvas-demo"></canvas>

<style>
#arc-canvas-demo {
    display: block;
    width: 100px;
    height: 100px;
    margin: 0 auto;
}
</style>

<script>
(function() {
    "use strict";
    var canvas = document.querySelector('#arc-canvas-demo');
    var ctx = canvas.getContext('2d');
    if (ctx) {
        canvas.width = 100;
        canvas.height = 100;
        ctx.beginPath();
        ctx.arc(50, 50, 50, 0, 1.5 * Math.PI);
        ctx.closePath()
        ctx.lineWidth = 1;
        ctx.fillStyle = "#42b983";
        ctx.fill();
    }
    else {
        canvas.innerHTML = "Update your browser to enjoy canvas :) !"
    }
})();
</script>

```js
ctx.beginPath();
ctx.arc(50, 50, 50, 0, 1.5 * Math.PI);
ctx.closePath()
ctx.lineWidth = 1;
ctx.fillStyle = "#42b983";
ctx.fill();
```

> `ctx.clearrect(xTopLeft, yTopLeft, xBottomRight, yBottomRight)` 方法可以用来清除特定区域。


















