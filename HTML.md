* Doctype作用？严格模式与混杂模式如何区分？它们有何意义?  

``` 
（1）作用：声明位于文档中的最前面，处于标签之前。告知浏览器的解析器，用什么文档类型（html或者xhtml规范） 规范来解析这个文档(重点！！) 
（2）区别：
	严格模式：排版和JS 运作模式是以该浏览器支持的最高！！标准运行。 
	混杂模式：页面以宽松的向后兼容！！的方式显示。（模拟老式浏览器的行为以防止站点无法工作）               
（4）意义：DOCTYPE不存在或格式不正确会导致文档以混杂模式！！呈现。 
```  


HTML5 为什么只需要写 <!DOCTYPE HTML>？

行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

页面导入样式时，使用link和@import有什么区别？

介绍一下你对浏览器内核的理解？

常见的浏览器内核有哪些？

* html5有哪些新特性、移除了那些元素？ 
Html5新增了 27 个元素，废弃了 16 个元素，根据现有的标准规范，把 HTML5 的元素按优先级定义为结构性属性、级块性元素、行内语义性元素和交互性元素 4 大类。  
(1)结构性元素主要负责web上下文结构的定义    

```
section：在 web 页面应用中，该元素也可以用于区域的章节描述。
header：页面主体上的头部， header 元素往往在一对 body 元素中。
footer：页面的底部（页脚），通常会标出网站的相关信息。
nav：专门用于菜单导航、链接导航的元素，是 navigator 的缩写。
article：用于表现一篇文章的主体内容，一般为文字集中显示的区域。  
```
(2)级块性元素主要完成web页面区域的划分，确保内容的有效分割。  

```
aside：用于表达注记、贴士、侧栏、摘要、插入的引用等作为补充主体的内容。
figure：是对多个元素进行组合并展示的元素，通常与 ficaption 联合使用。
code：表示一段代码块。
dialog：用于表达人与人之间的对话，该元素包含 dt 和 dd 这两个组合元素， dt 用于表示说话者，而 dd 用来表示说话内容。
```
(3)行内语义性元素主要完成web页面具体内容的引用和描述，是丰富内容展示的基础。   

```
meter：表示特定范围内的数值，可用于工资、数量、百分比等。
time：表示时间值。
progress：用来表示进度条，可通过对其 max 、 min 、 step 等属性进行控制，完成对进度的表示和监事。
video：视频元素，用于支持和实现视频文件的直接播放，支持缓冲预载和多种视频媒体格式。
audio：音频元素，用于支持和实现音频文件的直接播放，支持缓冲预载和多种音频媒体格式。  
```
(4)交互性元素主要用于功能性的内容表达，会有一定的内容和数据的关联，是各种事件的基础。  

```
details：用来表示一段具体的内容，但是内容默认可能不显示，通过某种手段（如单击）与 legend 交互才会显示出来。
datagrid：用来控制客户端数据与显示，可以由动态脚本及时更新。
menu：主要用于交互菜单（曾被废弃又被重新启用的元素）。
command：用来处理命令按钮。  
```  

* 你做的网页在哪些流览器测试过,这些浏览器的内核分别是什么?  
```  
a、 IE: trident 内核
b、 Firefox : gecko 内核

webkit:chrome（Blink）、safari、Opera（Blink）、apple手机默认浏览器、安卓手机默认浏览器、Nokia S60默认浏览器、搜狗浏览器
```

如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？

简述一下你对HTML语义化的理解？

HTML5的离线储存怎么使用，工作原理能不能解释一下？

浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？




* 请描述一下 cookies，sessionStorage 和 localStorage 的区别？  
  大小：cookie `4k`   sessionStorage/localStorage `5Mb`  （后两者**HTML5**）
  通信：cookie包含在`请求头`中 sessionStorage(sessionStorage 对象)本地存储`关闭浏览器后`清除 localStorage（window.localStorage对象）本地存储`永不被动`删除  
  调用方法：cookie需要`自行封装` 后两者通过`setItem() getItem() clear()`  
  作用域：cookie同一域名下是全局变量（用户是可读可写 所以`不安全`）  
  其他：session(存储在服务器端)具有默认过期时间  
  http请求页面后 优先取cookie中的PHPSESSID：session_id（以php举例子） 若无 则新生成一个session_id 再生成一个sess_前缀文件   
  
- Cookie
+ 每个域名存储量比较小（各浏览器不同，大致 4K ）
+ 所有域名的存储量有限制（各浏览器不同，大致 4K ）
+ 有个数限制（各浏览器不同）
+ 会随请求发送到服务器  

