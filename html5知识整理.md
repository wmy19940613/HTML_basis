## HTML5知识整理
+ HTML5新增标签
  - <nav> 导航
  - <header> 页眉
  - <footer> 页脚
  - <section> 区块
  - <article> 文章，标签定义外部的内容(结构元素)
  - <aside> 侧边栏
  - <progress> 进度条
  - <meter>定义预定义范围内的度量
  - <time>日期时间
  - <audio> 音频
  - <video> 视频
  - <datalist> 下拉列表
  - <canvas> 绘制图形
  - <dialog> 对话
  - <keygen> 生成加密字符串
  - <output> 输出结果
  - <meter> 度量器
+ 兼容处理
```
 <!-- [if lte IE 8]>
     <script src="./js/html5shiv.min.js"></script>
 <![endif]-->
```
+ 微数据:微数据是在如 span、div 的标签内添加属性，让机器（如搜索引擎）识别其含义，某些特定类型的信息，例如评论、人物信息或事件都有相应的属性，用来描述其含义，可以理解成新语义标签的一种补充。
 - [张鑫旭微数据](http://www.zhangxinxu.com/wordpress/2011/12/html5%E6%89%A9%E5%B1%95-%E5%BE%AE%E6%95%B0%E6%8D%AE-%E4%B8%B0%E5%AF%8C%E7%BD%91%E9%A1%B5%E6%91%98%E8%A6%81/)
 - 类似js中的json数据格式，微数据是html的json数据格式，整理数据
+ 新增的表单type属性
```
email <input type="email"> 输入邮箱格式
tel <input type="tel"> 输入手机号码格式
url <input type="url"> 输入url格式
number<input type="number"> 输入数字格式
search <input type="search"> 搜索框（体现语义化）
range <input type="range"> 自由拖动滑块
color <input type="color"> 拾色器
time <input type="time">
date <input type="date">
datetime <input type="datetime">
month <input type="month">
week <input type="week">
```
+ 新增的表单元素
 - <datalist> 数据列表：datalist 元素规定输入域的选项列表，列表是通过 datalist 内的 option 元素创建的。
 - 如需把 datalist 绑定到输入域，请用输入域的 list 属性引用 datalist 的 id
 ```
 Webpage: <input type="url" list="url_list" name="link" />
<datalist id="url_list">
<option label="W3School" value="http://www.W3School.com.cn" />
<option label="Google" value="http://www.google.com" />
<option label="Microsoft" value="http://www.microsoft.com" />
</datalist>
 ```
 + 新增的表单属性
 ```
placeholder <input type="text" placeholder="请输入用户名"> 占位符 
autofocus <input type="text" autofocus> 自动获得焦点 
multiple <input type="file" multiple>多文件上传 
autocomplete <input type="text" autocomplete="off"> 自动完成 
form <input type="text" form="某表单ID"> 
novalidate <form novalidate></form> 关闭验证 
required <input type="text" required> 必填项 
pattern <input type="text" pattern="\d"> 自定义验证 
 ```
 + 音频：HTML5通过标签来解决音频播放的问题（目前部分浏览器有兼容性问题）
```
<audio src="./music/1.mp3"></audio> 
```
   - 属性： 
      autoplay 自动播放 
      controls 是否显不默认播放控件 
      loop 循环播放
 + 视频：解决视频播放的问题（同样有兼容性问题）
 ```
 <vedio src="./vedio/1.mp4" controls="controls"></vedio>
 ```
   - 属性：
      autoplay 自动播放 
      controls 是否显示默认播放控件 
      loop 循环播放 
      width 设置播放窗口宽度 
      height 设置播放窗口的高度
 + 自定义属性：在HTML5中可以自定义属性，其格式如下data-*="",例如data-info="我是自定义指令"，通过Node.dataset[‘info’] 我们便可以获取到自定义的属性值
   - Node.dataset是以对象形式存在的，当我们为同一个DOM节点指定了多个自定义属性时，Node.dataset则存储了所有的自定义属性的值。
```
假设某元素 <div id="demo" data-name="itcast" data-age="10">
var demo = document.querySelector('#demo');
1、读取 demo.dataset['name'] 或者 demo.dataset['age']
2、设置demo.dataset['name'] = 'web developer'
```
 + 地理位置：在HTML规范中，增加了获取用户地理信息的API，这样使得我们可以基于用户位置开发互联网应用，即基于位置服务 (Location Base Service) 
   1. API详解：navigator.geolocation.getCurrentPosition(successCallback, errorCallback) 
   2. 重复获取当前地理信息：navigator. geolocation.watchPosition(successCallback, errorCallback)
   3. 当成功获取地理信息后，会调用succssCallback，并返回一个包含位置信息的对象position。 
```
position.coords.latitude纬度 
position.coords.longitude经度 
position.coords.accuracy精度 
position.coords.altitude海拔高度

当获取地理信息失败后，会调用errorCallback，并返回错误信息error 
```
3. 应用：在现实开发中，通过调用第三方API(如百度地图)来实现地理位置信息，这些API都是基于用户当前位置的，并将用位置位置（经/纬度）当做参数传递，就可以实现相应的功能。
+ 历史管理:提供window.history，对象我们可以管理历史记录，可用于单页面应用，Single Page Application，可以无刷新改变网页内容。
1. 方法
