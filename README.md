介绍一下标准的CSS的盒子模型？与低版本IE的盒子模型有什么不同的？

CSS选择符有哪些？哪些属性可以继承？

CSS优先级算法如何计算？
权重
!important > style(1000) > #id(100) > .class(10) >　div(1)
CSS3新增伪类有那些？  
 **伪类**
 `p ~ ul`p之后的所有ul亲兄弟  
 (css2中有个`p+ul`指p之后的唯一一个最亲的ul亲兄弟)  
 `a[href^="https"]`(^以开头)  
 `a[href$="https"]`($以结尾)  
 `a[href*="https"]`(但凡包含)  
 
 
 `:checked`用法input:checked  
 `:disabled`用法input:disabled  
 `:enabled`用法input:enabled  
 `:invalid`用法input:invalid eg:`<input type="email"/>` 如果其中写的格式不是email 则会被命中  
 `:valid`  
 `:optional` 选择非<input required> 即未被 required的元素  
 `:in-range`用法input:in-range eg:`<input type="number" min="5" max="10" value="7">`写入的元素在范围内 则会被命中  
 `:out-of-range`  
 `:read-only`<input readonly>  
 `:read-write`选择非<input readonly>
 `:root`选择根节点html
 
 `:empty`用法input:empty 选择那些没有孩子的节点 （注意：`空文本`也算一个节点）  
 `:first-of-type`或者`:last-of-type`用法p:first-of-type 找到所有局部环境中的第一个p节点（注意：`p不一定是第一个节点` 可选中**多个**元素）  
 `:last-of-type`用法p:last-of-type 找到所有局部环境中的最后一个p节点（注意：`p不一定是最后一个节点`）  
 `:last-child`(css3) `:first-child`(css2)  （注意：只能选中**一个**元素）  
  举栗子
  ```  
  <div class="parent">
    <h1>Child</h1>   <!-- .parent > :first-of-type -->
    <div>Child</div> <!-- .parent > :first-of-type -->
    <div>Child</div>
    <div>Child</div>
  </div>  
  ```  
  `:not(selector)`  用法:not(p) 除了  
  `:nth-child(n)` 用法p:nth-child(2n+1) 参数可以变量可以常数  
  `:nth-last-child(n)` 从后往前数第N个  
  `:nth-last-of-type(n)` 用法nth-last-of-type(odd) 但是没有nth-first-of-type(n)..  
  `:nth-of-type(n)` 用法nth-of-type(odd)  
  `:only-child` 相当于既是first-child又是last-child  
  `:only-of-type` ??  
   举栗子  
   ```  
   li:first-child:nth-last-child(4)~li{
      //某元素既是第一个也是倒着数第四个,则一共有四个元素
      //~命中该范围内的全部li
   }  
   ```  
   
   
  
  
  `:link`(css1)  未被访问过
  `:hover`(css1)   悬停
  `:visited`(css1)  已访问过
  `:active`(css1)  被点击时  
   激活顺序（一般-->特殊）`link - visited - hover - focus(鼠标松开) - active`  
  `:target`用法#news:target  
  
   **伪元素**  
   `::before`  
   `::after`  
   `::first-line` 只能用于块元素中 匹配元素中第一行的文本  
   `::selection`匹配用户被用户选中或者处于高亮状态的部分  
   `::placeholder` 只有被设置时有效<input type="email" placeholder="name@domain.com">   
   
   ![image](http://7xsk2q.com1.z0.glb.clouddn.com/CSS/css%E4%BC%AA.png)  
  


如何居中div？如何居中一个浮动元素？如何让绝对定位的div居中？

display有哪些值？说明他们的作用。

position的值relative和absolute定位原点是？

CSS3有哪些新特性？

请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？

用纯CSS创建一个三角形的原理是什么？

一个满屏 品 字布局 如何设计?

常见兼容性问题？

li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？

经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hack的技巧 ？

为什么要初始化CSS样式。

absolute的containing block计算方式跟正常流有什么不同？

CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？

position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？

对BFC规范(块级格式化上下文：block formatting context)的理解？

CSS权重优先级是如何计算的？

请解释一下为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式

移动端的布局用过媒体查询吗？

使用 CSS 预处理器吗？喜欢那个？

CSS优化、提高性能的方法有哪些？

浏览器是怎样解析CSS选择器的？

在网页中的应该使用奇数还是偶数的字体？为什么呢？

margin和padding分别适合什么场景使用？

抽离样式模块怎么写，说出思路，有无实践经验？[阿里航旅的面试题]

元素竖向的百分比设定是相对于容器的高度吗？

全屏滚动的原理是什么？用到了CSS的那些属性？

什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE？

视差滚动效果，如何给每页做不同的动画？（回到顶部，向下滑动要再次出现，和只出现一次分别怎么做？）