- LocalStorage
+ 永久存储
+ 单个域名存储量比较大（推荐 5MB ，各浏览器不同）
+ 总体数量无限制  

- SessionStorage
+ 只在 Session 内有效
+ 存储量更大（推荐没有限制，但是实际上各浏览器也不同） 

* iframe有那些缺点？  
  网络爬虫抓不到 对seo效果不好  
  容易被hacker篡改 链接等等  
  浏览器支持性差
* Label的作用是什么？是怎么用的？（加 for 或 包裹）
  label即使没有for 但是在作用域内也可以选
  <Label FOR="InputBox" ACCESSKEY＝"N">姓名</Label><input ID="InputBox" type="text">  
  `点击label 或者热键N label 都会触发input`  
  <Label><span>hahahahaa</span><input ID="InputBox" type="text"></Label>  
  `只要input是label其中一个子元素 即使不给label加属性 在非input处点击父元素label也会触发input`
* HTML5的form如何关闭自动完成功能？  
  <input type="text" id="cc" name="cc" autocomplete="off"> 有什么卵用？
如何实现浏览器内多个标签页之间的通信? (Ali)

* webSocket如何兼容低浏览器？(Ali)  
  定义:WebSocket一种在单个TCP 连接上进行全双工通讯的协议 客户端只需向服务端发起一次握手 就可就坐等服务器端的回调 而无需轮询  
  ？？额外js？？
  
* 网页验证码是干嘛的，是为了解决什么安全问题？  
  防止机器人批量注册、登录、灌水  
* tite与h1的区别、b与strong的区别、i与em的区别？
  一个网站只会有一个标题 多个H1会稀释主题 支持多title 且title权重大于h1 爬虫易于获取利于seo  
  b（Bold）i（Italic）视觉要素（presentationl elements）无意义加粗 斜体 `物理标记`
  em（emphasized text）和 strong（strong emphasized text）是表达要素(phrase elements) 语义化 `逻辑标记` 
页面可见性（Page Visibility）API 可以有哪些用途？

如何在页面上实现一个圆形的可点击区域？

实现不使用 border 画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都能保持同一效果。

* HTML XHTML XML解释 
```markdown
	1.SGML（标准通用标记语言）是一个标准，告诉我们怎么去指定文档标记。
	2.html即是超文本标记语言（Hyper Text Markup Language）规范不是很好，大小写混写且编码不规范；
	3.xhtml即是升级版的html（Extensible Hyper Text Markup Language），一种过渡语言，html向xml过渡的语言；
	4.xml即时可扩展标记语言（Extensible Markup Language），是一种跨平台语言，XML 被设计用来传输和存储数据。
	5.html>>xhtml>>xml 
	6.关系
	   -SGML
	      -HTML
	    -XML -XHTML
```
* doctype
```markdown
    **作用** doctype声明指出阅读程序应该用什么规则集来解释文档中的标记
    **规则** W3C所发布的一个文档类型定义（DTD）中包含的规则     
    **结构** 
	  -语法 HTML 顶级元素 可用性 "注册//组织//类型 标签//定义 语言""URL"
		    -顶级元素 指定 DTD 中声明的顶级元素类型 HTML 默认
		    -可用性 指定正式公开标识符(FPI)是可公开访问的对象还是系统资源。 PUBLIC 默认
		    -注册 指定组织（w3c）是否由国际标准化组织(ISO)注册。 + 默认 组织名称已注册;- 组织名称未注册
		    -组织 由!DOCTYPE 声明引用的 DTD 的创建和维护的团体或组织的名称（w3c）
		    -类型 指定公开文本类，即所引用的对象类型。 DTD 默认。DTD。
		    -标签 指定公开文本描述，后面可附带版本号。 HTML 默认。
		    -定义 指定文档类型定义,Frameset 框架集文档。Transitional 包含除 frameSet 元素的全部内容。/Strict
		    -语言  EN 默认。英语。
		    -URL 指定所引用对象的位置。
     **模式**
	    	  -标准模式Standards 
	    	  		-概念 览器以其支持的最高标准呈现页面
	    	  		-例子 如果XHTML、HTML 4.01文档包含形式完整的DOCTYPE;包含过渡DTD和URI的DOCTYPE
	    	  -混杂模式Quirks （向后兼容）
	    	  		-概念 览器以其支持的最高标准呈现页面
	    	  		-例子 如果XHTML、HTML 4.01文档包含形式完整的DOCTYPE;有过渡DTD而没有URI;DOCTYPE不存在或形式不正确
	    	  -特殊
				-HTML5 
		 	  	-特性 不基于SGML，因此不需要对DTD进行引用（也就没有严格模式与宽松模式的区别）但是需要doctype来规范浏览器的行为
						
```
* 行块空元素
```markdown
  -种类
	**行**   a span img br(换行)
		 input label textarea select(项目选择)
		 em(强调) strong b(加粗) font i(斜体) big small u(下划线) 
		 sub sup(下标) abbr(缩写) cite(引用) code (计算机代码 在引用源码的时候需要)


	**块**   div p ul ol li h1 hr(水平分割线) blockquote
		 table thead tbody tfoot tr th td dl(一个定义列表) dt dd form fieldset 
		 address center(居中对齐块) menu(菜单列表) pre(格式化文本) dir(目录列表)

	**空**   img input meta link 
```
* html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？   
      HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
      绘画 canvas;
      用于媒介回放的 video 和 audio 元素;
      本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
      sessionStorage 的数据在浏览器关闭后自动删除;
      语意化更好的内容元素，比如 article、footer、header、nav、section;
      表单控件，calendar、date、time、email、url、search;
      新的技术webworker, websocket, Geolocation;  
      
