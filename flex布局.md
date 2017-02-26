## flex布局

## Flex基本概念：

![flex.png](http://upload-images.jianshu.io/upload_images/2093884-2048a754a30d46c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在flex 容器中默认两条轴，水平主轴（main axis）和垂直交叉轴cross axis。
- 在容器中每个单元块被称之为flex item，每个项目占据的主轴空间为 main size，占据的交叉空间为cross size

## Flex容器：
flex布局首先需要一个指定容器，任何一个容器都可被置顶为flex布局，这样容器内部的元素就可以使用flex进行布局
```
.container{
    display: flex | inline-flex; // 可以有两种取值
}
```
> 当设置flex布局之后，子元素的float、clear、vertical-align 的属性将会失效。

有六种元素可以设置在容器上：
1. flex-direction：决定主轴方向（`.container{flex-direction: row|row-reverse|column|column-reverse}` ）
2. flex-wrap: 决定容器内 项目是否可换行（`.container:{flex-wrap:nowrap|wrap|wrap-reverse;}`）
3. flex-flow:flex-direction和flex-wrap的简写形式（`flex-flow:<flex-direction>||<flex-wrap>`）
4. justify-content:定义了项目在主轴的对齐方式（`justify-content:flex-start|flex-den|center|space-between|space-around;`）
> 默认值：flex-start 左对齐，flex-end 右对齐，center 居中， space-between 两端对齐，项目之间的间隔相等，即剩余空间等分成空隙。 space-around：每个项目两侧的间隔相等，所以项目之间的间隔比项目与边缘的间隔大一倍。
1. align-items： 定义了项目在交叉轴上的对齐方式（`flex-start|flex-end|center|baseline|stretch;`）
> 默认值为strech 即如果项目未设置高度或高度值设置为auto，将占满整个容器的高度，flex-start 交叉的起点对齐，flex-end：交叉的终点对齐，center ：交叉的中点对齐，baseline：项目第一行文字的基线对齐
1. align-content：定义多根轴线的对齐方式，如果项目只有一根轴线，那么该属性将不起作用

## flex项目属性
1. order：定义容器中的排列顺序，数值 越小越靠前
2. flex-basis：定义了在分配多余空间前，项目占据的主轴空间，浏览器根据这个属性，计算主轴是否有多余的空间
3. flex-grow： 定义项目的放大比例
> 默认值为零，如果存在剩余空间也不放大；值相同，均分；不同，按比例分
1. flex-shrink：定义了缩小比例，空间不足，项目将缩小，负值对该属性无效
> 默认属性值都为1，当空间不足，都将等比例缩小，如果一个为0，则空间不足时，其不缩小
1. flex:flex-grow,flex-shrink,flex-basis 的简写
> `flex:none| [<'flex-grow'> <'flex-shrink'> ? ||<'flex-basis'>]`
1. align-self：允许单个项目有与其他项目不一样的对齐方式 
> 单个项目覆盖align-items定义的属性,默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。与align-items属性是一样的，但它只对单个元素生效。

