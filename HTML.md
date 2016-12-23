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
页面可见性（Page Visibility）API 可以有哪些用途？

如何在页面上实现一个圆形的可点击区域？

实现不使用 border 画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都能保持同一效果。
 
  
