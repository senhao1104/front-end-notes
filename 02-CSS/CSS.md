## CSS的发展历程

从HTML被发明开始，样式就以各种形式存在。不同的浏览器结合它们各自的样式语言为用户提供页面效果的控制。最初的HTML只包含很少的显示属性。
随着HTML的成长，为了满足页面设计者的要求，HTML添加了很多显示功能。但是随着这些功能的增加，HTML变的越来越杂乱，而且HTML页面也越来越臃肿。于是CSS便诞生了。

## CSS初识

CSS(Cascading Style Sheets)

CSS通常称为CSS样式表或层叠样式表（级联样式表），主要用于设置HTML页面中的文本内容（字体、大小、对齐方式等）、图片的外形（宽高、边框样式、边距等）以及版面的布局等外观显示样式。

CSS以HTML为基础，提供了丰富的功能，如字体、颜色、背景的控制及整体排版等，而且还可以针对不同的浏览器设置不同的样式。

## CSS样式规则

使用HTML时，需要遵从一定的规范。CSS亦如此，要想熟练地使用CSS对网页进行修饰，首先需要了解CSS样式规则，具体格式如下：                                          

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_20-43-00.png" width = "60%">

在上面的样式规则中:

* 选择器用于指定CSS样式作用的HTML对象，花括号内是对该对象设置的具体样式。
* 属性和属性值以“键值对”的形式出现。
* 属性是对指定的对象设置的样式属性，例如字体大小、文本颜色等。
* 属性和属性值之间用英文“:”连接。
* 多个“键值对”之间用英文“;”进行区分。

## CSS3利用cacl()计算长度

css3提供了 calc() = calc(四则运算)用于动态计算长度值。

需要注意的是，运算符前后都需要保留一个空格，例如：width: calc(100% - 10px)；

## CSS字体样式属性

### font-size: 字号大小

font-size属性用于设置字号，该属性的值可以使用相对长度单位，也可以使用绝对长度单位。其中，相对长度单位比较常用，推荐使用像素单位px，绝对长度单位使用较少。具体如下：

| 相对长度单位 | 说明                           |
|--------------|--------------------------------|
| em           | 相对于当前对象内文本的字体尺寸 |
| px           | 像素（推荐使用）               |
| in           | 英寸                           |
| cm           | 厘米                           |
| mm           | 毫米                           |
| pt           | 点                             |

### font-family: 字体

font-family属性用于设置字体。网页中常用的字体有宋体、微软雅黑、黑体等，例如将网页中所有段落文本的字体设置为微软雅黑，可以使用如下CSS样式代码：

```css
p { font-family: "微软雅黑";}
```

可以同时指定多个字体，中间以逗号隔开，表示如果浏览器不支持第一个字体，则会尝试下一个，直到找到合适的字体。

> 常用技巧：

* 现在网页中普遍使用14px+。
* 尽量使用偶数的数字字号。ie6等老式浏览器支持奇数会有bug。
* 各种字体之间必须使用英文状态下的逗号隔开。
* 中文字体需要加英文状态下的引号，英文字体一般不需要加引号。当需要设置英文字体时，英文字体名必须位于中文字体名之前。
* 如果字体名中包含空格、#、$等符号，则该字体必须加英文状态下的单引号或双引号，例如:font-family: "Times New Roman";。
* 尽量使用系统默认字体，保证在任何用户的浏览器中都能正确显示。

### CSS Unicode字体

在 CSS 中设置字体名称，直接写中文是可以的。但是在文件编码（GB2312、UTF-8 等）不匹配时会产生乱码的错误。xp 系统不支持 类似微软雅黑的中文。

方案一： 你可以使用英文来替代。 比如 font-family: "Microsoft Yahei"。

方案二： 在 CSS 直接使用 Unicode 编码来写字体名称可以避免这些错误。使用 Unicode 写中文字体名称，浏览器是可以正确的解析的。
font-family: "\5FAE\8F6F\96C5\9ED1"，表示设置字体为“微软雅黑”。

> 可以通过escape()  来测试属于什么字体。

| 字体名称    | 英文名称        | Unicode 编码         |
|-------------|-----------------|----------------------|
| 宋体        | SimSun          | \5B8B\4F53           |
| 新宋体      | NSimSun         | \65B0\5B8B\4F53      |
| 黑体        | SimHei          | \9ED1\4F53           |
| 微软雅黑    | Microsoft YaHei | \5FAE\8F6F\96C5\9ED1 |
| 楷体_GB2312 | KaiTi_GB2312    | \6977\4F53_GB2312    |
| 隶书        | LiSu            | \96B6\4E66           |
| 幼园        | YouYuan         | \5E7C\5706           |
| 华文细黑    | STXihei         | \534E\6587\7EC6\9ED1 |
| 细明体      | MingLiU         | \7EC6\660E\4F53      |
| 新细明体    | PMingLiU        | \65B0\7EC6\660E\4F53 |

为了照顾不同电脑的字体安装问题，我们尽量只使用宋体和微软雅黑中文字体。

### font-weight: 字体粗细

字体加粗除了用 b  和 strong 标签之外，可以使用CSS 来实现，但是CSS 是没有语义的。

font-weight属性用于定义字体的粗细，其可用属性值：normal、bold、bolder、lighter、100~900（100的整数倍）。

>小技巧： 
数字 400 等价于 normal，而 700 等价于 bold。  但是我们更喜欢用数字来表示。  

### font-style: 字体风格

字体倾斜除了用 i  和 em 标签之外，可以使用CSS 来实现，但是CSS 是没有语义的。

font-style属性用于定义字体风格，如设置斜体、倾斜或正常字体，其可用属性值如下：

normal: 默认值，浏览器会显示标准的字体样式。

italic: 浏览器会显示斜体的字体样式。

oblique: 浏览器会显示倾斜的字体样式。

>小技巧： 
平时我们很少给文字加斜体，反而喜欢给斜体标签（em，i）改为普通模式。

### font: 综合设置字体样式 (重点)

font属性用于对字体样式进行综合设置，其基本语法格式如下：

```css
选择器{font: font-style  font-weight  font-size/line-height  font-family;}
```

使用font属性时，必须按上面语法格式中的顺序书写，不能更换顺序，各个属性以空格隔开。

>注意：其中不需要设置的属性可以省略（取默认值），但必须保留font-size和font-family属性，否则font属性将不起作用。

## 开发者工具（chrome）

此工具是我们的必备工具，以后代码出了问题，我们首先第一反应就是：

“按F12”或者是 “shift+ctrl+i”  打开 开发者工具。

菜单：右击网页空白出---查看 

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_21-11-48.jpg" width = "60%">

>小技巧：
1.ctrl+滚轮 可以 放大开发者工具代码大小。
2.左边是HTML元素结构   右边是CSS样式。
3.右边CSS样式可以改动数值和颜色查看更改后效果。

## 选择器（重点）

要想将CSS样式应用于特定的HTML元素，首先需要找到该目标元素。在CSS中，执行这一任务的样式规则部分被称为选择器（选择符）。

### 标签选择器（元素选择器、类型选择器）

标签选择器是指用HTML标签名称作为选择器，按标签名称分类，为页面中某一类标签指定统一的CSS样式。其基本语法格式如下：

```css
标签名 {属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3;}  或者
元素名 {属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3;}
```

标签选择器最大的优点是能快速为页面中同类型的标签统一样式，同时这也是他的缺点，不能设计差异化样式。

### 类选择器

类选择器使用“.”（英文点号）进行标识，后面紧跟类名，其基本语法格式如下：

```css
.类名{属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3; }
```

```css
 标签调用的时候用 class=“类名”  即可。
```

类选择器最大的优势是可以为元素对象定义单独或相同的样式。

>小技巧：
1.长名称或词组可以使用中横线来为选择器命名。
2.不建议使用“ _ ”下划线来命名CSS选择器。
浏览器兼容问题 (比如使用_tips的选择器命名，在IE6是无效的)
能良好区分JavaScript变量命名(JS变量命名是用“_”)
3.不要纯数字、中文等命名， 尽量使用英文字母来表示。

