
## 网页

网站是指指在因特网上根据一定的规则，使用HTML等制作的用于展示特定内容相关的网页的集合。

网页是构成网站的基本元素，它通常由图片、链接、文字、声音、视频等元素组成。通常我们看到的网页，
常见以 .html 或 .htm 后缀结尾的文件，因此将其俗称为HTML文件。

### HTML

HTML（英文Hyper Text Markup Language的缩写）中文译为“超文本标签语言”，主要是通过HTML标签对网页中的文本、图片、声音等内容进行描述。

### 网页的形成

网页是由元素组成的，这些元素是利用html标签描述出来，然后通过浏览器解析来显示给用户的。

## 常见浏览器

浏览器是网页、运行的平台，常用的浏览器有IE、火狐（Firefox）、谷歌（Chrome）、Safari和Opera等。平时称为五大浏览器。

### 浏览器内核      

负责读取网页内容，整理讯息，计算网页的显示方式并显示页面。

浏览器内核又可以分成两部分：渲染引擎(layout engineer 或者 Rendering Engine)和 JS 引擎。
渲染引擎 它负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入 CSS 等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。

JS 引擎 则是解析 Javascript 语言，执行 javascript语言来实现网页的动态效果。

| 浏览器 | 内核 | 备注 |
| --------- | ------- | -------------------------------------- |
| IE        | Trident | IE、猎豹安全浏览器、360极速浏览器、百度浏览器 |
| firefox   | Gecko   | Mozilla FireFox(火狐浏览器) |
| Safari    | webkit  | Safari 是苹果公司开发的浏览器 |
| chrome    | Bink    | Chrome 浏览器 |


## Web标准

Web 标准是由W3C组织和其他标准化组织制定的一系列标准的集合。W3C(万维网联盟)是国际最著名的标准化组织。

### Web 标准的好处

1. 让Web的发展前景更广阔 
2. 内容能被更广泛的设备访问
3. 更容易被搜寻引擎搜索
4. 降低网站流量费用
5. 使网站更易于维护
6. 提高页面浏览速度

### Web 标准构成

主要包括结构（Structure）、表现（Presentation）和行为（Behavior）三个方面。

* 结构标准：结构用于对网页元素进行整理和分类（html）。
* 样式标准：表现用于设置网页元素的版式、颜色、大小等外观样式（css）。
* 行为标准：行为是指网页模型的定义及交互的编写（JavaScript）。

Web标准提出的最佳体验方案：结构、样式、行为相分离。

## HTML 语法规范

### 基本语法概述

1. HTML标签是由尖括号宝威的关键词，例如 &lt;html&gt;。

2. HTML标签通常是成对出现的，例如 &lt;html&gt;和&lt;/html&gt;，我们成为 双标签。
标签中的第一个标签是开始标签，第二个标签是结束标签。

3. 有些特殊的标签必须是单个标签，例如 &lt;br /&gt;,我们成为 单标签。

### 标签关系

标签的关系可以分为两种，嵌套关系 和 并列关系

#### 嵌套关系

```html
<head>  
  <title> </title>  
</head>
```

#### 并列关系

```html
<head></head>
<body></body>
```

## HTML 基本结构标签

每个网页都会有一个基本的结构标签，页面内容也是在这些基本标签上书写。
HTML页面也成为HTML文档。

```html
<html>   
    <head>     
        <title></title>
    </head>
    <body>
    </body>
</html>
```

| 标签名             | 定义      | 说明                                   |
| ----------------- | -------- | -------------------------------------- |
| &lt;html&gt;      | html标签  | 页面中最大的标签，我们称为 根标签 |
| &lt;head&gt;      | 文档的头部 | 注意在head标签中我们必须要设置的标签是title |
| &lt;title&gt;     | 文档的标题 | 让页面拥有一个属于自己的标题 |
| &lt;body&gt;      | 文档的主体 | 元素包含文档的所有内容，页面内容 基本都是放到body里面的 |

### 文档类型 <!DOCTYPE>

