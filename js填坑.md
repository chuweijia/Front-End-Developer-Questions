* 误触  
**禁用缩放：**  
`<meta name="viewport" content="user-scalable=no">`  
`<meta name="viewport" content="initial-scale=1,maximum-scale=1">`  
**width=device-width的meta标签**  
针对于ios，除了`双击缩放`的约定，在渲染桌面端站点时候，使用`980px`的视口宽度，而非设备本身宽度（iphone为`320px`）  
**FastClick**  
虽然解决了300ms，但是由于它基与tap，副作用会带来误触  
**ios click bug**  
描述：  
```markdown  
   root.on('click','.master .inimg,.master .outimg',function(){
       `ios的坑，ios click自带阴影但是个别元素不需要这个效果，故click有时无效`
   })
```
解决：  
```markdown  
item.onclick = function(){
  `在这里被声明注册了onclick事件，则下面有效`  
}
```   

* jq  
jQuery("<a>").prop("tagName") //`"A"`  

* 随机数  
生成 `min <= 随机数 <= max` 的随机数  
`int num = min + (int)(Math.random() * (max-min+1));`  

* Math  
var a =5678;  
Math.floor(a/1000)%10;
`int num = min + (int)(Math.random() * (max-min+1));`  

* ios bug  
safari对事件的解析比较特殊，如果一个事件曾经被响应过，则会一直被冒泡／捕获到根结点。  
针对于`已大规模触发`的情况,解决方案，在body的所有子元素绑定一个空事件  
`("body > *").on('click',function(){})`  
然后再去引用`禁止事件冒泡`    





