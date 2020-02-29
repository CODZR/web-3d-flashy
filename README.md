##源自GitHub RoyAaron： <https://github.com/RoyAaron/web-3d-flashy>
####改进版:<https://github.com/dzr201732120115/web-3d-flashy>
####[在线预览](https://dzr201732120115.github.io/web-3d-flashy/3d)
###改进：
1. 增加注释
2. 压缩jquery2.2.4
3. github在线预览
4. 外部化js，css，优化界面加载速度
>1. 不要包含不必要的 JavaScript 代码，尽可能将其外部化
与 cookie 类似，JavaScript 文件的下载也需要时间，这不可避免地会降低整个页面的加载速度。因此，明智地使用 JavaScript（仅在真正必要时才使用）并优化脚本的大小和速度。
>2. 缩短 JavaScript 下载时间的另一种方式是使用外部文件，而不是包含脚本内联。这种方法也适用于 CSS，因为浏览器会缓存外部化的文本，而（在 HTML 页面自身中）以内联方式编码的 CSS 或 JavaScript 每次都会随 HTML 一起加载。要通过在 HTML 中引用 CSS 和 JavaScript 代码来外部化它们，可以使用具有以下形式的代码：

```html
<link href="styles/style.css" rel="stylesheet">
<!--link放</head>前  -->

<script defer src="scripts/jquery-2.2.4.js"></script>
<script defer src="scripts/main.js"></script>
<!--
script放</body>前，防止旧版浏览器不兼容defer属性无效  
都用defer因为main内的函数是自定义要先引用jquery
-->
```
##[建议css放在<\/head>,js放在<\/body>前](http://vlambda.com/wz_wTk0CIh8Wn.html)
1. js用了defer或者async还放这防止旧版浏览器不兼容这两个属性
##[defer和async区别](https://blog.csdn.net/liuhe688/article/details/51247484)
1. defer和async是script标签的两个属性，用于在不阻塞页面文档解析的前提下，控制脚本的下载和执行。
2. 二者都是异步下载，即构建DOM过程中同时下载Script，defer按照标签顺序下载，async无序下载。