```html
<!DOCTYPE html>
```

这句话就是告诉我们使用哪个html版本？我们使用的是 html 5 的版本。html有很多版本，那我们应该告诉用户和浏览器我们使用的版本号。

&lt;!DOCTYPE&gt;标签位于文档的最前面，用于向浏览器说明当前文档使用哪种 HTML 或 XHTML 标准规范，必需在开头处使用<!DOCTYPE>标签为所有的XHTML文档指定XHTML版本和类型，只有这样浏览器才能按指定的文档类型进行解析。#

### 字符集

```html
<meta charset="UTF-8">
```

* utf-8: 是目前最常用的字符集编码方式，常用的字符集编码方式还有gbk和gb2312

* gb2312: 简单中文 包括6763个汉字

* BIG5: 繁体中文 港澳台等用

* GBK: 包含全部中文字符 是GB2312的扩展，加入对繁体字的支持，兼容GB2312

>UTF-8则包含全世界所有国家需要用到的字符。

## HTML 标签

### HTML标签的语义化

所谓标签语义化，就是指标签的含义。

根据标签的语义，在合适的地方给一个最为合理的标签，可以让页面结构更清晰。

#### 为什么要有语义化标签

1. 方便代码的阅读和维护

2. 同时让浏览器或是网络爬虫可以很好地解析，从而更好分析其中的内容 

3. 使用语义化标签会具有更好地搜索引擎优化 

### 标签属性

属性就是特性 比如手机的颜色 尺寸..

使用HTML制作网页时，如果想让HTML标签提供更多的信息，可以使用HTML标签的属性加以设置。其基本语法格式如下：

```html
<标签名 属性1="属性值1" 属性2="属性值2" …> 内容 </标签名>
```

在上面的语法中：

1. 标签可以拥有多个属性，必须写在开始标签中，位于标签名后面。

2. 属性之间不分先后顺序，标签名与属性、属性与属性之间均以空格分开。

3. 任何标签的属性都有默认值，省略该属性则取默认值。

采取键值对 key="value"  的格式  

例如:  

```html
<hr width="400" />
```

>属性是 宽度 值是 400 

### 标题标签

为了使网页更具有语义化，我们经常会在页面中用到标题标签，HTML提供了6个等级的标题，即

```html
 <h1>、<h2>、<h3>、<h4>、<h5>、<h6>
```
单词缩写：head 头部、标题 

标签语义：作为标题使用，并且依据重要性递减。

特点：
1. 加了标题的文字会加粗，字号也会依次变大。
2. 一个标题独占一行。

### 段落标签

在网页中要把文字有条理地显示出来，就需要将这些文字分段显示。

```html
<p>文本内容</p>
```

单词缩写：paragraph 段落

标签语义：可以把HTML文档分割为若干段落。

特点：

1. 文本在一个段落中会根据浏览器窗口的大小自动换行。
2. 段落和段落之间保有空隙。

### 换行标签

在HTML中，一个段落中的文字会从左到右依次排列，直到浏览器窗口的右端，然后自动换行。如果希望某段文本强制换行显示，就需要使用换行标签。

```html
<br />
```

单词缩写：break 打断、换行

标签语义：强制换行

特点：
1. br是个单标签。
2. br标签只是简单地开始新的一行，与段落不同，段落之间会插入一些垂直的间距。

