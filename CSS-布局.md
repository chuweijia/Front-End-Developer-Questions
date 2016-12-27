* 如何居中div？如何居中一个浮动元素？如何让绝对定位的div居中？  
### 水平垂直居中（css3）  

>  绝对定位    
   ```  
   .main{
      position:absolute;
      top:50%;
      left:50%;
      margin-top:-3em; 6/2 
      margin-left:-9em; 18/2
      width:18em;
      height:6em;
   }  
   ```  
   ```  
   .main{
      position:absolute;
      top:calc(50% - 3em);
      left:calc(50% - 9em);
      width:18em;
      height:6em;
   }  
   ```  
   ```  
   .main{
      position:absolute;
      top:50%;
      left:50%;
      transform:translate(50% 50%); //这个属性以元素自身宽高进行换算和移动
   }  
   ```  
>  视口单位   
   ```  
   .main{
      width:18em;
      padding:1em 1.5em;
      margin:50vh auto 0;// 100vh = 100*1/100 =1 
      transform:translateY(-50%); //这个属性以元素自身宽高进行换算和移动
      //margin的百分比是按父元素计算的
   }  
   ```  
>  Flexbox  
   ```  
   body{
      display:flex;
      min-height:100vh;
      margin:0;
   }
   .main{
      margin:auto;//当使用flexbox时候 margin:auto实现了水平垂直居中
   }  
   ``` 

### 居中 

* CSS3有哪些新特性？ 
* 一个满屏 品 字布局 如何设计?  
  上面的div宽100%  
  下面的两个div分别宽50%  
  然后用float或者inline使其不换行即可  

* absolute的containing block计算方式跟正常流有什么不同？  
* margin和padding分别适合什么场景使用？  
  `padding`   
   盒子内,border内加`补白`时候  
   空白处不需要背景（色）时  
   盒子间,距离需要叠加时候,1px+2px = 3px  
   `margin`   
   盒子内,border外加`空白`时候  
   空白处需要背景（色）时。  
   盒子间,距离需要抵消时候,1px+2px = 2px   
* 移动端的布局媒体查询
* 对BFC规范(块级格式化上下文：block formatting context)的理解？
* CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？

* position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？  
* 请解释一下为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式  
* li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？（前页已有解答）
* 用纯CSS创建一个三角形的原理是什么？  
  ```  
      width: 0;
      height: 0;
      border-width: 20px;
      border-style: solid;
      border-color: transparent transparent #333 transparent;  //必须在宽度有的基础上去做颜色
  ```  
  
* position的值relative和absolute定位原点是？  

  >  static   
  
     对象遵循正常文档流   
     占据文档空间  
     positon的默认属性  
     top、right、bottom、left、z-index等属性是无效的  
     
     
  >  relative  
  
     对象遵循正常文档流   
     占据文档空间  
     加了top/bottom 会在正常文档流中偏移位置  文档空间`不会发生`偏移(后续元素依据top前的文档位置进行定位)  
     加了margin/padding 文档空间`会发生`偏移  (后续元素依据margin后的文档位置进行定位)  
     
     
     
    
  >  absolute   
  
     脱离文档流  
     根据祖先类元素(父类以上)进行定位 且该祖先是`position为非static`方式的   
     relative和static方式在最外层时是以`body`标签为定位原点的 而absoulte方式在无父级是position非static定位时是以`html`作为原点定位  
     `<html>和<body>元素相差9px左右`  
     如果使用absoulte或fixed定位的话，必须指定 left、right、 top、 bottom 属性中的至少一个，否则left/right/top/bottom属性会使用它们的默认值          auto ，这将导致对象遵从正常的HTML布局规则，在前一个对象之后立即被呈递，简单讲就是都变成relative，会占用文档空间(讲道理绝对定位已经脱离文档流)      祖先类的margin会让子类的absoulte跟着偏移，而padding却不会让子类的absoulte发生偏移。总结一下，就是absoulte是根据祖先类的`border`进行的定位  
     
     
  >  fixed  
  
     同absolute   
     定位原点是窗口  
     
  >  z-index  
  
     父子关系是无法用z-index来设定上下关系的，一定是子级在上父级在下  
     使用`static` 定位或`无position`定位的元素z-index属性是无效的  
     
     
     
