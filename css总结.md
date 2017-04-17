* box-shadow  
 h-shadow（必，水平阴影位置，可负） || v-shadow（必） || blur（模糊距离） || spread(阴影尺寸) || color || inset（内阴 默认outset）  
 **drop-shadow**  
 x-offset || y-offset || 模糊半径 || 模糊颜色  
 
 * 安卓line-height bug  
 ```markdown  
    <div>`当font-size为奇数时，line-height有2px误差`</div>  
    div{
      dispaly:inline-block;
      background:red;
      height:40px;
      line-height:40px;
      font-size:20px;
      transform:scale(0.5);  `二倍缩放问题`
      transform-orgin:0% 0%;
    }
 ```  
 * :after:before 伪  
 ```markdown  
 <div>:before 是在元素内的前后内容处调用的 `即不破坏文档树`</div>   
 ```  
 `input` `img` `iframe` 等元素不能包含元素 故不能用伪元素  
 `checkbox` `radio`在chrome中可以插入 目测是个bug   
 * background-size : cover || contain  
   相同点：保持图片比例不变  
   不同点：  
   cover，等比例的放大 直到某个边占满 即`不可留白`  
   contain，最小消耗的占满，即`可留白`    
   
 * box-sizing  
   默认：content-box  
   垂直居中：height = line-height  （若`无内边距影响`）  
   当属性值为border-box时：height中的高度包含了border-width，为了`保持height值`不变，需将`height+2*border`
   **绝对定位奇葩方法避免box-sizing 如下图**  
   ![image](http://7xsk2q.com1.z0.glb.clouddn.com/css/boxsizing2.png)  
 * 多行文本隐藏  
  ```markdown  
     div{
        overflow:hidden;
        text-overflow:ellipsis;
        display:-webkit-box;
        -webkit-line-clamp:5;
        -webkit-box-orient:vertical;
     }
  ```    
  * flex bug  
    display:flex; 会自动`过滤掉两个span间的空格`    
    display:block;  
    如果父元素M（display：flex）下的`子元素a内部还有个子元素b`,需要给`子元素a`再加个属性`display：flex；`  
    
    `space-between`两端对齐，项目之间的间隔相等。  
    `space-around` 每个项目两侧的间隔相等，所以，项目之间的间隔比项目与边框之间的距离大一倍。  
    
    
    
   
 
  
          
   
  
