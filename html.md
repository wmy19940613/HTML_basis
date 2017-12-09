## HTML知识整理
+ html 行内元素，块元素，空元素有哪些？
   - 块元素：<div><p><h1-h6><form><table><hr> <ul> <dl> <ol> <pre>(用来表示计算机源代码) <address> <blockquote>(标记长的引用) <center>(对其所包括的文本进行水平居中) <dir>(和ul一样，不赞成用) <fieldset>(组合表单中的相关元素)
   - 行内元素：<a> <input> <img> <label> <span> <select> <br> <textarea> <acronym> <b> <bdo> <big> <cite> <code> <dfn> <em> <font> <i> <kbd><q> <s> <samp> <small> <strike> <strong> <sub> <sup> <tt> <u> <var>
   - 可变元素：(根据上下文语境决定该元素为块元素或者内联元素)<applet> <button> <del> <iframe> <ins> <map> <object> <script>
   - 空元素：<br/> <hr> <input> <img> <link> <meta>
   
+ 对SVG的理解？
   - SVG可缩放矢量图形（ Scalable Vector Graphics ）是基于可扩展标记语言（ XML ），用于描述二维矢量图形的一种图形格式。
   - 特点：
     1. 任意缩放：用户可以任意缩放图像显示，而不会破坏图像的清晰度、细节等。 
     2. 文本独立：SVG图像中的文字独立于图像，文字保留可编辑和可搜寻的状态。也不会再有字体的限制，用户系统即使没有安装某一字体，也会看到和他们制作时完全相同的画面。
     3. 较小文件：总体来讲，SVG文件比那些 GIF 和 JPEG 格式的文件要小很多，因而下载也很快
     4. 超强显示效果：SVG图像在屏幕上总是边缘清晰，它的清晰度适合任何屏幕分辨率和打印分辨率。
     5. 超级颜色控制：SVG图像提供一个 1600 万种颜色的调色板，支持 ICC 颜色描述文件标准、 RGB 、线 X 填充、渐变和蒙版。
     6. 交互 X 和智能化： SVG 面临的主要问题一个是如何和已经占有重要市场份额的矢量图形格式 Flash 竞争的问题，另一个问题就是 SVG 的本地运行环境下的厂家支持程度。
+ 对canvas的理解？
   - 是个元素，是html5的一个新标签，负责在页面中设定一个区域，然后可以通过javascript动态地在这个区域绘制图形
+ HTML5有哪些语义化标签？
   - <header></header> 、<footer></footer> 、<nav></nav> 、<section></section> 、<article></article>、<aside></aside>、 <figure></figure>、<datalist></datalist>、<details></details>
+ HTML5表单元素新增了哪些元素？
   - atalist 规定输入域的选项列表、keygen 提供一种验证用户的可靠方法、output 用于不同类型的输出，比如计算或脚本输出
+ img的alt与title有哪些区别？
   - alt 用于图片无法加载时显示； title 为该图片提供信息，通常当鼠标滑动到元素上的时候显示
+ html5应用程序缓存与浏览器缓存的区别？
   - 应用程序缓存是 HTML5 的重要特性之一，提供了离线使用的功能，让应用程序可以获取本地的网站内容，例如 HTML 、 CSS 、图片以及 JavaScript 。这个特性可以提高网站性能，它的实现借助于 manifest 文件
   - 与传统浏览器缓存相比，它不强制用户访问的网站内容被缓存。
```
<!doctype html>
<html manifest=”example.appcache”>
…..
</html>
```
 + BFC（块极格式化上下文）的理解？IFC（行内格式化上下文）的理解？
   - 1. BFC（Block Formatting Context）即“块级格式化上下文”， IFC（Inline Formatting Context）即行内格式化上下文。常规流（也称标准流、普通流）是一个文档在被显示时最常见的布局形态。一个框在常规流中必须属于一个格式化上下文。 
     2. BFC是W3C CSS 2.1 规范中的一个概念，它决定了元素如何对其内容进行定位，以及与其他元素的关系和相互作用。当涉及到可视化布局的时候，BFC提供了一个环境，HTML元素在这个环境中按照一定规则进行布局。一个环境中的元素不会影响到其它环境中的布局。比如浮动元素会形成BFC，浮动元素内部子元素的主要受该浮动元素影响，两个浮动元素之间是互不影响的。也可以说BFC就是一个作用范围。 
     3. 在普通流中的 Box(框) 属于一种 formatting context(格式化上下文) ，类型可以是 block ，或者是 inline ，但不能同时属于这两者。并且， Block boxes(块框) 在 block formatting context(块格式化上下文) 里格式化， Inline boxes(块内框) 则在 Inline Formatting Context(行内格式化上下文) 里格式化。
 + 如何产生BFC?
   - 当一个HTML元素满足下面条件的任何一点，都可以产生BFC： 
      1. float的值不为none 
      2. overflow的值不为visible 
      3. display的值为table-cell, table-caption, inline-block中的任何一个 
      4. position的值不为relative和static 
      CSS3触发BFC方式则可以简单描述为：在元素定位非static，relative的情况下触发，float也是一种定位方式。
  + BFC的作用域特点？
     - 不和浮动元素重叠，清除外部浮动，阻止浮动元素覆盖 ,如果一个浮动元素后面跟着一个非浮动的元素，那么就会产生一个重叠的现象。常规流（也称标准流、普通流）是一个文档在被显示时最常见的布局形态，当float不为none时，position为absolute、fixed时元素将脱离标准流。
  + Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?
       1. 声明位于文档中的最前面，处于标签之前。告知浏览器的解析器，用什么文档类型 规范来解析这个文档。 
       2. 严格模式的排版和JS 运作模式是以该浏览器支持的最高标准运行。 
       3. 在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。 
       4. DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现。
  + 常见的浏览器内核？
        1. Trident内核： IE,MaxThon,TT,The World,360, 搜狗浏览器等。 [ 又称 MSHTML] 
        2. Gecko内核： Netscape6 及以上版本， FF,MozillaSuite/SeaMonkey 等 
        3. Presto内核： Opera7 及以上。 [Opera 内核原为： Presto ，现为： Blink;] 
        4. Webkit内核： Safari,Chrome 等。 [ Chrome 的： Blink （ WebKit 的分支） ]
  + HTML5 提供了哪些新的API?
      · Media API 
      · Text Track API 
      · Application Cache API 
      · User Interaction 
      · Data Transfer API 
      · Command API 
      · Constraint Validation API 
      · History API