* HTML5的离线储存怎么使用，工作原理能不能解释一下？  
			在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
			> 原理  
      
					HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。

			> 如何使用  
      
					1、页面头部像下面一样加入一个manifest的属性；
					2、在cache.manifest文件的编写离线存储的资源；
					    CACHE MANIFEST
					    #v0.11
					    CACHE:
					    js/app.js
					    css/style.css
					    NETWORK:
					    resourse/logo.png
					    FALLBACK:
					    / /offline.html
					3、在离线状态时，操作window.applicationCache进行需求实现。
	  	 > 移除的元素   
       
			      纯表现的元素：basefont，big，center，font, s，strike，tt，u;
			      对可用性产生负面影响的元素：frame，frameset，noframes；

* 简述一下你对HTML语义化的理解

				  用正确的标签做正确的事情。
				  html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
				  即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
				  搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
				  使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
* Label的作用是什么？是怎么用的？

				label标签来定义表单控制间的关系,当用户选择该标签时
				浏览器会自动将焦点转到和标签相关的表单控件上。

				<label for="Name">Number:</label>
				<input type="text" name="Name" id="Name"/>
				<label>Date:<input type="text" name="B"/></label>
* 前端性能优化的方法？

		  （1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。

		  （2） 前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数

		  （3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。

		  （4） 当需要设置的样式很多时设置className而不是直接操作style。

		  （5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。

		  （6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。

		  （7） 图片预加载，将样式表放在顶部，将脚本放在底部  加上时间戳。

		  （8） 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示比div+css布局慢。
		  对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO。向前端优化指的是，在不影响功能和体验的情况下，能在浏览
		  
		  
* 浏览器页面有哪三层构成，分别是什么，作用是什么 
结构层：HTML实现页面结构，  
表示层：CSS完成页面的表现与风格，  
行为层：JavaScript实现一些客户端的功能与业务  

* HTML5的优点与缺点？  
优点： 	
a、网络标准统一、（由W3C推的）。
b、多设备、跨平台、移动应用程序和游戏 
d、可用性、友好体验、即时更新、语义化的新标签；
f、更多的多媒体元素(视频和音频)、替代Flash和Silverlight；  
h、涉及到网站的抓取和索引的时候，对于SEO很友好； 

缺点： 
a、安全：web storage、web socket 这样的功能很容易被黑客利用，来盗取用户的信息和资料。 
b、完善性：许多特性各浏览器的支持程度也不一样。 
c、技术门槛：HTML5简化开发者工作的同时代表了有许多新的属性和API需要开发者学习，像web worker、web socket、web storage 等新特性，后台甚至浏览器原理的知识，机遇的同时也是巨大的挑战 
d、性能：某些平台上的引擎问题导致HTML5性能低下。 
e、浏览器兼容性：最大缺点，IE9以下浏览器几乎全军覆没。    

* 说说你对HTML5认识?（是什么,为什么）  
是什么： 
```  
HTML5指的是包括 HTML 、 CSS 和 JavaScript 在内的一套技术组合。
它希望能够减少网页浏览器对于需要插件的丰富性网络应用服务（ Plug-in-Based Rich Internet Application ， RIA ）， 
例如： AdobeFlash 、 Microsoft Silverlight 与 Oracle JavaFX 的需求，并且提供更多能有效加强网络应用的标准集。
```
为什么：
```  
为了增强浏览器功能 Flash 被广泛使用，但安全与稳定堪忧，不适合在移动端使用（耗电、触摸、不开放）。  
HTML5增强了浏览器的原生功能，符合 HTML5 规范的浏览器功能将更加强大，减少了 Web 应用对插件的依赖，让用户体验更好.  

```  

