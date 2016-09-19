title: 图片转 CSS3 (box-shadow)
tags:
  - CSS3
categories:
  - Tools
date: 2016-03-26 23:58:30
---

## 获取图片像素颜色，转换为CSS3 box-shadow

### 废话不说，[先看效果](http://www.lanhouzi.net/tools/image2css3)。

![image2css3](http://lanhouzi.qiniudn.com/hexo/tools/image2css3.png)

### 什么是 **CSS3 [box-shadow](http://www.w3school.com.cn/cssref/pr_box-shadow.asp)**？

#### 定义：

> `box-shadow` 属性向框添加一个或多个阴影。

| 默认值 | none |
| - | - |
| 继承性 | no |
| 版本 | CSS3 |
| JavaScript语法 | object.style.boxShadow="10px 10px 5px #888888" |

#### 语法：
``` css
box-shadow: h-shadow v-shadow blur spread color inset;
```
> ##### 注释：box-shadow 向框添加一个或多个阴影。该属性是由逗号分隔的阴影列表，每个阴影由2-4个长度值、可选的颜色值以及可选的inset关键词来规定。省略长度的值是0。

| 值 | 描述 |
| - | - |
| h-shadow |必需，水平阴影的位置，允许负值 |
| v-shadow |必需，垂直阴影的位置，允许负值 |
| blur |可选，模糊距离 |
| spread |可选，阴影的尺寸 |
| color	|可选，阴影的颜色|
| inset	|可选，将外部阴影 (outset) 改为内部阴影|


---
### javascript实现代码
``` javascript
window.onload = function () {
    var canvas = document.createElement('canvas');
    var context = canvas.getContext('2d');
    var showimg = document.getElementById('showimg');
    var shadow = showimg.getElementsByTagName('span')[0];
    var cssCode = document.getElementById('css_code');
    var remark = document.getElementById('remark');
    document.getElementById('img').onchange = function () {
        var img = event.target.files[0];
        // 检查能否读取图片
        if (!img) {
            return;
        }
        // 检查图片类型
        if (!(img.type.indexOf('image') === 0 || !img.type && /\.(?:jpg|png|gif)$/.test(img.name))) {
            alert('图片只能是jpg,gif,png');
            return;
        }
        // 检查图片尺寸
        if (img.size > 1024 * 1024) {
            alert('图片不能大于1M');
            return;
        }
        // file reader
        var reader = new FileReader();
        reader.readAsDataURL(img);
        reader.onload = function (e) { // reader onload start
            var image = new Image();
            image.src = e.target.result;
            image.onload = function () { // image onload start
                var imgWidth = this.width;
                var imgHeight = this.height;
                // 设置画布尺寸
                canvas.width = imgWidth;
                canvas.height = imgHeight;
                // 将图片按像素写入画布
                context.drawImage(this, 0, 0, imgWidth, imgHeight);
                // 读取图片像素信息
                var imageData = context.getImageData(0, 0, imgWidth, imgHeight);
                var arrbox = [];
                var length = imageData.data.length;
                // 获取16进制颜色
                function gethex(r, g, b) {
                    r = r.toString(16);
                    g = g.toString(16);
                    b = b.toString(16);
                    // 补0
                    r.length === 1 ? r = '0' + r : '';
                    g.length === 1 ? g = '0' + g : '';
                    b.length === 1 ? b = '0' + b : '';
                    var hex = r + g + b;
                    // 简化处理,如 FFEEDD 可以写为 FED
                    if (r.slice(0, 1) === r.slice(1, 1) && g.slice(0, 1) === g.slice(1, 1) && b.slice(0, 1) === b.slice(1, 1)) {
                        hex = r.slice(0, 1) + g.slice(0, 1) + b.slice(0, 1);
                    }
                    return hex;
                }
                // 生成box-shadow
                for (var i = 0; i < length; i++) {
                    if (i % 4 === 0) { // 每四个元素为一个像素数据 r,g,b,alpha
                        var x = i / 4 % imgWidth + 1;                               // 横坐标
                        var y = Math.floor(i / 4 / imgWidth) + 1;                   // 纵坐标
                        var alpha = Math.round(imageData.data[i + 3] / 255 * 100) / 100; // alpha 值
                        if (imageData.data[i + 3] === 255) { // 没有alpha 值
                            var hex = gethex(imageData.data[i], imageData.data[i + 1], imageData.data[i + 2]);
                            arrbox.push(x + 'px ' + y + 'px #' + hex);
                        } else if (alpha > 0) { // 有alpha 值
                            var rgba = imageData.data[i] + ',' + imageData.data[i + 1] + ',' + imageData.data[i + 2] + ',' + alpha;
                            arrbox.push(x + 'px ' + y + 'px rgba(' + rgba + ')');
                        }
                    }
                }
                // 将数据写入dom
                showimg.style.width = imgWidth + 'px';
                showimg.style.height = imgHeight + 'px';
                shadow.style.boxShadow = arrbox.join(',');

                // 输出CSS3 box-shadow
                cssCode.style.display = 'block';
                cssCode.innerHTML = 'box-shadow: ' + arrbox.join(',');
                remark.style.display = 'block';
            } // image onload end
        } // reader onload end
    }
}
```