>练习案例：[体育新闻](https://github.com/senhao1104/front-end-notes/blob/master/01-HTML/HTML%E7%BB%83%E4%B9%A0%E6%A1%88%E4%BE%8B/01-%E4%BD%93%E8%82%B2%E6%96%B0%E9%97%BB.html)
### 文本格式化标签

在网页中，有时需要为文字设置粗体、斜体或下划线效果，这时就需要用到HTML中的文本格式化标签，使文字以特殊的方式显示。

标签语义：突出重要性，比普通文字更重要。

| 标签                                              | 语义    | 说明                     |
|---------------------------------------------------|--------|-------------------------|
| &lt;b&gt;&lt;/b&gt;或&lt;strong&gt;&lt;/strong&gt; | 加粗   | 推荐使用 &lt;strong&gt; 语义更强烈 |
| &lt;i&gt;&lt;/i&gt;或&lt;em&gt;&lt;/em&gt;         | 倾斜   | 推荐使用 &lt;em&gt; 语义更强烈     |
| &lt;s&gt;&lt;/s&gt;或&lt;del&gt;&lt;/del&gt;       | 删除线  | 推荐使用 &lt;del&gt; 语义更强烈    |
| &lt;u&gt;&lt;/u&gt;或&lt;ins&gt;&lt;/ins&gt;       | 下划线  | 推荐使用 &lt;ins&gt; 语义更强烈    |

#### &lt;div&gt; 和 &lt;span&gt; 标签

&lt;div&gt; 和 &lt;span&gt;是没有语义的，是我们网页布局用来装内容的盒子。

```html
<div>  </div> 

<span> </span>
```

div 就是 division 的缩写 分割，分区的意思 其实有很多div 来组合网页。

span, 跨度，跨距；范围    

特点：
1. &lt;div&gt;标签用来布局，大盒子
2. &lt;span&gt;标签用来布局，小盒子

### 图像标签

在HTML标签中，&lt;img&gt;标签用于定义HTML页面中的图像。

```html
<img src="图像URL" />
```

单词缩写：image 图像

该语法中src属性用于指定图像文件的路径和文件名，它是img标签的必需属性。


| 属性   | 属性值 | 描述                   |
|--------|--------|---------------------|
| src    | url    | 图像的路径            |
| alt    | 文本   | 图像无法显示时替换文本  |
| title  | 文本   | 鼠标悬停时显示的内容    |
| width  | 像素   | 设置图像的宽度         |
| height | 像素   | 设置图像的高度         |
| border | 数字   | 设置图像边框的宽度      |

### 超链接标签

在HTML标签中，&lt;a&gt;标签用于定义超链接，作用是从一个页面链接到另一个页面。

```html
<a href="跳转目标" target="目标窗口的弹出方式">文本或图像</a>
```

单词缩写：anchor 的缩写  基本解释 锚

| 属性   | 作用|
| ------| ------------------- |
| href  | 用于指定链接目标的url地址，当为标签应用href属性时，它就具有了超链接的功能（必须属性） |
| target| 用于指定链接页面的打开方式，其中_self为默认值，_blank为在新窗口中打开方式          |

注意：

1. 外部链接：

```html
<a href = "http:// www.baidu.com"> 百度 </a>
```
2. 内部链接：直接链接内部页面名称即可

```html
<a href="index.html"> 首页 </a >
```

3. 空链接：如果当时没有确定链接目标时，通常将链接标签的href属性值定义为“#”，表示该链接暂时为一个空链接。

```html
<a href="#"> 首页 </a >
```

4. 下载链接：如果 href 里面的地址是一个文件或者压缩包，就会下载这个文件。

```html
<a href="img.zip"> 下载文件 </a >
```
5. 不仅可以创建文本超链接，在网页中各种网页元素，如图像、表格、音频、视频等都可以添加超链接。

```html
<a href="http:// www.baidu.com"><img src="baidu.jpg" /></a >
```

### 锚点定位

通过创建锚点链接，用户能够快速定位到目标内容。
创建锚点链接分为两步：

```html
1.使用 <a href="#id名">链接文本</a> 创建链接文本。

2.使用相应的id名标注跳转目标的位置。
```

## base 标签

base 可以设置整体链接的打开状态。

base 写到  &lt;head&gt;  &lt;/head&gt;  之间。

```html
<base target="_blank" />
```

## 注释标签

在HTML中还有一种特殊的标签——注释标签。如果需要在HTML文档中添加一些便于阅读和理解但又不需要显示在页面中的注释文字，就需要使用注释标签。其基本语法格式如下：

```html
<!-- 注释语句 -->
```

注释内容不会显示在浏览器窗口中，但是作为HTML文档内容的一部分，也会被下载到用户的计算机上，查看源代码时就可以看到。

## 路径

实际工作中，通常新建一个文件夹专门用于存放图像文件，这时再插入图像，就需要采用“路径”的方式来指定图像文件的位置。

路径可以分为： 相对路径和绝对路径。

### 相对路径

1. 图像文件和HTML文件位于同一文件夹：只需输入图像文件的名称即可，如&lt;img src="logo.gif" /&gt;。
2. 图像文件位于HTML文件的下一级文件夹：输入文件夹名和文件名，之间用“/”隔开，如&lt;img src="img/img01/logo.gif" /&gt;。
3. 图像文件位于HTML文件的上一级文件夹：在文件名之前加入“../” ，如果是上两级，则需要使用 “../ ../”，以此类推，如&lt;img src="../logo.gif" /&gt;。

### 绝对路径

“D:\web\img\logo.gif”，或完整的网络地址，例如“http://www.xxx.cn/images/logo.gif”。

## 列表标签

容器里面装载着文字或图表的一种形式，叫列表。

列表最大的特点就是  整齐 、整洁、 有序。

### 无序列表 ul （重点）

无序列表的各个列表项之间没有顺序级别之分，是并列的。其基本语法格式如下：

```html
<ul>
  <li>列表项1</li>
  <li>列表项2</li>
  <li>列表项3</li>
  ......
</ul>
```

注意：
 1. &lt;ul&gt;&lt;/ul&gt;中只能嵌套&lt;li&gt;&lt;/li&gt;，直接在&lt;ul&gt;&lt;/ul&gt;标签中输入其他标签或者文字的做法是不被允许的。
 2. &lt;li&gt;&lt;/li&gt;之间相当于一个容器，可以容纳所有元素。
 3. 无序列表会带有自己样式属性，放下那个样式，让css来！

### 有序列表 ol （了解）

有序列表即为有排列顺序的列表，其各个列表项按照一定的顺序排列定义，有序列表的基本语法格式如下：

```html
<ol>
  <li>列表项1</li>
  <li>列表项2</li>
  <li>列表项3</li>
  ......
</ol>
```

所有特性基本与ul 一致,但是实际工作中较少用 ol..

### 自定义列表（理解）

定义列表常用于对术语或名词进行解释和描述，定义列表的列表项前没有任何项目符号。其基本语法如下：

```html
<dl>
  <dt>名词1</dt>
  <dd>名词1解释1</dd>
  <dd>名词1解释2</dd>
  ...
  <dt>名词2</dt>
  <dd>名词2解释1</dd>
  <dd>名词2解释2</dd>
  ...
</dl>
```

## 表格 table(会使用)

表格到现在还是较为常用的一种标签，但不是用来布局，常见处理、显示表格式数据。

### 创建表格

在HTML网页中，要想创建表格，就需要使用表格相关的标签。创建表格的基本语法格式如下：

```html
<table>
  <tr>
    <td>单元格内的文字</td>
    <td>单元格内的文字</td>
    ...
  </tr>
  ...
</table>
```

在上面的语法中包含三对HTML标签，分别为 &lt;table&gt;&lt;/table&gt;、&lt;tr&gt;&lt;/tr&gt;、&lt;td&gt;&lt;/td&gt;
他们是创建表格的基本标签，缺一不可，下面对他们进行具体地解释。

1. table：用于定义一个表格。
2. tr：用于定义表格中的一行，必须嵌套在 table 标签中，在 table 中包含几对 tr，就有几行表格。
3. td：用于定义表格中的单元格，必须嵌套在&lt;tr&gt;&lt;/tr&gt;标签中，一对&lt;tr&gt;&lt;/tr&gt;中包含几对&lt;td&gt;&lt;/td&gt;，就表示该行中有多少列（或多少个单元格）。

注意：
1. &lt;tr&gt;&lt;/tr&gt;中只能嵌套&lt;td&gt;&lt;/td&gt;
2. &lt;td&gt;&lt;/td&gt;标签，他就像一个容器，可以容纳所有的元素

### 表格属性

| 属性名       | 含义                                    | 常用属性值          |
|-------------|----------------------------------------|--------------------|
| border      | 设置表格的边框 （默认 border = "0" 无边框） | 像素值              |
| cellspacing | 设置单元格与单元格边框之间的空白间距         | 像素值(默认为2像  素) |
| cellpadding | 设置单元格内边距                          | 像素值(默认为2像素)   |
| width       | 设置表格的宽度                           | 像素值               |
| height      | 设置表格的高度                           | 像素值               |
| align       | 设置表格在网页中的水平对齐方式              | left、center、right |

### 表头标签

表头一般位于表格的第一行或第一列，其文本加粗居中，即为设置了表头的表格。设置表头非常简单，只需用表头标签&lt;th&gt;</th&gt;替代相应的单元格标签&lt;td&gt;</td&gt;即可。


### 表格结构（了解）


在使用表格进行布局时，可以将表格划分为头部、主体和页脚（页脚因为有兼容性问题，我们不在赘述）

&lt;thead&gt;&lt;/thead&gt;：用于定义表格的头部。
必须位于&lt;table&gt;&lt;/table&gt;标签中，一般包含网页的logo和导航等头部信息。

&lt;tbody&gt;&lt;/tbody&gt;：用于定义表格的主体。
位于&lt;table&gt;&lt;/table&gt;标签中，一般包含网页中除头部和底部之外的其他内容。

### 表格标题

定义和用法

caption 元素定义表格标题。

```html
<table>
   <caption>我是表格标题</caption>
</table>
```

caption 标签必须紧随 table 标签之后。您只能对每个表格定义一个标题。通常这个标题会被居中于表格之上。

### 合并单元格(难点)

跨行合并：rowspan 
跨列合并：colspan 

合并的顺序：先上 先左 

## 表单标签(掌握)

在HTML中，一个完整的表单通常由表单控件（也称为表单元素）、提示信息和表单域3个部分构成。

* 表单控件：
​包含了具体的表单功能项，如单行文本输入框、密码输入框、复选框、提交按钮、重置按钮等。

* 提示信息：
​一个表单中通常还需要包含一些说明性的文字，提示用户进行填写和操作。

* 表单域：  
​它相当于一个容器，用来容纳所有的表单控件和提示信息，可以通过他定义处理表单数据所用程序的url地址，以及数据提交到服务器的方法。如果不定义表单域，表单中的数据就无法传送到后台服务器。

### input 控件(重点)

在上面的语法中，&lt;input /&gt;标签为单标签，type属性为其最基本的属性，其取值有多种，用于指定不同的控件类型。除了type属性之外，&lt;input /&gt;标签还可以定义很多其他的属性，其常用属性如下表所示。

![image](https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-04_17-00-32.jpg)

###  label标签(理解)

label 标签为 input 元素定义标注（标签）。

作用：用于绑定一个表单元素, 当点击label标签的时候, 被绑定的表单元素就会获得输入焦点。

for 属性规定 label 与哪个表单元素绑定。

```html
<label for="male">Male</label>
<input type="radio" name="sex" id="male" value="male">
```

### textarea控件(文本域)

如果需要输入大量的信息，就需要用到&lt;textarea&gt;&lt;/textarea&gt;标签。通过textarea控件可以轻松地创建多行文本输入框，其基本语法格式如下：

```html
<textarea cols="每行中的字符数" rows="显示的行数">
  文本内容
</textarea>
```

### 下拉菜单

使用select控件定义下拉菜单的基本语法格式如下

```html
<select>
  <option>选项1</option>
  <option>选项2</option>
  <option>选项3</option>
  ...
</select>
```

注意：
1. &lt;select&gt;&lt;/select&gt;中至少应包含一对&lt;option&gt;&lt;/option&gt;。
2. 在 option 中定义selected ="selected"时，当前项即为默认选中项。

### 表单域

在HTML中，form标签被用于定义表单域，即创建一个表单，以实现用户信息的收集和传递，form中的所有内容都会被提交给服务器。创建表单的基本语法格式如下：

```html
<form action="url地址" method="提交方式" name="表单名称">
  各种表单控件
</form>
```

常用属性：
1. action
在表单收集到信息后，需要将信息传递给服务器进行处理，action属性用于指定接收并处理表单数据的服务器程序的url地址。
2. method
用于设置表单数据的提交方式，其取值为get或post。
3. name
用于指定表单的名称，以区分同一个页面中的多个表单。

注意：每个表单都应该有自己表单域。

## HTML5新标签与特性

![image](https://github.com/senhao114/front-end-notes/blob/master/99-images/2019-10-04_17-25-24.jpg)

### 文档类型设定

document:
* HTML: 输入html:4s
* XHTML: 输入html:xt
* HTML5: 输入 html:5 

```html
<!DOCTYPE html>
```

### 字符设定

```html
<meta http-equiv="charset" content="utf-8">  HTML与XHTML中建议这样去写
<meta charset="utf-8">  HTML5的标签中建议这样去写
```

### 常用新标签

w3c 手册中文官网     :   http://w3school.com.cn/

* header：定义文档的页眉 头部
* nav：定义导航链接的部分
* footer：定义文档或节的页脚 底部
* article：定义文章
* section：定义文档中的节（section、区段）
* aside：定义其所处内容之外的内容 侧边

```html
<header>定义页面的头部 页眉</header>
<nav>定义导航栏</nav> 
<footer>定义页面底部 页脚</footer>
<article>定义文章</article>
<section>定义区域</section>
<aside>定义其所处内容之外的内容 侧边</aside>
```

* datalist：定义选项列表。请与 input 元素配合使用该元素

```html
<input type="text" value="输入明星" list="star"/>  <!-- input里面用list -->
<datalist id="star">  <!-- datalist 里面用id来实现和input链接 -->  
    <option>刘德华</option>
    <option>郭富城</option>
    <option>张学友</option>
</datalist>
```

* fieldset 元素可将表单内的相关元素分组、打包，与legend 搭配使用

```html
<fieldset>
    <legend>用户登录</legend>  <!-- 标题 -->
    用户名: <input type="text"><br />
    密　码: <input type="password">
</fieldset>
```

## 新增的input type属性值：

| 类型      | 使用示例                 | 含义               |
|----------|-------------------------|-------------------|
| email    | <input type="email">    | 输入邮箱格式        |
| tel      | <input type="tel">      | 输入手机号码格式     |
| url      | <input type="url">      | 输入url格式        |
| number   | <input type="number">   | 输入数字格式        |
| search   | <input type="search">   | 搜索框（体现语义化） |
| range    | <input type="range">    | 自由拖动滑块        |
| time     | <input type="time">     | 小时分钟           |
| date     | <input type="date">     | 年月日             |
| datetime | <input type="datetime"> | 时间               |
| month    | <input type="month">    | 月年               |
| week     | <input type="week">     | 星期 年            |

## 常用新属性

| 属性          | 用法                                            | 含义                                                     |
|--------------|------------------------------------------------|----------------------------------------------------------|
| placeholder  | <input type="text" placeholder="请输入用户名">   | 占位符 当用户输入的时候 里面的文字消失 删除所有文字，自动返回    |
| autofocus    | <input type="text" autofocus>                  | 规定当页面加载时 input 元素应该自动获得焦点                    |
| multiple     | <input type="file" multiple>                   | 多文件上传                                                 |
| autocomplete | <input type="text" autocomplete="off">         | autocomplete 属性规定输入字段是否应该启用自动完成功能。         |
| required     | <input type="text" required>                   | 必填项  内容不能为空                                        |
| accesskey    | <input type="text" accesskey="s">              | 规定激活（使元素获得焦点）元素的快捷键 采用 alt + s 的形式      |

## 综合案例

```html
<form action="">
  <fieldset>
    <legend>学生档案</legend>
    <label for="userName">姓名:</label>
    <input type="text" name="userName" id="userName" placeholder="请输入用户名"> <br>
    <label for="userPhone">手机号码:</label>
    <input type="tel" name="userPhone" id="userPhone" pattern="^1\d{10}$"><br>
    <label for="email">邮箱地址:</label>
    <input type="email" required name="email" id="email"><br>
    <label for="collage">所属学院:</label>
    <input type="text" name="collage" id="collage" list="cList" placeholder="请选择"><br>
    <datalist id="cList">
      <option value="前端与移动开发学院"></option>
      <option value="java学院"></option>
      <option value="c++学院"></option>
    </datalist><br>
    <label for="score">入学成绩:</label>
    <input type="number" max="100" min="0" value="0" id="score"><br>
   <form action="">
    <fieldset>
    	<legend>学生档案</legend>
    	<label>姓名: <input type="text" placeholder="请输入学生名字"/></label> <br>
    	<label>手机号: <input type="tel" /></label> <br />
    	<label>邮箱: <input type="email" /></label> <br />
    	<label>所属学院:  <input type="text" placeholder="请选择学院" list="xueyuan"/>
    	<datalist id="xueyuan">
    	  <option>java学院</option>
    	  <option>前端学院</option>
    	  <option>php学院</option>
    	  <option>设计学院</option>
    	</datalist>
    	<br /><br />
    	<label>出生日期: <input type="date" /></label> <br>
    	<label>成绩: <input type="number" /></label> <br>
    	<label>毕业时间: <input type="date" /></label> <br>
    	<input type="submit" />  <input type="reset" />
    </fieldset>
    </form>
    <label for="inTime">入学日期:</label>
    <input type="date" id="inTime" name="inTime"><br>
    <label for="leaveTime">毕业日期:</label>
    <input type="date" id="leaveTime" name="leaveTime"><br>
    <input type="submit">
  </fieldset>
</form>
```

## 多媒体标签

* embed：标签定义嵌入的内容
* audio：播放音频
* video：播放视频

### 多媒体 embed（会使用）

embed可以用来插入各种多媒体，格式可以是 Midi、Wav、AIFF、AU、MP3等等。url为音频或视频文件及其路径，可以是相对路径或绝对路径。

```html
<embed src="helloworld.swf" />
```
### 多媒体 audio

HTML5通过<audio>标签来解决音频播放的问题。

```html
<!-- 通过src属性指定音频路径即可 -->
<audio src="./music/See You Again.mp3"></audio>
```

并且可以通过附加属性可以更友好控制音频的播放，如：
* autoplay 自动播放
* controls 是否显不默认播放控件
* loop 循环播放 
loop = 2 循环2次   
loop 或者 loop = "-1" 无限循环

由于版权等原因，不同的浏览器可支持播放的格式是不一样的，
多浏览器支持的方案：

```html
<!-- 通过source标签指定多格式音频文件 -->
<audio controls>
  <source src="./music/See You Again.mp3">
  <source src="./music/See You Again.wav">
  <source src="./music/See You Again.ogg">
  您的浏览器不支持此功能
</audio>
```

### 多媒体 video

同音频播放一样，&lt;video&gt;使用也相当简单:

```html
<!-- 通过src属性指定视频路径即可 -->
<video src="./video/move.mp4" controls="controls"></video>
```

同样，通过附加属性可以更友好的控制视频的播放:

* autoplay：自动播放
* controls：是否显示默认播放控件
* loop：循环播放
* width：设置播放窗口宽度
* height：设置播放窗口的高度

由于版权等原因，不同的浏览器可支持播放的格式是不一样的，
多浏览器支持的方案：

```html
<!-- 通过source标签指定多格式音频文件 -->
<video controls>
  <source src="./video/move.mp4">
  <source src="./video/move.ogg">
  您的浏览器不支持此功能
</video>
```