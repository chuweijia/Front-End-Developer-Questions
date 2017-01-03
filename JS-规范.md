* 介绍JavaScript的基本数据类型。 

### typeof 

  返回值"undefined""boolean""string" "number" "object" "function"    
 
### undefined  
  
      ```  
	  	 var mes ;//带分号表示已声明未主动初始化,不带分号表示未声明

		同var mes = undefined; 默认被动初始化值为undefined

		alert(mes == undefined);//true;

		var mes2

		alert(typeof(mes));//"undefined"

		alert(typeof(mes2));//"undefined" 
      
      ``` 
      
  ### Null  
  
      ```  
	    var mes = null;//null值表示一个空对象指针！！
	    alert(typeof(mes));//"object" 区分于上面六种
	    alert(null == undefined);//true undefined是派生于null的
	    //若意在保存对象的变量还没有真正保存对象时 应明确让它先保存null值(null作为空指针惯例)
      
      ```  
  ### boolean  
  
      ```  
	true false // True False 不是bool值而是字面量  
        Boolean()//对应表在P26  
	
        
      ``` 
  ### Number  
  
      ```  
      
        5.1 十进制八进制十六进制 --> 算术运算统统转为十进制数值 
		    5.2 数值范围
		            Number.MIN_VALUE(值为 5e-324) ~ Number.MAX_VALUE(值为 1.7976931348623157e+308)
 					超范围自动转值 -Infinity ~ Infinity
        5.3 NaN(Not a Number 即非数值)
            alert(NaN == NaN);//false NaN与任何值都不相等包括自己 ..疯了
            isNaN(NaN);//true
            isNaN(0/0);//NaN   此函数会确认这个参数是否 "不是数值"
            isNaN(12/0);//Infinity  
            isNaN(-12/0);//-Infinity  
	5.4 数值转换
		5.4.1 Number()
			Number(null);//0
			Number(undefined);//NaN
			Number("");//0
			Number("123blue");//NaN
		5.4.2 parseInt()
				parseInt("");//NaN
					parseInt("123blue");//123
		5.4.3 parseFloat()  
        
      ```  
      
  ### String    
  
      ```  
      
        6.1 支持'' 和 "" 
	    字符字面量 被当做一个字符来解析
	    var text = "This is \u03a3"; //text.length 为9 一个空格算一个字符
        6.2 toString()
            6.2.1 null 和 undefined 没有这个方法
            6.2.2 含参 2 8 10 16 代表进制转换
        6.3 String()
            String(null);//"null"
            String(undefined);//"undefined"
      
      ``` 
  ### Object  
  
   ```  
        var o = new Object();
	constructor
	hasOwnProperty(propertyName);
	isPrototypeOf(object);
	propertyIsEnumerable(propertyName);
	toLocaleString();
	toString();
	valueOf();  
      
   ```   
   
   
* 说说写JavaScript的基本规范？  
  
* JavaScript有几种类型的值？（堆：原始数据类型和 栈：引用数据类型），你能画一下他们的内存图吗？
* Javascript创建对象的几种方式？
* 什么是window对象? 什么是document对象?
* null，undefined的区别？  
	```  
	  var mes = null;//null值表示一个空对象指针！！  
	  var mes = undefined; //默认被动初始化值为undefined   
	  var mes2 //未声明  
	  alert(typeof(mes));//"undefined"  
	  alert(typeof(mes2));//"undefined"  
	  alert(typeof(mes));//"object" 据说这是一个bug  
	```  

	
	
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
  
  ```  
  $( "#foo" ).bind( "mouseenter mouseleave", function() {
    $( this ).toggleClass( "entered" );
  });  
  //暂时想不到了
  ```  
  
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
  点击a 触发顺序 `ul捕获 li捕获 a捕获 a冒泡（a的注册顺序） li冒泡 ul冒泡`  
  
  
 
