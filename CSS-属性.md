* CSS选择符有哪些？  
**1.基本选择器**  
`*`  
`p`  
`.`  
`#`  
`p,ul`  
`p ul`  
`p > ul`  
`p + ul` `p ~ ul`(css3)  
**2.属性选择器**  
`以下所有 都可以只保留到[]写法`  
`p[title]`  
`div[class=error]`  
`td[headers~=col1]`  值col1是 headers属性下用空格分割的众多值中的一个  
`p[lang|=en]`  匹配lang属性的值，这个值以en开头。比如 `<p lang="en-us">Hi!</p>`  
**3.css2.1中的伪类**  
`p:first-child` 只有当该元素为其父元素的第一个孩子时才会被匹配，即该元素之前没有兄弟节点  
`E:lang(c)` 匹配lang属性等于c的E元素  
`a:link`  
`a:hover` 先
`input:focus` 后 比如 input必须保证点击一下 才能获取焦点  
`a:active` 鼠标按下未抬起时 即点按激活时  
`a:visited` 已被访问过的  
**css2.1中的伪元素  （貌似伪元素规定用双冒号表示 但是由于兼容性 选择了单引号）**    
`p:first-line` p的第一行元素  
`p:first-letter` p的第一个元素   
`p:before`  
`p:after`  

**4.css3基本选择器**  
`p ~ ul`  
`div[class^="nav"]`class以nav开头  
`div[class$="nav"]`class以nav结尾  
`div[class*="nav"]`class中包含nav的   

**5.css3与用户界面有关的伪类**  
`input:enabled`  表单中激活的元素  
`input:disabled` 表单中禁用的元素  
`.radio:checked`  
`input::selection` 匹配用户当前选中的元素  

**6.css3与结构性的伪类**    

```
p:nth-child(3) { color:#f00; }
p:nth-child(odd) { color:#f00; }
p:nth-child(even) { color:#f00; }
p:nth-child(3n+0) { color:#f00; }
p:nth-child(3n) { color:#f00; }
tr:nth-child(2n+11) { background:#ff0; }
tr:nth-last-child(2) { background:#ff0; }
p:last-child { background:#ff0; }
p:only-child { background:#ff0; }
p:empty { background:#ff0; }
:not(p)  
E:target	匹配文档中特定"id"点击后的效果
```  


* 哪些属性可以继承？  
**1.可继承的样式**  
字体：`font`、`color`、`font-family`、`font-size（继承计算后的值）`、font-size-adjust、font-stretch 、font-style 、font-style 、text-underline-position 、font-variant 、 text-transform `line-height`、`letter-spacing` 、word-spacing  
文本：`text-indent` 、`text-align` 、layout-flow 、writing-mode 、white-space 、`word-wrap` 、text-kashida-space 、layout-grid 、layout-grid-char 、layout-grid-char-spacing 、layout-grid-line 、layout-grid-mode 、layout-grid-type  
列表：`list-style` 、list-style-image 、list-style-position 、list-style-type  
表格：`border-collapse` 、border-spacing 、caption-side 、empty-cells 、table-layout 、speak-header  

**2.不可继承的样式**  
字体：text-decoration 、`text-shadow`  
文本：text-overflow 、`vertical-align` 、direction、unicode-bidi 、`word-break` 、line-break 、text-autospace、`text-justify` 、ruby-align 、ruby-overhang 、ruby-position 、ime-mode  
背景：`background`  
定位：`position 、z-index 、top、right 、bottom 、left `   
尺寸：`height 、max-height 、min-height 、width、max-width 、min-width`  
布局：clear 、`float`、clip 、`overflow`、`display`、`visibility`  
外补丁：`margin`  
内补丁：`padding`   
轮廓：`outline`  
边框：`border`  
列表：marker-offset   
其他：`cursor`、`zoom`  

