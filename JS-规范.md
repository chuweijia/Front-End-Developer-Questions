* 介绍JavaScript的基本数据类型。 

### typeof 

	返回值"undefined""boolean""string" "number" "object" "function"    
 
### undefined  
  

	var mes ;//带分号表示已声明未主动初始化,不带分号表示未声明

	同var mes = undefined; 默认被动初始化值为undefined

	alert(mes == undefined);//true;

	var mes2

	alert(typeof(mes));//"undefined"

	alert(typeof(mes2));//"undefined" 
      
        
      
### Null  
    var mes = null;//null值表示一个空对象指针！！
    alert(typeof(mes));//"object" 区分于上面六种
    alert(null == undefined);//true undefined是派生于null的
    //若意在保存对象的变量还没有真正保存对象时 应明确让它先保存null值(null作为空指针惯例)
### boolean  
  
    true false // True False 不是bool值而是字面量  
    Boolean()//对应表在P26  
### Number  
  
      
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
          
    
      
### String    
  
	6.1 支持'' 和 "" 
	    字符字面量 被当做一个字符来解析
	    var text = "This is \u03a3"; //text.length 为9 一个空格算一个字符
	6.2 toString()
	    6.2.1 null 和 undefined 没有这个方法
	    6.2.2 含参 2 8 10 16 代表进制转换
	6.3 String()
	    String(null);//"null"
	    String(undefined);//"undefined"
	    
### Object  
 
	var o = new Object();
	constructor
	hasOwnProperty(propertyName);
	isPrototypeOf(object);
	propertyIsEnumerable(propertyName);
	toLocaleString();
	toString();
	valueOf();    
   
   
* 说说写JavaScript的基本规范？  
  