* 对WEB标准以及W3C的理解与认识?   

```
标签:闭合、小写、不乱嵌套、提高搜索机器人搜索几率、
内容：提高seo，提高搜索，使用外链css和 js 脚本
逻辑：使用外链css和 js 脚本，结构的行为表现的分离，文件下载与页面速度更快，访问用户更多，更广泛的设备访问，更少的代码和组件

其他：容易维护、改版方便，不需要变动页面内容、提供打印版本而不需要复制内容、提高网站易用性。
```    

* 什么是WebGL,它有什么优点?  
定义：  
```  
WebGL（全写 Web Graphics Library ）是一种 3D 绘图标准，  
这种绘图技术标准允许把 JavaScript 和 OpenGL ES 2.0 结合在一起，通过增加 OpenGL ES 2.0 的一个 JavaScript 绑定， WebGL 可以为 HTML5 Canvas 提供硬件 3D 加速渲染，这样 Web 开发人员就可以借助系统显卡来在浏览器里更流畅地展示 3D 场景和模型了，还能创建复杂的导航和数据视觉化。显然， WebGL 技术标准免去了开发网页专用渲染插件的麻烦，可被用于创建具有复杂 3D 结构的网站页面，甚至可以用来设计 3D 网页游戏等等。
```  
作用：
```  
全写 Web Graphics Library 
通俗说WebGL中 canvas 绘图中的 3D 版本。因为原生的 WebGL 很复杂，我们经常会使用一些三方的库，如 three.js 等，这些库多数用于 HTML5 游戏开发。
 
```


* link和@import的区别?  
引用：
<link rel='stylesheet' rev='stylesheet' href='CSS文件 ' type='text/css' media='all' />  
<style type='text/css' media='screen'>
@import url('CSS文件 ');
</style>  

两者都是外部引用CSS的方式，但是存在一定的区别：
区别1： link 是 XHTML 标签，除了加载 CSS 外，还可以定义 RSS 等其他事务； @import 属于 CSS 范畴，只能加载 CSS 。
区别2： link 引用 CSS 时，在页面载入时同时加载； @import 需要页面网页完全载入以后加载。
区别3： link 是 XHTML 标签，无兼容问题； @import 是在 CSS2.1 提出的，低版本的浏览器不支持。
区别4： link 支持使用 Javascript 控制 DOM 去改变样式；而 @import 不支持。  



* 说说你对SVG理解?  
SVG可缩放矢量图形（ Scalable Vector Graphics ）是基于可扩展标记语言（ XML ），用于描述二维矢量图形的一种图形格式。 SVG 是 W3C('World Wide Web ConSortium' 即 ' 国际互联网标准组织 ') 在 2000 年 8 月制定的一种新的二维矢量图形格式，也是规范中的网络矢量图形标准。 SVG 严格遵从 XML 语法，并用文本格式的描述性语言来描述图像内容，因此是一种和图像分辨率无关的矢量图形格式。 SVG 于 2003 年 1 月 14 日成为 W3C 推荐标准。
特点：
(1)任意放缩
用户可以任意缩放图像显示，而不会破坏图像的清晰度、细节等。
(2)文本独立
SVG图像中的文字独立于图像，文字保留可编辑和可搜寻的状态。也不会再有字体的限制，用户系统即使没有安装某一字体，也会看到和他们制作时完全相同的画面。
(3)较小文件
总体来讲，SVG文件比那些 GIF 和 JPEG 格式的文件要小很多，因而下载也很快。
(4)超强显示效果
SVG图像在屏幕上总是边缘清晰，它的清晰度适合任何屏幕分辨率和打印分辨率。
(5)超级颜色控制
SVG图像提供一个 1600 万种颜色的调色板，支持 ICC 颜色描述文件标准、 RGB 、线 X 填充、渐变和蒙版。
(6)交互 X 和智能化。 SVG 面临的主要问题一个是如何和已经占有重要市场份额的矢量图形格式 Flash 竞争的问题，另一个问题就是 SVG 的本地运行环境下的厂家支持程度。
浏览器支持：
Internet Explorer9，火狐，谷歌 Chrome ， Opera 和 Safari 都支持 SVG 。
IE8和早期版本都需要一个插件 - 如 Adobe SVG 浏览器，这是免费提供的。










 
  