>案例：

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_21-22-51.jpg" width = "40%">

~~~html
<head>
  <meta charset="utf-8">
  <style>
    span {
      font-size: 100px;
    }
    .blue {
      color: blue;
    }
    .red {
      color: red;
    }
    .orange {
      color: orange;
    }
    .green {
      color: green;
    }
  </style>
</head>
<body>
  <span class="blue">G</span>
  <span class="red">o</span>
  <span class="orange">o</span>
  <span class="blue">g</span>
  <span class="green">l</span>
  <span class="red">e</span>
</body>
~~~

### 多类名选择器

我们可以给标签指定多个类名，从而达到更多的选择目的。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_21-29-00.png" width = "60%">

>注意：
1.样式显示效果跟HTML元素中的类名先后顺序没有关系,受CSS样式书写的上下顺序有关。
2.各个类名中间用空格隔开。

多类名选择器在后期布局比较复杂的情况下，还是较多使用的。

### id选择器

id选择器使用“#”进行标识，后面紧跟id名，其基本语法格式如下：

```css
#id名 {属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3;}
```

该语法中，id名即为HTML元素的id属性值，大多数HTML元素都可以定义id属性，元素的id值是唯一的，只能对应于文档中某一个具体的元素。

用法基本和类选择器相同。

### id选择器和类选择器区别

W3C标准规定，在同一个页面内，不允许有相同名字的id对象出现，但是允许相同名字的class。

类选择器（class） 好比人的名字，是可以多次重复使用的，比如  张伟  王伟  李伟  李娜。

id选择器 好比人的身份证号码，全中国是唯一的、不得重复、只能使用一次。

>选择器和类选择器最大的不同在于 使用次数上。

### 通配符选择器

通配符选择器用“*”号表示，他是所有选择器中作用范围最广的，能匹配页面中所有的元素。其基本语法格式如下：

```css
* { 属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3; }
```

例如下面的代码，使用通配符选择器定义CSS样式，清除所有HTML标记的默认边距。

```css
* {
  margin: 0;                    /* 定义外边距*/
  padding: 0;                   /* 定义内边距*/
}
``` 

### 伪类选择器

伪类选择器用于向某些选择器添加特殊的效果。比如给链接添加特殊效果， 比如可以选择 第1个，第n个元素。

为了和我们刚才学的类选择器相区别，  类选择器是一个点 比如 .demo {}   
而我们的伪类 用 2个点 就是 冒号  比如  :link{}


#### 1.链接伪类选择器

- :link      /* 未访问的链接 */
- :visited   /* 已访问的链接 */
- :hover     /* 鼠标移动到链接上 */
- :active    /* 选定的链接 */

注意写的时候，他们的顺序尽量不要颠倒,按照 lvha 的顺序。

```css
a {   
  /* a是标签选择器  所有的链接 */
  font-weight: 700;
  font-size: 16px;
  color: gray;
}
a:hover {
  /* :hover 是链接伪类选择器 鼠标经过 */
  color: red; /*  鼠标经过的时候，由原来的 灰色 变成了红色 */
}
```

#### 2.结构(位置)伪类选择器（CSS3)

- :first-child: 选取属于其父元素的首个子元素的指定选择器
- :last-child: 选取属于其父元素的最后一个子元素的指定选择器
- :nth-child(n): 匹配属于其父元素的第 N 个子元素，不论元素的类型
- :nth-of-type(n): 简单来说nth-of-type会忽略其它标签的顺序而安装标签自身种类的顺序进行筛选，也就是选择的参照点并不是DOM数，而是自身。
- :nth-last-child(n): 选择器匹配属于其元素的第 N 个子元素的每个元素，不论元素的类型，从最后一个子元素开始计数。
  n 可以是数字、关键词或公式

```css
li:first-child {
  /* 选择第一个孩子 */
  color: pink; 
}
li:last-child {
  /* 最后一个孩子 */
  color: purple;
}
li:nth-child(4) {
  /* 选择第4个孩子 n代表 第几个的意思 */
  color: skyblue;
}
```

#### nth-child介绍 

nth-child(n) 选择器匹配属于其父元素的第 n 个子元素。  

##### 使用它的时候需要注意几点：  

- 第n个子元素的计数是从1开始，不是从0开始的
- 选择表达式中的字母n代表≥0的整数

##### 它有3种常见用法

- 直接指明n的值：span:nth-child(1)
-  用even/odd分别代表偶数 / 奇数：span:nth-child(even) 
- 借助n自定义选择范围：
-   nth-child(2n)/nth-child(2n + 1)：偶数 / 奇数
-  nth-child(n + 3)：第3个开始到最后 

##### 进阶用法 

上面的用法中的第三部分，一般都是使用n，而有时候也会用到-n，比如选取前2个元素就是：nth-child(-n + 2)。  

为什么是这样呢？其实运算：-n + 2 ≥ 0，就可以推出n ≤ 2。  由此，结合两者自动取交集，我们就可以限制选择某一范围。

比如选择第6个到第9个，就是：:nth-child(-n+9):nth-child(n+6)  
注意：不是nth-child(2 - n)，-n要写在一起！  真正理解“子元素”的含义 还是nth-child选择器，
那么下面这段代码的样式是什么呢？

```html
<html>
<head>
  <style>
    span:nth-child(2n) {
      color: red;
    }
  </style>
</head>
<body>
  <div>
    <span>1</span>
    <span>2</span>
  </div>
  <span>3</span>
</body>
</html>
```
答案是：1是黑色的，2和3都是红色的。

因为```<span>2</span>```是其父节点的第2个（偶数）子元素,```<span>3</span>```是其父节点的第2个子元素，第一个是```<div></div>```

所以辨别是否匹配的关键是：找到父元素，然后再计算在父元素中的位置。

##### nth-of-type与nth-child的区别

nth-of-child:

​它的属性就是按照所有类型标签的所谓整体队列进行排序筛选，也就是说不论你是h1，span还是p标签，使用这个属性你要遵循在DOM树中的顺序来进行操作。

nth-of-type:

​简单来说nth-of-type会忽略其它标签的顺序而安装标签自身种类的顺序进行筛选，也就是选择的参照点并不是DOM数，而是自身。就是按照类型来计算，碰到一个同类型就加1。

#### 3.目标伪类选择器(CSS3)

:target目标伪类选择器 :选择器可用于选取当前活动的目标元素

```css
:target {
  color: red;
  font-size: 30px;
}
```

## CSS注释

CSS规则是使用     / *  需要注释的内容  * /  进行注释的，即在需要注释的内容前使用 / * 标记开始注释，在内容的结尾使用 * /结束。

例如：

```css
p {
  font-size: 14px;  /*所有的字体是14像素大小*/
}
```

## CSS外观属性

### color: 文本颜色

color属性用于定义文本的颜色，其取值方式有如下3种：

1. 预定义的颜色值，如red，green，blue等。

2. 十六进制，如#FF0000，#FF6600，#29D794等。实际工作中，十六进制是最常用的定义颜色的方式。

3. RGB代码，如红色可以表示为rgb(255,0,0)或rgb(100%,0%,0%)。

> 需要注意的是，如果使用RGB代码的百分比颜色值，取值为0时也不能省略百分号，必须写为0%。

### line-height: 行间距（行高）

line-height属性用于设置行间距，就是行与行之间的距离，即字符的垂直间距，一般称为行高。line-height常用的属性值单位有三种，分别为像素px，相对值em和百分比%，实际工作中使用最多的是像素px。

>一般情况下，行距比字号大7、8像素左右就可以了。

### text-align: 水平对齐方式

text-align属性用于设置文本内容的水平对齐，相当于html中的align对齐属性。其可用属性值如下：

* left: 左对齐（默认值）
* right: 右对齐
* center: 居中对齐

### text-indent: 首行缩进