* JavaScript有几种类型的值？（堆：原始数据类型和 栈：引用数据类型），你能画一下他们的内存图吗？
* Javascript创建对象的几种方式？
* 什么是window对象? 什么是document对象?   
### window  

		  定义：BOM（浏览器对象模型）的核心对象   
		       表示浏览器的一个实例   
		       是接口,js访问浏览器时候  
		       是Global对象,ECMAScript规定的,所以有权全局访问方法和属性  



		  var age = 10;
		  window.color:red;
		  delete window.age;//能获取  无法删除
		  delete window.color;//能获取  能删除 delete可以删除直接定义在window上的对象  
	  
	  
       
  
  ![image](http://7xsk2q.com1.z0.glb.clouddn.com/JS/bower.png)  
  		
		  window.screenLeft/screenTop ; 表示窗口相对于屏幕的左/上的位置
		  window.innerWidth含滚动条宽度
		  标准模式(且IE6必须保证是标准)：document.documentElement.clientWidth 可以取得视口大小  
		  混杂模式：document.documentElement.clientWidth 可以取得视口大小 (chrome混杂模式两种都可取得)   
  
  
  
 
### document  

		定义：JS通过Document类型表示文档
		      在浏览器中,是HTMLDocument(继承自Document类型)的一个实例 表示整个HTML页面
		      document对象是window对象的一个属性,可作为为全局对象访问
	       
		DOM(文档对象模型)是针对HTML和XML文档的一个API(应用程序编程接口),可将其描绘成由多层节点构成的结构  
		Node.ELEMENT_NODE(1) //Node类型 node.nodeType == 1
		Node.DOCUMENT_NODE(9) //document类型 node.nodeType == 9  
	
	
* null，undefined的区别？  
	 
		  var mes = null;//null值表示一个空对象指针！！  
		  var mes = undefined; //默认被动初始化值为undefined   
		  var mes2 //未声明  
		  alert(typeof(mes));//"undefined"  
		  alert(typeof(mes2));//"undefined"  
		  alert(typeof(mes));//"object" 据说这是一个bug  
	

	
	
* javascript 代码中的"use strict";是什么意思 ? 使用它区别是什么？
* documen.write和 innerHTML的区别?  

		   document.write是直接写入到页面的内容流，如果在写之前没有调用document.open, 浏览器会自动调用open。每次写完关闭之后重新调		  用该函数，会导致页面被重写。
		   innerHTML则是DOM页面元素的一个属性，代表该元素的html内容。你可以精确到某一个具体的元素来进行更改。如果想修改document的   	      内容，则需要修改document.documentElement.innerElement。
		   innerHTML将内容写入某个DOM节点，不会导致页面全部重绘
		   innerHTML很多情况下都优于document.write，其原因在于其允许更精确的控制要刷新页面的那一个部分。  

		   document.write  页面全部绘制  
		   innerHTML 页面局部绘制  
	   
  ![image](http://7xsk2q.com1.z0.glb.clouddn.com/inner.gif)  
  
* DOM操作——怎样添加、移除、移动、复制、创建和查找节点?    
### 添加：
		  someNode.appendChild(newNode);//表示在整个childNodes结尾添加节点,如果newNode已存在 仅表示移位置,返回值为新增的节点  
		  someNode.insertBefore(newNode,Node);//第二个参数是被参照节点可NULL 
		  someNode.replaceChild(newNode,someNode.firstChild);//newNode替换了firstChild  
### 移除：
  	  	someNode.removeChild(newNode);
### 复制：
		  someNode.cloneNode(true);//深复制 包括副本和其所有子节点
		  someNode.cloneNode(false);//浅复制 包括副本 成为孤儿  
### 创建：
		  document.createElement("div");//尚未添加到文档树中 不会影响浏览器的显示！
		  document.body.appendChild();//这样就添加到文档树中了！
		  document.createElement("<div id=\"id1\" class=\"class1\"></div>");//直接添加  
### 查找：
		  someNode.nextSibling;
		  someNode.previousSibling;
		  someNode.parentNode;
		  someNode.firstChild;
		  someNode.lastChild;

		  document.getElementById("id");
		  document.getElementsByTagName("li");
		  document.querySelector("#id");//选择第一个#id的元素
		  document.querySelectorAll("p strong");//选择全部p下的strong  


		  firstElementChild是它的元素版/previousElementChild/childElementCount(返回子元素且不含文本节点和注释的个数)/parentElement
 
* JavaScript中的作用域与变量声明提升？

* ["1", "2", "3"].map(parseInt) 答案是多少？  

### parseInt()函数   

		  parseInt(string, radix)  
		  运算为加	
		  string	必需。要被解析的字符串。

		  radix  	可选。表示要解析的数字的基数。该值介于 2 ~ 36 之间。
				如果省略该参数或其值为 0，则数字将以 10 为基础来解析。如果它以 “0x” 或 “0X” 开头，将以 16 为基数。
				如果该参数小于 2 或者大于 36，则 parseInt() 将返回 NaN。  

		  parseInt("10");	        //返回 10
		  parseInt("19",10);		//返回 19 (10+9)
		  parseInt("11",2);		//返回 3 (2+1)
		  parseInt("17",8);		//返回 15 (8+7)
		  parseInt("1f",16);		//返回 31 (16+15)
		  parseInt("010");		//未定：返回 10 或 8  



		  function parseInt(str, radix) {   
			return str+'-'+radix;   
		  };  
		  var a=["1", "2", "3", "4","5",6,7,8,9,10,11,12,13,14,15];  
		  a.map(parseInt);   
		  输出结果为：["1-0","2-1","3-2","4-3","5-4","6-5","7-6","8-7","9-8","10-9","11-10","12-11","13-12","14-13","15-	    14"]  

		  索引index的起始值从0开始，与radix的对应如前陈述一致，所以才会出现返回NaN的类型值  
	  
	  
	  
  
  
* 数组和对象有哪些原生方法，列举一下？    

### 数组

>  栈和队列  
    
    		// 队列 push() shift()
	    	var arr = new Array();
		arr.push("a");
		arr.push("b");
		arr.push("c");//队列压入
		console.log(arr);//["a", "b", "c"]
		arr.shift();//返回头部a 并删除	
	
		// 栈 push() pop()
		var arr = new Array();
		arr.push("a");
		arr.push("b");
		arr.push("c");//栈压入
		console.log(arr);//["a", "b", "c"]	
		// 若是如下
		arr = arr.push("a");
		console.log(typeof(arr));//number!!!! push的返回值是元素个数


        	// unshift（）在数组头部添加 返回数组长度
		var arr = new Array();
		arr.unshift("a");
		arr.unshift("b");
		arr.unshift("c");//把unshift看做除了入栈 入队列的第三种方“入”
		console.log(arr);//["c", "b", "a"]
		arr.pop();//返回尾部值a 并删除
		console.log(arr);//["c", "b"]


		// 若整块unshift()
		arr.unshift("a","b");
		arr.unshift("c");
		console.log(arr);//["c", "a", "b"] 注意整块移植到头部!!  
	
>  重排序  

    		sort(sortfunction)
		sortFunction
		可选项。是用来确定元素顺序的函数的名称。如果这个参数被省略，那么元素将按照 ASCII字符顺序进行升序排列。
		sort 方法将 Array 对象进行适当的排序；在执行过程中并不会创建新的 Array 对象。 
		如果为 sortfunction 参数提供了一个函数，那么该函数必须返回下列值之一： 
		负值，如果所传递的第一个参数比第二个参数小。 
		零，如果两个参数相等。 
		正值，如果第一个参数比第二个参数大。    
		
		
		var values = ["A","3"];
		values.sort();
		console.log(values);//["3", "A"]

		//优先比较第一位 第一位一样比较第二位**  

		var values = ["1A","3"];
		values.sort();
		console.log(values);//["1A", "3"]
		var values = ["A1","3"];
		values.sort();
		console.log(values);//["3", "A1"]

		//根据上述 所以此时的排序会出现bug 于是我们需要加一个函数来消除bug

		function up(e1,e2){//升序
			//return e1-e2;
			if(e1<e2) {
				return -1;//应该是sort()的特定属性
			}else if(e1>e2) {
				return 1;
			}else {
				return 0;
			} 
		}
		function down(e1,e2){//降序
			//return e2-e1;
			if(e1<e2) {
				return 1;
			}else if(e1>e2) {
				return -1;
			}else {
				return 0;
			} 
		}
		var values = [0,1,5,10,15];
		values.sort();
		console.log(values);//[0, 1, 10, 15, 5] 出问题了！
		values.sort(up);
		console.log(values);//[0, 1, 5, 10, 15] 
		values.sort(down);
		console.log(values);//[15, 10, 5, 1, 0] 
		//reverse()反转顺序 并不是进行了值的比较！！
		values.reverse();
		console.log(values);//[15, 10, 5, 1, 0]   
		
>  数组的增删改  

		// concat() 连接的意思 
		// concat()会基于原数组创建一个数组的副本 
		var values = ["a","b","c","d"];
		values.concat("new");
		console.log(values);//["a", "b", "c", "d"]
		var values = ["a","b","c","d"];
		var nvalues = values.concat("new");
		console.log(nvalues);//["a", "b", "c", "d","new"]

		// slice() 切片的意思 返回被切下来的数组
		// slice()会基于原数组创建一个新数组 且不会影响原数组！！
		var values = ["a","b","c","d"];
		values.slice(1,2);  //相当于取的索引是[1,2) 若只有一个参数 例则[0,values.length)取得全部元素
		console.log(values);//["a", "b", "c", "d"]
		var values = ["a","b","c","d"];
		var nvalues = values.slice(1,2);
		console.log(nvalues);//["b"]

		// splice(起始位置,要删除的项数,要插入的项目们)
		// 其中第二个参数不包括其本身！！
		// splice()返回被删除的项目们
		var values = ["a","b","c","d"];
		values.splice(1,2,"b1","c1");
		console.log(values);//["a", "b1", "c1", "d"]  
		
>  数组的索引位置    

		// indexof() lastindexof() 返回要查找的值的索引 第二个参数是查找起点(可选) 无则返回-1
		var values = ["a","b","c","d"];
		var ind = values.indexOf("c",1);
		console.log(ind);//2   
		
		
>  数组的迭代    

		var values = ["a","b","c","d"];
		values.forEach(function(item,index,array){//结果应该是最后一次的
		console.log(item);//a b c d
		console.log(index);//0 1 2 3 
		console.log(item);
		//["a", "b", "c", "d"]
			//["a", "b", "c", "d"]
			//["a", "b", "c", "d"]
			//["a", "b", "c", "d"]
		},this);
		console.log(this);//window 对象
		var values = ["a","b","c","d"];
		for(item in values){//遍历出了每一次的结果 同上对比
			console.log(item);// 0 1 2 3
		}
		
### 对象  



		
		
		

		
		
    		
    
  
## 移动端  
* 移动端最小触控区域是多大？
* 移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决这个延时？（click 有 300ms 延迟,为了实现safari的双击事件的设计，浏览器要知道你是不是要双击操作。）

## 交互  
   * 对JSON的了解？  
   * Ajax 是什么? 如何创建一个Ajax？  
## 事件篇  
* JQuery一个对象可以同时绑定多个事件，这是如何实现的？ 

		  $( "#foo" ).bind( "mouseenter mouseleave", function() {
		    $( this ).toggleClass( "entered" );
		  });  
		  //暂时想不到了
  
* 关于事件，IE与火狐的事件机制有什么区别？ 如何阻止冒泡？  
	
	
		element.addEventListener(type,handler,false);//DOM2 IE9 FF Safari Chrome Opera
		element.attachEvent("on"+type,handler);//IE Opera 
		event.preventDefault();//阻止默认行为 当event.cancelable为true时
		event.stopPropagation();//停止进一步冒泡 当event.cancelable为true时    
	
	
* 我们给一个dom同时绑定两个点击事件，一个用捕获，一个用冒泡，你来说下会执行几次事件，然后会先执行冒泡还是捕获      

		  document 往 target节点，`捕获前进`，遇到注册的捕获事件立即触发执行   
		  到达target节点，触发事件（对于target节点上，是先捕获还是先冒泡则捕获事件和冒泡事件的`注册顺序`，先注册先执行）  
		  target节点 往 document 方向，`冒泡前进`，遇到注册的冒泡事件立即触发  
  
  举个例子  
  
	    <ul id="ul">
	      <li id="li">
	      123
	      <a href="#" id="a">aaa</a>
	      </li>
	      <li>456</li>
	      <li>789</li>
	      123
	    </ul>    
  点击a 触发顺序 `ul捕获 li捕获 a捕获 a冒泡（a的注册顺序） li冒泡 ul冒泡`  
  
  
 
