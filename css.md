# css

#### 选择器

##### 基础选择器

标签选择器：

类选择器：样式  .    ,调用class，可调用多次

id选择器：样式#，调用id，只能调用一次

通配选择器：*定义，给所有的标签，元素都改样式

##### 复合选择器

后代选择器：选父元素里面的***所有**子元素（儿子孙子）

​                        可以一一往后推空格分开，

​                        可以是任何基础选择器的组合

子选择器：选**最近**一级（亲儿子）>分开

并集选择器: 逗号相隔

##### **伪类选择器**：特点是用冒号（:）表示

链接伪类选择器：

 hover：鼠标悬停状态 
active：激活状态，即鼠标按下状态 
link：超链接未访问时的状态 
visited：超链接访问过后的状态 
使用顺序：link、visited、hover、active   

```
/* a 是标签选择器	所有的链接 */ 
a {
  color: gray;
}
/* :hover 是链接伪类选择器 鼠标经过 */ 
a:hover {
    color: red;	/* 鼠标经过的时候，由原来的 灰色 变成了红色 */
}

/* 选中鼠标按下时的a元素 */
a:active{
    color:#008c8c;
}
```

##### 伪元素选择器

使结构简单，可以简化代码；

使用场景：

- 伪元素字体图标（多个类似的时可有效简化代码量）
- 经过盒子时出现灰色罩层
- 清除浮动    

**新增伪类选择器**

- E:first-child  选择第一个子元素 
- E:last-child   选择最后一个子元素
- E:nth-child(n)  选择第n个子元素（n可为数字，even（偶数），odd（奇数），未知数）

------

#### CSS的三大特性：

- 层叠性

- 继承性（文字类，**行高的继承**）

- 优先级

  > 若选择器相同，层叠性
  >
  > 选择器不同，选择器的权重（**继承的权重为0**）

#### 字体属性

- **字体(font-family)**:body指定整个页面,单位

- **字体大小（front-size）**：body指定整个页面，标题较特殊，需要特定指定字体大小

- **字体粗细(font-weigth)**：

  用数字更好（不需要加单位）

  可以是标题变细number：400

  bold:700

- **字体样式（font-style）**一般用于em和i便正常

  > 复合写法：font：font-style font-weight font-size/line-height font-family
  >
  > **注意**：顺序不可改；可省略某些属性，但必须保留font-size、 font-family，否则font属性不起作用

- **字体颜色（color）**

#### 背景属性

- 背景颜色

- 背景图片

- 背景平铺

- 背景图片位置

- 背景图像固定

1. 背景颜色

   background-color:颜色值;

   background-color:transparent;（默认）

   2、背景图片

​        background-image :  url (url)

​        background-image ：none（默认）

​        **实际开发常见于 logo 或者一些装饰性的小图片或者是超**

​        **大的背景图片（便于控制位置）**

  注意：背景颜色和背景图片可以同时设置，图片于颜色上面

  3、背景平铺

​        background-repeat: repeat | no-repeat | repeat-x | repeat- y

  4、背景图片位置

​       background-position: x y;

> ​       x 坐标和 y 坐标。 可以使用 方位名词（left.center.right | top.center.bottom ） 或者 精确单位  
>
> - 都为方位：顺序无关
> - 都为数值：第一个为x坐标，第二个为y坐标
> - 混合数值：第一个为x，第二个为y坐标

  **注意：**若只指定一个，则第二个默认居中

  5、背景图像固定

​       background-attachment : scroll | fixed

   **简写（提倡）**：     background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置;  （顺序无关）

   **背景半透明：**background: rgba(0, 0, 0, 0.3);（可以把0.3——.3）

------

#### 三角做法

```
div{
    width:0;
    height:0;
    border:10px solid transparent;
    border-bottom-color:red;
}
```

#### 图片应用

> 当图片属于网页内容时，使用img元素
>
> 当图片仅用于美化页面时，使用背景图url（便于控制位置）
>
> 字体图标：显示网页中通用、样式简单的小图标
>
> 精灵图：结构样式复杂的小图片

------

#### 元素的显示模式

1. 行内元素
2. 块级元素

**块级元素**

常见的块元素有<h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>等，其中 <div> 标签是最典型的块元素。

块级元素的特点：

① 独占一行。

② 高度，宽度、外边距以及内边距都可以控制。

③ 宽度默认是容器（父级宽度）的100%。

④ 是一个容器及盒子，里面可以放**行内或者块级元素。**

> **注意：**
>
> 文字类（<p>、<h1>-<h6>）的元素内不能使用块级元素

**行内元素**

常见的行内元素有 <a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>等，其中

<span> 标签是最典型的行内元素。有的地方也将行内元素称为内联元素。

行内元素的特点：

① 相邻行内元素在一行上，一行可以显示多个。

② 高、宽直接设置是无效的。

③ 默认宽度就是它本身内容的宽度。

④ 行内元素只能容纳**文本或其他行内元素。**

> **注意：**
>
> <a>链接里面不能再放链接
>
>  特殊情况链接 **<a> 里面可以放块级元素**，但是给 <a> 转换一下块级模式最安全

**行内块元素**

在行内元素中有几个特殊的标签 ——**<img>** 、<input />、<td>，它们同时具有块元素和行内元素的特点。  有些资料称它们为行内块元素。

行内块元素的特点：

① 和相邻行内元素（行内块）在一行上，但是他们之间会有**空白缝隙**。一行可以显示多个（行内元素特点）。

② 默认宽度就是它本身内容的宽度（行内元素特点）。

③ 高度，行高、外边距以及内边距都可以控制（块级元素特点）。

#### 元素模式的转换

转换为块元素：display:block;

转换为行内元素：display:inline;

转换为行内块：display: inline-block

------

#### CSS3css盒子模型

- box-sizing：content-box；（默认）

  盒子大小=width+padding+border

- box-sizing：border-box；

  盒子大小=width.(border和padding增大则容量减少)

#### CSS3过渡

语法：

transition：过渡的属性 花费的时间 运动曲线 何时开始

### 圆角边框

border-radius：length；

- 参数可以为数值/百分数

- 圆：数值设为正方形高度/宽度一半或者50%

  矩形：高度的一半

  ```
  border-radius：50%；
  ```

- 该属性为简写；可跟几个值：

  四个值：顺时针旋转（左上 右上 右下 左下）

  三个值：左上   左下右上   右下

  两个值：左上右下     左下右上

- 分开写：

  eg：border-top-left-radius；

### 盒子阴影

box-shadow:水平阴影 垂直阴影 距离模糊（虚实）阴影尺寸（影子大小） 阴影颜色  内/外阴影

h-shadow: 必需，水平阴影的位置，允许负值

v-shadow: 必需，垂直阴影位置，允许负值

blur：可选 模糊距离

spread：可选 阴影尺寸

color：可选 阴影的颜色 查阅css颜色值

inset：可选 将外部阴影（outset）改为内部阴影

```
box-shadow：10px 10px 10px -4px raba（0,0,0,0.1）
```

**注意**

默认outset，但是不可写这个单词，否则阴影无效

盒子阴影不占用空间