text-indent属性用于设置首行文本的缩进，其属性值可为不同单位的数值、em字符宽度的倍数、或相对于浏览器窗口宽度的百分比%，允许使用负值, 建议使用em作为设置单位。

1em 就是一个字的宽度。如果是汉字的段落，1em 就是一个汉字的宽度。

### letter-spacing: 字间距

letter-spacing属性用于定义字间距，所谓字间距就是字符与字符之间的空白。其属性值可为不同单位的数值，允许使用负值，默认为normal。

### word-spacing: 单词间距

word-spacing属性用于定义英文单词之间的间距，对中文字符无效。和 letter-spacing 一样，其属性值可为不同单位的数值，允许使用负值，默认为normal。

word-spacing和letter-spacing均可对英文进行设置。不同的是letter-spacing定义的为字母之间的间距，而word-spacing定义的为英文单词之间的间距。

### 颜色半透明(css3)

文字颜色到了CSS3我们可以采取半透明的格式了语法格式如下：

color: rgba(r,g,b,a)  
a 是alpha  透明的意思  取值范围 0~1之间 
0 是全透明，1是不透明

例如：
```css
color: rgba(0,0,0,0.3)  
```

### 文字阴影(CSS3)

以后我们可以给我们的文字添加阴影效果了  shadow  影子  

```css
text-shadow: 水平位置 垂直位置 模糊距离 阴影颜色;
```
| 值            | 说明                       |
|--------------|--------------------------- |
| h-shadow     | 必须。水平阴影的位置 允许负值。 |
| v-shadow     | 必须。垂直阴影的位置 允许负值。 |
| blur         | 可选。模糊的距离。            |
| color        | 可选。阴影的颜色。            |

## sublime快捷方式

sublime可以快速提高我们代码的书写方式：

1. 生成标签 直接输入标签名 按tab键即可。
2. 如果想要生成多个相同标签  加上 * 就可以了 比如 div*3 就可以快速生成3个div。
3. 如果有父子级关系的标签，可以用 >  比如   ul > li就可以了。
4. 如果有兄弟关系的标签，用  +  就可以了 比如 div+p。  
5. 如果生成带有类名或者id名字的，直接写.demo 或者  #two  tab 键就可以了。

## 引入CSS样式表（书写位置）

CSS可以写到那个位置？ 是不是一定写到html文件里面呢？

### 内部样式表

内嵌式是将CSS代码集中写在HTML文档的head头部标签中，并且用style标签定义，其基本语法格式如下：

```html
<head>
<style type="text/css">
    选择器 {属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3;}
</style>
</head>
```

语法中，style标签一般位于head标签中title标签之后，也可以把他放在HTML文档的任何地方。

type="text/css"  在html5中可以省略， 写上也比较符合规范， 所以这个地方可以写也可以省略。

### 行内式（内联样式）

内联样式，又有人称行内样式、行间样式、内嵌样式。是通过标签的style属性来设置元素的样式，其基本语法格式如下：

```html
<标签名 style="属性1: 属性值1; 属性2: 属性值2; 属性3: 属性值3;"> 内容 </标签名>
```

语法中style是标签的属性，实际上任何HTML标签都拥有style属性，用来设置行内式。其中属性和值的书写规范与CSS样式规则相同，行内式只对其所在的标签及嵌套在其中的子标签起作用。

### 外部样式表（外链式）

链入式是将所有的样式放在一个或多个以.CSS为扩展名的外部样式表文件中，通过link标签将外部样式表文件链接到HTML文档中，其基本语法格式如下：

```html
<head>
  <link href="CSS文件的路径" type="text/css" rel="stylesheet" />
</head>
```

该语法中，link标签需要放在head头部标签中，并且必须指定link标签的三个属性，具体如下：

* href: 定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径。
* type: 定义所链接文档的类型，在这里需要指定为“text/css”，表示链接的外部文件为CSS样式表。
* rel: 定义当前文档与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件。

### 三种样式表总结

| 样式表     | 优点                     | 缺点                     | 使用情况       | 控制范围           |
|------------|--------------------------|--------------------------|----------------|--------------------|
| 行内样式表 | 书写方便，权重高         | 没有实现样式和结构相分离 | 较少           | 控制一个标签（少） |
| 内部样式表 | 部分结构和样式相分离     | 没有彻底分离             | 较多           | 控制一个页面（中） |
| 外部样式表 | 完全实现结构和样式相分离 | 需要引入                 | 最多，强烈推荐 | 控制整个站点（多） |

## 标签显示模式（display）

标签的类型(显示模式)

HTML标签一般分为块标签和行内标签两种类型，它们也称块元素和行内元素。具体如下：

### 块级元素(block-level)

每个块元素通常都会独自占据一整行或多整行，可以对其设置宽度、高度、对齐等属性，常用于网页布局和网页结构的搭建。

```html
常见的块元素有: <h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>等，其中<div>标签是最典型的块元素。
```
块级元素的特点：

* 总是从新行开始
* 高度，行高、外边距以及内边距都可以控制
* 宽度默认是容器的100%
* 可以容纳内联元素和其他块元素

### 行内元素(inline-level)

行内元素（内联元素）不占有独立的区域，仅仅靠自身的字体大小和图像尺寸来支撑结构，一般不可以设置宽度、高度、对齐等属性，常用于控制页面中文本的样式。

```html
常见的行内元素有:<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>等，其中<span>标签最典型的行内元素。
```

行内元素的特点：

* 和相邻行内元素在一行上
* 高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效
* 默认宽度就是它本身内容的宽度
* 行内元素只能容纳文本或则其他行内元素（a特殊）

>注意：
1.只有 文字才 能组成段落  因此 p  里面不能放块级元素，同理还有这些标签h1,h2,h3,h4,h5,h6,dt，他们都是文字类块级标签，里面不能放其他块级元素。
2.链接里面不能再放链接。

### 块级元素和行内元素区别

块级元素的特点：

* 总是从新行开始
* 高度，行高、外边距以及内边距都可以控制
* 宽度默认是容器的100%
* 可以容纳内联元素和其他块元素

行内元素的特点：

* 和相邻行内元素在一行上
* 高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效
* 默认宽度就是它本身内容的宽度
* 行内元素只能容纳文本或则其他行内元素（a特殊）


### 行内块元素（inline-block）

在行内元素中有几个特殊的标签: &lt;img /&gt;、&lt;input /&gt;、&lt;td&gt;，可以对它们设置宽高和对齐属性，有些资料可能会称它们为行内块元素。

行内块元素的特点：
* 和相邻行内元素（行内块）在一行上,但是之间会有空白缝隙。
* 默认宽度就是它本身内容的宽度。
* 高度，行高、外边距以及内边距都可以控制。

### 标签显示模式转换 display

块转行内: display: inline;

行内转块: display: block;

块、行内元素转换为行内块： display: inline-block;

此阶段，我们只需关心这三个，其他的是我们后面的工作。

## CSS复合选择器

复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的,目的是为了可以选择更准确更精细的目标元素标签。

### 交集选择器

交集选择器由两个选择器构成，其中第一个为标签选择器，第二个为class选择器，两个选择器之间不能有空格，如h3.special。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_23-11-00.png">

比如：p.one 选择的是： 类名为 .one  的 段落 标签。  

用的相对来说比较少，不太建议使用。

### 并集选择器

并集选择器（CSS选择器分组）是各个选择器通过<strong style="color:#f00">逗号</strong>连接而成的，任何形式的选择器（包括标签选择器、class类选择器id选择器等），都可以作为并集选择器的一部分。如果某些选择器定义的样式完全相同，或部分相同，就可以利用并集选择器为它们定义相同的CSS样式。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_23-37-00.png">

比如  .one, p , #test {color: #F00;}  表示 .one 和 p  和 #test 这三个选择器都会执行颜色为红色。 通常用于集体声明。

### 后代选择器

后代选择器又称为包含选择器，用来选择元素或元素组的后代，其写法就是把外层标签写在前面，内层标签写在后面，中间用空格分隔。当标签发生嵌套时，内层标签就成为外层标签的后代。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_23-40-00.png">

