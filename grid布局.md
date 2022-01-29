# grid布局
### Flex 布局是轴线布局，只能指定"项目"针对轴线的位置，可以看作是一维布局。Grid 布局则是将容器划分成"行"和"列"，产生单元格，然后指定"项目所在"的单元格，可以看作是二维布局。Grid 布局远比 Flex 布局强大。  

1. grid是二维布局
2. 也有container与items
3. 使用display:grid | inline-grid 是元素变为grid布局
 
## 容器属性
1. 容器指定了网格布局以后，接着就要划分行和列。grid-template-columns属性定义每一列的列宽，grid-template-rows属性定义每一行的行高。    
* --template
  
  n.模板；样板；型板；模框  
  网络范本；模板文件；模板模式
```
 .container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 100px 100px;
}
.container {
  display: grid;
  grid-template-columns: 33.33% 33.33% 33.33%;
  grid-template-rows: 33.33% 33.33% 33.33%;
}
```
* grid-template
>-是grid-template-rows和grid-template-columns的缩写形式  
比如说，grid-template: 50% 50% / 200px;  
将创建一个具有两行的网格，每一行占据50%，以及一个200像素宽的列。  

除了使用绝对单位，也可以使用百分比。    

[预览链接](http://js.jirengu.com/vaxuvinigi/3/edit)  
 
1. 容器属性 fr 关键字

为了方便表示比例关系，网格布局提供了fr关键字（fraction 的缩写，意为"片段"）。如果两列的宽度分别为1fr和2fr，就表示后者是前者的两倍。适合做平均布局.
[预览链接](http://127.0.0.1:5500/grid.html)

```
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
}
```
4. 容器属性 grid-row-gap 属性，grid-column-gap 属性，grid-gap 属性.  
* grid-row-gap属性设置行与行的间隔（行间距），grid-column-gap属性设置列与列的间隔（列间距）。
* grid-gap属性是grid-column-gap和grid-row-gap的合并简写形式，语法如下。
```
.container {
  grid-gap: 20px（列间距） 20px（行间距））;
}
```
1. 容器属性 grid-template-areas 属性 网格布局允许指定"区域"（area），一个区域由单个或多个单元格组成。  
2. [预览链接1](http://js.jirengu.com/qucikukuru/4/edit)[预览链接2](http://js.jirengu.com/gevidabaqo/2/edit)
```
.container{
  display: grid;
  grid-template-areas:
    "header header header"
    "aside main ad"
    "footer footer footer"
    ;
  grid-template-rows:60px auto 60px;
  grid-template-columns:191px auto 191px;
  min-height: 100vh;
  outline: 1px solid red;
}
```
## 2.项目items属性
1. item属性 可以设置范围

```
.item-a{
  grid-column-start: 1 ; 也可设置span相对于结束位置来设置其宽度
  grid-column-end:2 | span 2;/* span 加数字可跨行 */
  gri-row-start: 1 ; 也可设置span相对于结束位置来设置其宽度
  grid-row-end: 2 | span 2;
  
}


```
* 如果每次都输入grid-column-start和grid-column-end两个属性，我们一定会厌烦的。幸运的是，grid-column是一个缩写形式，它可以一次接受两个值，只要用'/'分开就好。
```
.item-a{
  grid-column:1/4;  1 | span (num)
  grid-row:1/2;  1 | span(num) 
  
}
```   


2. 如果你觉得同时输入grid-column和grid-row也很复杂，我们还有另一种缩写。grid-area属性接受4个由'/'分开的值：grid-row-start, grid-column-start, grid-row-end, 最后是grid-column-end。

举个例子如下所示：grid-area: 1 / 1 / 3 / 6;。  
[grid小游戏链接](https://cssgridgarden.com/#zh-cn) 
