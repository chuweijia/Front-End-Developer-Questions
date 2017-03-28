Doctype作用？严格模式与混杂模式如何区分？它们有何意义?

HTML5 为什么只需要写 <!DOCTYPE HTML>？

行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

页面导入样式时，使用link和@import有什么区别？

介绍一下你对浏览器内核的理解？

常见的浏览器内核有哪些？

html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？

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
        1.SGML（标准通用标记语言）是一个标准，告诉我们怎么去指定文档标记。
        2.html即是超文本标记语言（Hyper Text Markup Language）规范不是很好，大小写混写且编码不规范；
        3.xhtml即是升级版的html（Extensible Hyper Text Markup Language），一种过渡语言，html向xml过渡的语言；
        4.xml即时可扩展标记语言（Extensible Markup Language），是一种跨平台语言，XML 被设计用来传输和存储数据。
        5.html>>xhtml>>xml 
        6.关系
           -SGML
              -HTML
            -XML -XHTML
* doctype
	    -作用 doctype声明指出阅读程序应该用什么规则集来解释文档中的标记
	          -规则 W3C所发布的一个文档类型定义（DTD）中包含的规则
	          
	    -结构 
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
	    -模式
	    	  -标准模式Standards 
	    	  		-概念 览器以其支持的最高标准呈现页面
	    	  		-例子 如果XHTML、HTML 4.01文档包含形式完整的DOCTYPE;包含过渡DTD和URI的DOCTYPE
	    	  -混杂模式Quirks （向后兼容）
	    	  		-概念 览器以其支持的最高标准呈现页面
	    	  		-例子 如果XHTML、HTML 4.01文档包含形式完整的DOCTYPE;有过渡DTD而没有URI;DOCTYPE不存在或形式不正确
	    	  -特殊
					-HTML5 
		 	  			-特性 不基于SGML，因此不需要对DTD进行引用（也就没有严格模式与宽松模式的区别）但是需要doctype来规范浏览器的行为

* 行块空元素
			  -种类
			   		-行 a span img br(换行)
			   			input label textarea select(项目选择)
			   			em(强调) strong b(加粗) font i(斜体) big small u(下划线) 
			   			sub sup(下标) abbr(缩写) cite(引用) code (计算机代码 在引用源码的时候需要)


			   		-块 div p ul ol li h1 hr(水平分割线) blockquote
			   			table thead tbody tfoot tr th td dl(一个定义列表) dt dd form fieldset 
			   			address center(居中对齐块) menu(菜单列表) pre(格式化文本) dir(目录列表)

			   		-空 img input meta link 
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






 
  