子孙后代都可以这么选择。 或者说，它能选择任何包含在内的标签。 

### 子元素选择器

子元素选择器只能选择作为某元素子元素的元素。其写法就是把父级标签写在前面，子级标签写在后面，中间跟一个 &gt; 进行连接，注意，符号左右两侧各保留一个空格。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-10_23-43-00.png">

这里的子 指的是 儿子  不包含孙子 重孙子之类。

比如：.demo > h3 {color: red;}   说明  h3 一定是demo 的儿子、demo 元素包含着h3。

### 属性选择器

选取标签带有某些特殊属性的选择器 我们成为属性选择器。

<table>
  <tr>
    <th>选择器</th>
    <th>描述</th>
  </tr>
  <tr>
    <td>[attribute]</td>
    <td>用于选取带有指定属性的元素。</td>
  </tr>
  <tr>
    <td>[attribute=value]</td>
    <td>用于选取带有指定属性和值的元素。</td>
  </tr>
  <tr>
    <td>[attribute~=value]</td>
    <td>用于选取属性值中包含指定词汇的元素。</td>
  </tr>
  <tr>
    <td>[attribute|=value]</td>
    <td>用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。</td>
  </tr>
  <tr>
    <td>[attribute^=value]</td>
    <td>匹配属性值以指定值开头的每个元素。</td>
  </tr>
  <tr>
    <td>[attribute$=value]	</td>
    <td>匹配属性值以指定值结尾的每个元素。</td>
  </tr>
  <tr>
    <td>[attribute*=value]</td>
    <td>匹配属性值中包含指定值的每个元素。</td>
  </tr>
</table>

```css
/* 获取到 拥有 该属性的元素 */
div[class^=font] {
  /* class^=font 表示 font 开始位置就行了 */
  color: pink;
}
div[class$=footer] { 
  /* class$=footer 表示 footer 结束位置就行了 */
  color: skyblue;
}
div[class*=tao] { 
  /* class*=tao  *=  表示tao 在任意位置都可以 */
  color: green;
}
```

```html
<div class="font12">属性选择器</div>
<div class="font12">属性选择器</div>
<div class="font24">属性选择器</div>
<div class="font24">属性选择器</div>
<div class="font24">属性选择器</div>
<div class="24font">属性选择器123</div>
<div class="sub-footer">属性选择器footer</div>
<div class="jd-footer">属性选择器footer</div>
<div class="news-tao-nav">属性选择器</div>
<div class="news-tao-header">属性选择器</div>
<div class="tao-header">属性选择器</div>
```

#### 存在和值（Presence and value）属性选择器节
这些属性选择器尝试匹配精确的属性值：

- [attr]: 该选择器选择包含 attr 属性的所有元素，不论 attr 的值为何。
- [attr=val]: 该选择器仅选择 attr 属性被赋值为 val 的所有元素。
- [attr~=val]: 该选择器仅选择具有 attr 属性的元素，而且要求 val 值是 attr 值包含的被空格分隔的取值列表里中的一个。

让我们看一个特别的例子，下面是它的的HTML代码： 

```html
我的食谱配料: <i lang="fr-FR">Poulet basquaise</i>
<ul>
  <li data-quantity="1kg" data-vegetable>Tomatoes</li>
  <li data-quantity="3" data-vegetable>Onions</li>
  <li data-quantity="3" data-vegetable>Garlic</li>
  <li data-quantity="700g" data-vegetable="not spicy like chili">Red pepper</li>
  <li data-quantity="2kg" data-meat>Chicken</li>
  <li data-quantity="optional 150g" data-meat>Bacon bits</li>
  <li data-quantity="optional 10ml" data-vegetable="liquid">Olive oil</li>
  <li data-quantity="25cl" data-vegetable="liquid">White wine</li>
</ul>
```

和一个简单的样式表：

```css
/* 所有具有"data-vegetable"属性的元素将被应用绿色的文本颜色 */
[data-vegetable] {
  color: green
}

/* 所有具有"data-vegetable"属性且属性值刚好为"liquid"的元素将被应用金色的背景颜色 */
[data-vegetable="liquid"] {
  background-color: goldenrod;
}

/* 所有具有"data-vegetable"属性且属性值包含"spicy"的元素，
即使元素的属性中还包含其他属性值，都会被应用红色的文本颜色 */
[data-vegetable~="spicy"] {
  color: red;
}
```

### 伪元素选择器（CSS3)

* E::first-letter文本的第一个单词或字（如中文、日文、韩文等）
* E::first-line 文本第一行
* E::selection 可改变选中文本的样式

```css
p::first-letter {
  font-size: 20px;
  color: hotpink;
}

/* 首行特殊样式 */
p::first-line {
  color: skyblue;
}

p::selection {
  /* font-size: 50px; */
  color: orange;
}
```

* E::before和E::after

在E元素内部的开始位置和结束位创建一个元素，该元素为行内元素，且必须要结合content属性使用。

```css
div::before {
  content:"开始";
}
div::after {
  content:"结束";
}
```

E:after、E:before 在旧版本里是伪元素，CSS3的规范里“:”用来表示伪类，“::”用来表示伪元素，但是在高版本浏览器下E:after、E:before会被自动识别为E::after、E::before，这样做的目的是用来做兼容处理。

E:after、E:before后面的练习中会反复用到，目前只需要有个大致了解。

":" 与 "::" 区别在于区分伪类和伪元素

## CSS书写规范

开始就形成良好的书写规范，是你专业化的开始。

### 空格规范