* CSS优先级算法如何计算？ 
权重   
!important > style(1000) > #id(100) > .class(10) >　div(1)   
* CSS3新增伪类有那些？  
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
  ```markdown 
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
   
   
  
  
`:link`(css2)  未被访问过
`:hover`(css2)   悬停
`:focus`(css2)   获得焦点 比如input元素得在点击后获取焦点  
`:active`(css2)  被点击鼠标未抬起   
`:visited`(css2)  已访问过
激活顺序（一般-->特殊）`link - visited - hover - focus(鼠标松开) - active`  
`:target`用法#news:target  
  
**伪元素**  
`::before`  
`::after`  
`::first-line` 只能用于块元素中 匹配元素中第一行的文本  
`::selection`匹配用户被用户选中或者处于高亮状态的部分  
`::placeholder` 只有被设置时有效<input type="email" placeholder="name@domain.com">   

![image](http://7xsk2q.com1.z0.glb.clouddn.com/CSS/css%E4%BC%AA.png)  
  
* display有哪些值？说明他们的作用。   
`display: none;`  
> 同$.hide() 不占位;  visibility:hidden; 占位  
`display: inline;`  
> text-align无效，设置了line-height会让inline元素居中   
```  
设置inline元素同行消除间隙  
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>
<body>
  <div class="main">
    <div class="test">zhan</div>
    <div class="test">123</div>
  </div>
</body>
</html>
html{
  -webkit-text-size-adjust:none;/* 使用webkit的私有属性，让字体大小不受设备终端的调整，可定义字体大小小于12px */
}
.main{
  font-size:0;
  *word-spacing:-1px;/* 使用word-spacing 修复 IE6、7 中始终存在的 1px 空隙，减少单词间的空白（即字间隔） */
}
.test{
  display:inline;
  width: 10000px;
  height:10000px;
  border:1px solid;
  font-size:12px;
  letter-spacing: normal;/* 设置字母、字间距为0 */ 
  word-spacing: normal; /* 设置单词、字段间距为0 */
}   
```   


`display: block;`  
> 默认会继承父元素的宽度,并且独占一行,高度一般以子元素撑开的高度为准  

`display: list-item;`  
> 此属性默认会把元素作为列表显示，要完全模仿列表的话还需要加上 `list-style-position` `list-style-type`  

`display: inline-block;`  
>  inline-block既具有block的宽高特性又具有inline的同行元素特性  
   inline-block会形成一个`BFC`  待了解  
   
    
`display: table;`  
> 作为块级表格显示  


display: inline-table;  
`display: table-cell;`   
display: table-column;  
display: table-column-group;  
display: table-footer-group;  
display: table-header-group;  
display: table-row;  
display: table-row-group;  
display: table-caption;  
display: inline-list-item;  
`display: flex;`  
> 设为Flex布局以后，子元素的float、clear和vertical-align属性将失效   
`display: box;`  
> Flexbox的兼容性问题会有叙述    

`display: inline-flex;`  
`display: grid;`  
`display: inline-grid;`  
display: ruby;
display: ruby-base;
display: ruby-text;
display: ruby-base-container;
display: ruby-text-container;  

display: contents;
display: run-in;  

display: inherit;  
display: initial;  
display: unset;  
`inherit` 继承  
`initial` 初始化  
`unset`  默认可继承，则值为inherit；否则值为initial  
`revert` 若用户定义样式表中显式设置，则按此设置；否则，按照浏览器定义样式表中的样式设置；否则，等价于unset   
`all` 表示重设除unicode-bidi和direction之外的所有CSS属性的属性值，取值只能是initial、inherit、unset和revert  

  



* 请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？  
  `flex-direction(方向)`  
  >  flex-direction: row(起点左) | row-reverse | column（起点上） | column-reverse;  
  
  
  `flex-wrap（换行方式）`    
  >  flex-wrap: nowrap | wrap（换行起点在左,新行在下） | wrap-reverse（换行起点在左,新行在上）;   
  
  `flex-flow(方向+换行方式)`    
  >  flex-flow: <flex-direction> || <flex-wrap>;（默认值为 row nowrap）    
  
  `justify-content横轴`  
   >  justify-content: flex-start | flex-end | center | space-between | space-around;  
      box-pack:start(defalut) | end | center | justify  `兼容Android4.3-`  
    
    
    
  `align-items竖轴`  
  >  align-items: flex-start | flex-end | center | baseline | stretch;   
     box-align:start | end | center | baseline | stretch(default)  `兼容Android4.3-`  
    
     
  `align-content`定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用   
  >  align-content: flex-start | flex-end | center | space-between | space-around | stretch;    
  
  
  
  
  
  












