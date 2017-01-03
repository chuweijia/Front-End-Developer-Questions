## 数据类型
* 介绍JavaScript的基本数据类型。
* 说说写JavaScript的基本规范？
* JavaScript有几种类型的值？（堆：原始数据类型和 栈：引用数据类型），你能画一下他们的内存图吗？
* Javascript创建对象的几种方式？
* 什么是window对象? 什么是document对象?
* null，undefined的区别？
* javascript 代码中的"use strict";是什么意思 ? 使用它区别是什么？
* documen.write和 innerHTML的区别?
* DOM操作——怎样添加、移除、移动、复制、创建和查找节点?
* JavaScript中的作用域与变量声明提升？

* ["1", "2", "3"].map(parseInt) 答案是多少？
* 数组和对象有哪些原生方法，列举一下？

## 移动端  
* 移动端最小触控区域是多大？
* 移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决这个延时？（click 有 300ms 延迟,为了实现safari的双击事件的设计，浏览器要知道你是不是要双击操作。）

## 交互  
   * 对JSON的了解？  
   * Ajax 是什么? 如何创建一个Ajax？  
## 事件篇  
* JQuery一个对象可以同时绑定多个事件，这是如何实现的？ 
* 关于事件，IE与火狐的事件机制有什么区别？ 如何阻止冒泡？  

  ```  
    		element.addEventListener(type,handler,false);//DOM2 IE9 FF Safari Chrome Opera
    	  element.attachEvent("on"+type,handler);//IE Opera 
        event.preventDefault();//阻止默认行为 当event.cancelable为true时
        event.stopPropagation();//停止进一步冒泡 当event.cancelable为true时
  ```  
  
  
  
* 我们给一个dom同时绑定两个点击事件，一个用捕获，一个用冒泡，你来说下会执行几次事件，然后会先执行冒泡还是捕获      

  document 往 target节点，`捕获前进`，遇到注册的捕获事件立即触发执行   
  
  到达target节点，触发事件（对于target节点上，是先捕获还是先冒泡则捕获事件和冒泡事件的`注册顺序`，先注册先执行）  
  
  target节点 往 document 方向，`冒泡前进`，遇到注册的冒泡事件立即触发  
  
  举个例子  
 
  
  ```  
    		<ul id="ul">
          <li id="li">
          123
          <a href="#" id="a">aaa</a>
          </li>
          <li>456</li>
          <li>789</li>
          123
    </ul>    
  ```  
 