【强制】 选择器 与 { 之间必须包含空格。

示例： .selector { }

【强制】 属性名 与之后的 : 之间不允许包含空格， : 与 属性值 之间必须包含空格。

示例：

font-size: 12px;

### 选择器规范

【强制】 当一个 rule 包含多个 selector 时，每个选择器声明必须独占一行。

示例：

```css
/* 正例 */
.post,
.page,
.comment {
    line-height: 1.5;
}

/* 反例 */
.post, .page, .comment {
    line-height: 1.5;
}
```

【建议】 选择器的嵌套层级应不大于 3 级，位置靠后的限定条件应尽可能精确。

示例：

```css
/* 正例 */
#username input {}
.comment .avatar {}

/* 反例 */
.page .header .login #username input {}
.comment div * {}
```

### 属性规范

【强制】 属性定义必须另起一行。

示例：

```css
/* 正例 */
.selector {
    margin: 0;
    padding: 0;
}

/* 反例 */
.selector { margin: 0; padding: 0; }
```

【强制】 属性定义后必须以分号结尾。

示例：

```css
/* 正例 */
.selector {
    margin: 0;
}

/* 反例 */
.selector {
    margin: 0
}
```

## CSS 背景(background)

CSS 可以添加背景颜色和背景图片，以及来进行图片设置。

| 属性                        |说明            |
|----------------------------|--------------- |
| background-color           | 背景颜色        |
| background-image           | 背景图片地址     |
| background-repeat          | 是否平铺        |
| background-position        | 背景位置        |
| background-attachment      | 背景固定还是滚动 |

背景的合写（复合属性）

```css                                       
background: 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置 
```

### 背景图片(image)

语法： 

```css
background-image: none | url (url) 
```

参数： 

none: 无背景图（默认的）
url: 使用绝对或相对地址指定背景图像 

background-image 属性允许指定一个图片展示在背景中（只有CSS3才可以多背景）可以和 background-color 连用。 如果图片不重复地话，图片覆盖不到地地方都会被背景色填充。 如果有背景图片平铺，则会覆盖背景颜色。

>小技巧：  
我们提倡 背景图片后面的地址，url不要加引号。

### 背景平铺（repeat）

语法： 

```css
background-repeat: repeat | no-repeat | repeat-x | repeat-y 
```

参数： 

repeat: 背景图像在纵向和横向上平铺（默认的）

no-repeat: 背景图像不平铺

repeat-x: 背景图像在横向上平铺

repeat-y: 背景图像在纵向平铺 

### 背景位置(position)

语法： 

```css
background-position: length || length

background-position: position || position 
```

参数： 

length: 百分数 | 由浮点数字和单位标识符组成的长度值。
position: top | center | bottom | left | center | right 

说明： 

设置或检索对象的背景图像位置。必须先指定background-image属性。默认值为：(0% 0%)。
如果只指定了一个值，该值将用于横坐标。纵坐标将默认为50%。第二个值将用于纵坐标。

>注意：
1.position 后面是x坐标和y坐标。 可以使用方位名词或者精确单位。
2.如果和精确单位和方位名字混合使用，则必须是x坐标在前，y坐标后面。比如 background-position: 15px top;   则 15px 一定是  x坐标   top是 y坐标。

实际工作用的最多的，就是背景图片居中对齐了。

### 背景附着

设置或检索背景图像是随对象内容滚动还是固定的。

语法： 

```css
background-attachment: scroll | fixed 
```

参数： 

scroll : 背景图像是随对象内容滚动
fixed : 背景图像固定 

### 背景简写

background属性的值的书写顺序官方并没有强制标准的。为了可读性，建议大家如下写：

background:背景颜色 背景图片地址 背景平铺 背景滚动 背景位置

```css
background: transparent url(image.jpg) repeat-y  scroll 50% 0 ;
```

### 背景透明(CSS3)

CSS3支持背景半透明的写法语法格式是:

```css
background: rgba(0,0,0,0.3);
```

最后一个参数是alpha 透明度  取值范围 0~1之间

>注意：背景半透明是指盒子背景半透明， 盒子里面的内容不收影响。

### 背景缩放(CSS3)

通过background-size设置背景图片的尺寸，就像我们设置img的尺寸一样，在移动Web开发中做屏幕适配应用非常广泛。

其参数设置如下：

1. 可以设置长度单位(px)或百分比（设置百分比时，参照盒子的宽高；设置px的时候，尽量之改一个值，防止失真，改的那个值是宽度）
2. 设置为cover时，会自动调整缩放比例，保证图片始终填充满背景区域，如有溢出部分则会被隐藏。
**我们平时用的cover 最多**
3. 设置为contain会自动调整缩放比例，保证图片始终完整显示在背景区域。

```css
background-image: url('images/gyt.jpg');
			background-size: 300px 100px;
			/* background-size: contain; */
			/* background-size: cover; */
```

### 导航栏案例

#### 文本的装饰

text-decoration   通常我们用于给链接修改装饰效果

| 值           | 描述                                          |
|--------------|-----------------------------------------------|
| none         | 默认。定义标准的文本。                        |
| underline    | 定义文本下的一条线。下划线 也是我们链接自带的 |
| overline     | 定义文本上的一条线。                          |
| line-through | 定义穿过文本下的一条线。                      |

**使用技巧**：在一行内的盒子内，我们设定行高等于盒子的高度，就可以使文字垂直居中。

```html
<head>
  <meta charset="utf-8">
  <style>
    body {
      background-color: #000;
    }
    a {
      width: 200px;
      height: 50px;
      /* background-color: orange; */
      display: inline-block;  /* 把a 行内元素转换为行内块元素 */
      text-align: center;  /* 文字水平居中 */
      line-height: 50px;  /* 我们设定行高等于盒子的高度，就可以使文字垂直居中 */
      color: #fff;
      font-size: 22px;
      text-decoration: none;  /* 取消下划线 文本装饰 */
      }
    a:hover {  /* 鼠标经过 给我们的链接添加背景图片*/
      background: url(images/h.png) no-repeat; 
    }
  </style>
</head>
<body>
  <a href="#">专区说明</a>
  <a href="#">申请资格</a>
  <a href="#">兑换奖励</a>
  <a href="#">下载游戏</a>
</body>
```

## CSS 三大特性

层叠、继承、优先级 是我们学习CSS 必须掌握的三个特性。

### CSS层叠性

所谓层叠性是指多种CSS样式的叠加。

是浏览器处理冲突的一个能力,如果一个属性通过两个相同选择器设置到同一个元素上，那么这个时候一个属性就会将另一个属性层叠掉

比如先给某个标签指定了内部文字颜色为红色，接着又指定了颜色为蓝色，此时出现一个标签指定了相同样式不同值的情况，这就是样式冲突。

一般情况下，如果出现样式冲突，则会按照CSS书写的顺序，以最后的样式为准。

1. 样式冲突，遵循的原则是就近原则。 那个样式离着结构近，就执行那个样式。
2. 样式不冲突，不会层叠

###  CSS继承性

所谓继承性是指书写CSS样式表时，子标签会继承父标签的某些样式，如文本颜色和字号。想要设置一个可继承的属性，只需将它应用于父元素即可。

>注意：恰当地使用继承可以简化代码，降低CSS样式的复杂性。子元素可以继承父元素的样式（text-，font-，line-这些元素开头的都可以继承，以及color属性）

### CSS优先级

定义CSS样式时，经常出现两个或更多规则应用在同一元素上，这时就会出现优先级的问题。

在考虑权重时，初学者还需要注意一些特殊的情况，具体如下：

* 继承样式的权重为0。即在嵌套结构中，不管父元素样式的权重多大，被子元素继承时，他的权重都为0，也就是说子元素定义的样式会覆盖继承来的样式。

* 行内样式优先。应用style属性的元素，其行内样式的权重非常高，可以理解为远大于100。总之，他拥有比上面提高的选择器都大的优先级。

* 权重相同时，CSS遵循就近原则。也就是说靠近元素的样式具有最大的优先级，或者说排在最后的样式优先级最大。

* CSS定义了一个!important命令，该命令被赋予最大的优先级。也就是说不管权重如何以及样式位置的远近，!important都具有最大优先级。

#### CSS特殊性（Specificity）

关于CSS权重，我们需要一套计算公式来去计算，这个就是 CSS Specificity，我们称为CSS 特性或称非凡性，它是一个衡量CSS值优先级的一个标准 具体规范入如下：

specificity用一个四位的数 字串(CSS2是三位)来表示，更像四个级别，值从左到右，左面的最大，一级大于一级，数位之间没有进制，级别之间不可超越。 

| 继承或者* 的贡献值       | 0,0,0,0  |
|-----------------------|----------|
| 每个元素（标签）贡献值为  | 0,0,0,1  |
| 每个类，伪类贡献值为     | 0,0,1,0  |
| 每个ID贡献值为          | 0,1,0,0  |
| 每个行内样式贡献值       | 1,0,0,0  |
| 每个!important贡献值    | ∞ 无穷大  |


总结优先级：

1. 使用了 !important声明的规则。
2. 内嵌在 HTML 元素的 style属性里面的声明。
3. 使用了 ID 选择器的规则。
4. 使用了类选择器、属性选择器、伪元素和伪类选择器的规则。
5. 使用了元素选择器的规则。
6. 只包含一个通用选择器的规则。
7. 同一类选择器则遵循就近原则。

>权重是优先级的算法，层叠是优先级的表现

## 盒子模型（CSS重点）

其实，CSS就三个大模块：盒子模型、浮动、定位，其余的都是细节。要求这三部分，无论如何也要学的非常精通。  

所谓盒子模型就是把HTML页面中的元素看作是一个矩形的盒子，也就是一个盛装内容的容器。每个矩形都由元素的内容、内边距（padding）、边框（border）和外边距（margin）组成。

### 看透网页布局的本质

网页布局中，我们是如何把里面的文字，图片，按照美工给我们的效果图排列的整齐有序呢？

把网页元素比如文字图片等等，放入盒子里面，然后利用CSS摆放盒子的过程，就是网页布局。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_20-56-00.png">

### 盒子模型（Box Model）

所有的文档元素（标签）都会生成一个矩形框，我们成为元素框（element box），它描述了一个文档元素再网页布局汇总所占的位置大小。因此，<strong style="color: #f00;">每个盒子除了有自己大小和位置外，还影响着其他盒子的大小和位置。</strong>

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_21-02-00.png">

### 盒子边框（border）

语法： 

```css
border: border-width || border-style || border-color 
```

边框属性—设置边框样式（border-style）

边框样式用于定义页面中边框的风格，常用属性值如下：

* none: 没有边框即忽略所有边框的宽度（默认值）
* solid: 边框为单实线(最为常用的)
* dashed: 边框为虚线  
* dotted: 边框为点线
* double: 边框为双实线

#### 盒子边框写法总结表

| 设置内容     | 样式属性                                                                                                 | 常用属性值                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| 上边框       | border-top-style: 样式; border-top-width: 宽度;border-top-color: 颜色;border-top: 宽度 样式 颜色;              |                                                            |
| 下边框       | border-bottom-style: 样式;border- bottom-width: 宽度;border- bottom-color:颜色;border-bottom: 宽度 样式 颜色; |                                                            |
| 左边框       | border-left-style: 样式; border-left-width: 宽度;border-left-color: 颜色;border-left: 宽度 样式 颜色;          |                                                            |
| 右边框       | border-right-style: 样式;border-right-width: 宽度;border-right-color: 颜色;border-right: 宽度 样式 颜色;       |                                                            |
| 样式综合设置 | border-style: 上边 [右边 下边 左边];                                                                        | none无（默认）、solid单实线、dashed虚线、dotted点线、double双实线 |
| 宽度综合设置 | border-width: 上边 [右边 下边 左边];                                                                        | 像素值                                                      |
| 颜色综合设置 | border-color: 上边 [右边 下边 左边];                                                                        | 颜色值、#十六进制、rgb(r,g,b)、rgb(r%,g%,b%)                   |
| 边框综合设置 | border: 四边宽度 四边样式 四边颜色;                                                                          |                                                             |

#### 表格的细线边框

table{ border-collapse: collapse; }  collapse 单词是合并的意思

border-collapse: collapse; 表示边框合并在一起。

### 内边距（padding）

padding属性用于设置内边距。  是指 边框与内容之间的距离。

* padding-top: 上内边距
* padding-right: 右内边距
* padding-bottom:下 内边距
* padding-left: 左内边距

>注意：后面跟几个数值表示的意思是不一样的。

| 值的个数  | 表达意思                                                                                                            |
|----------|-------------------------------------------------------------------------------------------------------------------|
| 1个值    | padding: 上下左右边距 比如padding: 3px; 表示上下左右都是3像素                                                            |
| 2个值    | padding: 上下边距 左右边距 比如 padding: 3px 5px; 表示 上下3像素 左右 5像素                                               |
| 3个值    | padding: 上边距 左右边距 下边距 比如 padding: 3px 5px 10px; 表示 上是3像素 左右是5像素 下是10像素                            |
| 4个值    | padding:上内边距 右内边距 下内边距 左内边距 比如: padding: 3px 5px 10px 15px; 表示 上3px 右是5px 下 10px 左15px   **顺时针** |

### 外边距（margin）

margin属性用于设置外边距。  设置外边距会在元素之间创建“空白”， 这段空白通常不能放置其他内容。

* margin-top: 上外边距
* margin-right: 右外边距
* margin-bottom: 下外边距
* margin-left: 上外边距
* margin: 上外边距 右外边距  下外边距  左外边

取值顺序跟内边距相同。

#### 外边距实现盒子居中

可以让一个盒子实现水平居中，需要满足一下两个条件：

1. 必须是块级元素。     
2. 盒子必须指定了宽度（width）

然后就给**左右的外边距都设置为auto**，就可使块级元素水平居中。

实际工作中常用这种方式进行网页布局，示例代码如下：

```css
.header{ width: 960px; margin: 0 auto;}
```

#### 文字盒子居中图片和背景区别

1.  文字水平居中是  text-align: center
2.  盒子水平居中  左右margin 改为 auto 

```css
text-align: center; /*  文字居中水平 */
margin: 10px auto;  /* 盒子水平居中  左右margin 改为 auto 就可以了 */
```

3. 插入图片 我们用的最多 比如产品展示类
4. 背景图片我们一般用于小图标背景 或者 超大背景图片

```css
section img {  
  width: 200px;/* 插入图片更改大小 width 和 height */
  height: 210px;
  margin-top: 30px;  /* 插入图片更改位置 可以用margin 或padding  盒模型 */
  margin-left: 50px; /* 插入当图片也是一个盒子 */
}

aside {
  width: 400px;
  height: 400px;
  border: 1px solid purple;
  background: #fff url(images/sun.jpg) no-repeat;

  background-size: 200px 210px; /*  背景图片更改大小只能用 background-size */
  background-position: 30px 50px; /* 背景图片更该位置 我用 background-position */
}
```

#### 清除元素的默认内外边距

为了更方便地控制网页中的元素，制作网页时，可使用如下代码清除元素的默认内外边距： 

~~~css
* {
   padding: 0;         /* 清除内边距 */
   margin: 0;          /* 清除外边距 */
}
~~~

>注意：
1.行内元素是只有左右外边距的，是没有上下外边距的。 内边距，在ie6等低版本浏览器也会有问题。
2.我们尽量不要给行内元素指定上下的内外边距就好了。

### 外边距合并

使用margin定义块元素的垂直外边距时，可能会出现外边距的合并。

#### 相邻块元素垂直外边距的合并

当上下相邻的两个块元素相遇时，如果上面的元素有下外边距margin-bottom，下面的元素有上外边距margin-top，则他们之间的垂直间距不是margin-bottom与margin-top之和，而是两者中的较大者。这种现象被称为相邻块元素垂直外边距的合并（也称外边距塌陷）。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_21-40-00.png">

解决方案：避免就好了。

#### 嵌套块元素垂直外边距的合并

对于两个嵌套关系的块元素，如果父元素没有上内边距及边框，则父元素的上外边距会与子元素的上外边距发生合并，合并后的外边距为两者中的较大者，即使父元素的上外边距为0，也会发生合并。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_21-51-00.png">

解决方案：

1. 可以为父元素定义1像素的上边框或上内边距。
2. 可以为父元素添加overflow: hidden。

### content宽度和高度

使用宽度属性width和高度属性height可以对盒子的大小进行控制。

width和height的属性值可以为不同单位的数值或相对于父元素的百分比%，实际工作中最常用的是像素值。

大多数浏览器，如Firefox、IE6及以上版本都采用了W3C规范，符合CSS规范的盒子模型的总宽度和总高度的计算原则是：

```css
  /*外盒尺寸计算（元素空间尺寸）*/
  Element空间高度 = content height + padding + border + margin
  Element 空间宽度 = content width + padding + border + margin
  /*内盒尺寸计算（元素实际大小）*/
  Element Height = content height + padding + border （Height为内容高度）
  Element Width = content width + padding + border （Width为内容宽度）
```

>注意：

1. 宽度属性width和高度属性height仅适用于块级元素，对行内元素无效（img标签和 input除外）。
2. 计算盒子模型的总高度时，还应考虑上下两个盒子垂直外边距合并的情况。
3. **如果一个盒子没有给定宽度/高度或者继承父亲的宽度/高度，则padding 不会影响本盒子大小**。

### 盒子模型布局稳定性

开始学习盒子模型，同学们最大的困惑就是， 分不清内外边距的使用，什么情况下使用内边距，什么情况下使用外边距？

答案是：  其实他们大部分情况下是可以混用的。  就是说，你用内边距也可以，用外边距也可以。 你觉得哪个方便，就用哪个。

但是，总有一个最好用的吧，我们根据稳定性来分，建议如下：

按照 优先使用  宽度 （width）  其次 使用内边距（padding）    再次  外边距（margin）。   

原因：

1. margin 会有外边距合并 还有 ie6下面margin 加倍的bug（讨厌）所以最后使用。

2. padding  会影响盒子大小， 需要进行加减计算（麻烦） 其次使用。

3. width   没有问题（嗨皮）我们经常使用宽度剩余法 高度剩余法来做。

### CSS3盒模型

CSS3中可以通过box-sizing 来指定盒模型，即可指定为content-box、border-box，这样我们计算盒子大小的方式就发生了改变。

可以分成两种情况：

1. box-sizing: content-box  盒子大小为 width + padding + border   content-box:此值为其默认值，其让元素维持W3C的标准Box Mode

2. box-sizing: border-box  盒子大小为 width    就是说  padding 和 border 是包含到width里面的

注：上面的标注的width指的是CSS属性里设置的width: length，content的值是会自动调整的。

```css
div {
  width: 100px;
  height: 100px;
  background: skyblue;
  margin: 0 auto;
  border: 1px solid gray;
  box-sizing: border-box;
}
  /* 
  content-box是默认的设置，如果我们添加了 border属性 该容器的大小会发生改变
  因为他要优先保证内部的内容所占区域不变
  */

  /*  
  box-sizing  如果不设置 默认的值 就是 
  content-box: 优先保证内容的大小 对盒子进行缩放;
  border-box: 让盒子优先保证自己所占区域的大小,对内容进行压缩;
  */
```

## 浮动(float)

### 普通流(normal flow)

这个单词很多人翻译为 文档流 ， 字面翻译 普通流 或者标准流都可以。

前面我们说过，网页布局的核心，就是用CSS来摆放盒子位置。如何把盒子摆放到合适的位置？  

CSS的定位机制有3种：普通流（标准流）、浮动和定位。

html语言当中另外一个相当重要的概念------普通流（标准流）。普通流实际上就是一个网页内标签元素正常从上到下，从左到右排列顺序的意思，比如块级元素会独占一行，行内元素会按顺序依次前后排列；按照这种大前提的布局排列之下绝对不会出现例外的情况叫做普通流布局。

### 浮动(float)

浮动最早是用来控制图片，以便达到其他元素（特别是文字）实现“环绕”图片的效果。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-02-00.png" width = "50%">

后来，我们发现浮动有个很有意思的事情：就是让任何盒子可以一行排列,因此我们就慢慢的偏离主题，用浮动的特性来布局了。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-05-00.png" width = "50%">

### 什么是浮动？

元素的浮动是指设置了浮动属性的元素会脱离标准普通流的控制，移动到其父元素中指定位置的过程。

在CSS中，通过float属性来定义浮动，其基本语法格式如下：

```css
选择器 {float: 属性值;}
```

| 属性值 | 描述                 |
|--------|--------------------|
| left   | 元素向左浮动         |
| right  | 元素向右浮动         |
| none   | 元素不浮动（默认值）  |

### 浮动详细内幕特性

浮动首先创建包含块的概念（包裹）。就是说， 浮动的元素总是找距离它最近的父级元素对齐。但是不会超出内边距的范围。 

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-17-00.jpg" width = "50%">

浮动的元素排列位置，跟上一个元素（块级）有关系。如果上一个元素有浮动，则A元素顶部会和上一个元素的顶部对齐；如果上一个元素是标准流，则A元素的顶部会和上一个元素的底部对齐。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-20-00.jpg" width = "50%">

由2可以推断出，一个父盒子里面的子盒子，如果其中一个子级有浮动的，则其他子级都需要浮动。这样才能一行对齐显示。

浮动脱离标准流，不占位置，会影响标准流。浮动只有左右浮动。

元素添加浮动后，元素会具有行内块元素的特性。元素的大小完全取决于定义的大小或者默认的内容多少

浮动根据元素书写的位置来显示相应的浮动。

## 清除浮动

### 为什么要清除浮动

我们前面说过，浮动本质是用来做一些文字混排效果的，但是被我们拿来做布局用，则会有很多的问题出现，但是，你不能说浮动不好 。 

由于浮动元素不再占用原文档流的位置，所以它会对后面的元素排版产生影响，为了解决这些问题，此时就需要在该元素中清除浮动。

准确的说，不是清除浮动，**而是清除浮动造成的影响**。

### 清除浮动本质

清除浮动主要为了解决父级元素因为子级浮动引起内部高度为0 的问题。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-25-00.jpg" width = "60%">

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-29-00.jpg" width = "60%">

### 清除浮动的方法

其实本质叫做闭合浮动更好一些, 记住，清除浮动就是把浮动的盒子圈到里面，让父盒子闭合出口和入口不让他们出来影响其他元素。

在CSS中，clear属性用于清除浮动，其基本语法格式如下：

```css
选择器 {clear: 属性值;}
```

| 属性值 | 描述                                 |
|--------|-------------------------------------|
| left   | 不允许左侧有浮动元素（清除左侧浮动的影响） |
| right  | 不允许右侧有浮动元素（清除右侧浮动的影响） |
| both   | 同时清除左右两侧浮动的影响              |

#### 额外标签法

```html
W3C推荐的做法是通过在浮动元素末尾添加一个空的标签例如 <div style=”clear: both”></div>
或则其他标签br等亦可。
```

优点：通俗易懂，书写方便

缺点：添加许多无意义的标签，结构化较差。

#### 父级添加overflow属性方法

可以通过触发BFC的方式，可以实现清除浮动效果。（BFC后面讲解）

```css
可以给父级添加：overflow为 hidden|auto|scroll  都可以实现。
```

优点：代码简洁

缺点：内容增多时候容易造成不会自动换行导致内容被隐藏掉，无法显示需要溢出的元素。

#### 使用after伪元素清除浮动

使用方法：

```css
 .clearfix:after {content: "."; display: block; height: 0; clear: both; visibility: hidden;}   

 .clearfix {*zoom: 1;}   /* IE6、7 专有 */
```

>注意：
content:"."  里面尽量跟一个小点，或者其他，尽量不要为空，否则再firefox 7.0前的版本会有生成空格。

优点：符合闭合浮动思想  结构语义化正确

缺点：由于IE6-7不支持:after，使用 zoom:1触发 hasLayout。

代表网站：百度、淘宝网、网易等

#### 使用before和after双伪元素清除浮动

使用方法：

```css
.clearfix:before,.clearfix:after { 
  content: ".";
  display: table;	/*触发BFC，防止外边距合并*/
}
.clearfix:after {
 clear: both;
}
.clearfix {
  *zoom: 1;
}
```

优点：代码更简洁

缺点：由于IE6-7不支持:after，使用 zoom:1触发 hasLayout。

代表网站：小米、腾讯等

## 版心和布局流程

阅读报纸时容易发现，虽然报纸中的内容很多，但是经过合理地排版，版面依然清晰、易读。同样，在制作网页时，要想使页面结构清晰、有条理，也需要对网页进行“排版”。

“版心”是指网页中主体内容所在的区域。一般在浏览器窗口中水平居中显示，常见的宽度值为960px、980px、1000px、1200px等。

### 布局流程

为了提高网页制作的效率，布局时通常需要遵守一定的布局流程，具体如下：

1. 确定页面的版心（可视区）。

2. 分析页面中的行模块，以及每个行模块中的列模块。

3. 制作HTML页面，CSS文件。

4. CSS初始化，然后开始运用盒子模型的原理，通过DIV+CSS布局来控制网页的各个模块。

### 一列固定宽度且居中

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_22-57-00.jpg" width = "50%">

最普通的，最为常用的结构

### 两列左窄右宽型

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_23-00-00.jpg" width = "50%">

比如: <a href="http://www.mi.com" target="_blank"> 小米官网 </a>

### 通栏平均分布型

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_23-03-00.jpg" width = "50%">

比如: <a href="http://www.smartisan.com/" target="_blank"> 锤子官网 </a>

## 定位(position)

如果，说浮动， 关键在一个 “浮” 字上面， 那么我们的定位，关键在于一个 “位” 上。

PS: 定位是我们CSS算是数一数二难点的了，但是，你务必要学好它，我们CSS离不开定位，特别是后面的js特效，天天和定位打交道。

### 为什么要用定位？

那么定位，最长运用的场景再那里呢？ 来看几幅图片，你一定会有感悟！

第一幅图， 小黄色块可以再图片上移动：

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_23-45-01.gif">

第二幅图， 左右箭头压住图片：

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_23-45-02.gif">

以上，如果用标准流或者浮动，实现会比较复杂或者难以实现，此时我们用定位来做。

### 元素的定位属性

元素的定位属性主要包括 定位模式 和 边偏移 两部分。

#### 边偏移

| 边偏移属性 | 描述                                     |
|------------|----------------------------------------|
| top        | 顶端偏移量，定义元素相对于其父元素上边线的距离 |
| bottom     | 底部偏移量，定义元素相对于其父元素下边线的距离 |
| left       | 左侧偏移量，定义元素相对于其父元素左边线的距离 |
| right      | 右侧偏移量，定义元素相对于其父元素右边线的距离 |

也就说，以后定位要和这边偏移搭配使用了， 比如 top: 100px;  left: 30px; 等等

#### 定位模式（定位的分类）

在CSS中，position属性用于定义元素的定位模式，其基本语法格式如下：

```css
选择器 {position: 属性值;}
```

position属性的常用值

| 值       | 描述                                      |
|----------|------------------------------------------|
| static   | 自动定位（默认定位方式）                     |
| relative | 相对定位，相对于其原文档流的位置进行定位        |
| absolute | 绝对定位，相对于其上一个已经定位的父元素进行定位 |
| fixed    | 固定定位，相对于浏览器窗口进行定位             |

### 静态定位(static)

静态定位是所有元素的默认定位方式，当position属性的取值为static时，可以将元素定位于静态位置。 所谓静态位置就是各个元素在HTML文档流中默认的位置。

在静态定位状态下，无法通过边偏移属性（top、bottom、left或right）来改变元素的位置。

一般用来清除定位的

### 相对定位(relative)

相对定位是将元素相对于它在 标准流 中的位置进行定位，当position属性的取值为relative时，可以将元素定位于相对位置。

对元素设置相对定位后，可以通过边偏移属性改变元素的位置，但是**它在文档流中的位置仍然保留**。如下图所示，即是一个相对定位的效果展示：

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-11_23-55-45.jpg">

>注意：    
1.相对定位最重要的一点是，它可以通过边偏移移动位置，但是原来的所占的位置，继续占有。
2.其次，每次移动的位置，是以自己的左上角为基点移动（相对于自己来移动位置）

就是说，相对定位的盒子仍在标准流中，它后面的盒子仍以标准流方式对待它。（相对定位不脱标）

如果说浮动的主要目的是 让多个块级元素一行显示，那么定位的主要价值就是 移动位置，让盒子到我们想要的位置上去。

### 绝对定位(absolute)

如果文档可滚动，绝对定位元素会随着它滚动，因为元素最终会相对于正常流的某一部分定位。

当position属性的取值为absolute时，可以将元素的定位模式设置为绝对定位。

>注意：
绝对定位最重要的一点是，它可以通过边偏移移动位置，**但是它完全脱标，完全不占位置**。

#### 父级没有定位

若所有父元素都没有定位，以浏览器为准对齐(document文档)。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-12_00-06-39.jpg">

#### 父级有定位

绝对定位是将元素依据最近的已经定位（绝对、固定或相对定位）的父元素（祖先）进行定位。 

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-12_00-08-16.jpg">

#### 绝对定位的盒子没有边偏移

如果只是给盒子指定了 定位，但是没有给与边偏移，则改盒子以标准流来显示排序，和上一个盒子的底边对齐，但是不占有位置。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-12_00-10-27.jpg">

#### 子绝父相

这个“子绝父相”太重要了，是我们学习定位的口诀，时时刻刻记住的。

这句话的意思是 子级是绝对定位的话， 父级要用相对定位。

首先，绝对定位是将元素依据最近的(已经定位绝对、固定或相对定位）的父元素（祖先）进行定位。

就是说，子级是绝对定位，父亲只要是定位即可（不管父亲是绝对定位还是相对定位，甚至是固定定位都可以），就是说， 子绝父绝，子绝父相都是正确的。

但是，

因为子级是绝对定位，不会占有位置， 可以放到父盒子里面的任何一个地方。

父盒子布局时，需要占有位置，因此父亲只能是 相对定位. 

这就是子绝父相的由来。

#### 绝对定位的盒子水平/垂直居中

普通的盒子是左右margin 改为 auto就可， 但是对于绝对定位就无效了

定位的盒子也可以水平或者垂直居中，有一个算法。

1. 首先left 50%   父盒子的一半大小

2. 然后走自己外边距负的一半值就可以了 margin-left。

### 固定定位fixed

固定定位是绝对定位的一种特殊形式，它以浏览器窗口作为参照物来定义网页元素。当position属性的取值为fixed时，即可将元素的定位模式设置为固定定位。

当对元素设置固定定位后，它将脱离标准文档流的控制，始终依据浏览器窗口来定义自己的显示位置。不管浏览器滚动条如何滚动也不管浏览器窗口的大小如何变化，该元素都会始终显示在浏览器窗口的固定位置。

固定定位有两点：

1. 固定定位的元素跟父亲没有任何关系，只认浏览器。
2. 固定定位完全脱标，不占有位置，不随着滚动条滚动。

ie6等低版本浏览器不支持固定定位。

### 叠放次序（z-index）

当对多个元素同时设置定位时，定位元素之间有可能会发生重叠。

<img src = "https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-12_00-19-05.jpg">

在CSS中，要想调整重叠定位元素的堆叠顺序，可以对定位元素应用z-index层叠等级属性，其取值可为正整数、负整数和0。

比如：z-index: 2;

>注意：
1.z-index的默认属性值是0，取值越大，定位元素在层叠元素中越居上。
2.如果取值相同，则根据书写顺序，后来居上。
3.后面数字一定不能加单位。
4.只有相对定位，绝对定位，固定定位有此属性，其余标准流，浮动，静态定位都无此属性，亦不可指定此属性。

### 四种定位总结

| 定位模式                     | 是否脱标占有位置     | 是否可以使用边偏移 | 移动位置基准                  |
|----------------------------|-------------------|-----------------|----------------------------- |
| 静态static                  | 不脱标，正常模式     | 不可             | 正常模式                     |
| 相对定位relative             | 不脱标，占有位置     | 可以             | 相对自身位置移动(自恋型)       |
| 绝对定位absolute             | 完全脱标，不占有位置 | 可               | 相对于定位父级移动位置（拼爹型） |
| 固定定位fixed（特殊的绝对定位） | 完全脱标，不占有位置 | 可以             | 相对于浏览器移动位置（认死理型） |

## 定位模式转换

跟浮动一样，元素添加了 绝对定位 和 固定定位 之后，元素模式也会发生转换， 都转换为 行内块 模式， 因此 比如 行内元素 如果添加了 绝对定位或者 固定定位后，可以不用转换模式，直接给高度和宽度就可以了。

## 元素的显示与隐藏

在CSS中有三个显示和隐藏的单词比较常见，我们要区分开，他们分别是 display visibility 和 overflow。

他们的主要目的是让一个元素在页面中消失，但是不在文档源码中删除。 最常见的是网站广告，当我们点击类似关闭不见了，但是我们重新刷新页面，它们又会出现和你玩躲猫猫！！

### display 显示

display 设置或检索对象是否及如何显示。

display: none 隐藏对象 与它相反的是 display: block 除了转换为块级元素之外，同时还有显示元素的意思。

特点：**隐藏之后，不再保留位置**。

### visibility 可见性

设置或检索是否显示对象。

visible: 对象可视

hidden: 对象隐藏

特点：**隐藏之后，继续保留原有位置**。

### overflow 溢出

检索或设置当对象的内容超过其指定高度及宽度时如何管理内容。

visible: 不剪切内容也不添加滚动条

auto: 超出自动显示滚动条，不超出不显示滚动条

hidden: 不显示超过对象尺寸的内容，超出的部分隐藏掉

scroll: 不管超出内容否，总是显示滚动条