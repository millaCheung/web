# WEB简介

## 1. 网页

### 1.1 什么是网页

网站是指在因特网上根据一定的规则，使用HTML等制作的用于展示特定内容相关的网页集合。

网页时网站的一“页”，通常是HTML格式的文件，它要浏览器来阅读。

网页是构成网站的基本元素，它通常由图片、链接、文字、声音、视频等元素组成。通常我们看到的网页，常见以 .htm 或 .html 后缀结尾的文件，因此其俗称为HTML文件。

### 1.2 什么是HTML

HTML指的是超文本标记语言（Hyper Text Markup Language），它是用来描述网页的一种语言。

HTML不是一种编程语言，而是一种标记语言（markup language）。

标记语言是一套标记标签（markup tag）。

超文本：

1. 它可以加入图片、声音、动画、多媒体等内容（超越了文本限制）。
2. 它还可以从一个文件跳转到另一个文件，与世界各地主机的文件连接（超级链接文本）。

### 1.3 网页的形成

网页是由网页元素组成的，这些元素是利用html标签描述出来，然后通过浏览器解析来显示给用户的。

前端代码  ——  浏览器显示代码（解析、渲染）  ——  生成web页面

## 2. 常用浏览器

浏览器是网页显示、运行的平台。常用的浏览器由IE、火狐（Firefox）、谷歌（Chrome）、Safari和Opera等。

#### 浏览器内核

浏览器内核（渲染引擎）：负责读取网页内容，整理讯息，计算网页的显示方式并显示页面。

| 浏览器       | 内核    | 备注                                            |
| ------------ | ------- | ----------------------------------------------- |
| IE           | Trident | IE、猎豹安全、360极速浏览器、百度浏览器         |
| Firefox      | Gecko   | 火狐浏览器内核                                  |
| Safari       | WebKit  | 苹果浏览器内核                                  |
| Chrome/Opera | Blink   | chrome/opera浏览器内核。Blink其实是WebKit的分支 |

## 3. WEB标准

Web标准是由W3C组织和其他标准化组织制订的一系列标准的集合。W3C（万维网联盟）是国际最著名的标准化组织。

### 3.1 为什么需要Web标准

浏览器不同，它们显示页面或者排版就有些许差异。

遵循Web标注除了可以让不同的开发人员写出的页面更标准、更统一外，还有以下优点：

1. 让Web的发展前景更广阔
2. 内容能被更广泛的设备访问
3. 更容易被搜索引擎搜索
4. 降低网站的维护费用
5. 使网站更易于维护
6. 提高页面浏览速度

### 3.2 Web标准的构成

主要包括结构（Structure）、表现（Presentation）和行为（Behavior）三个方面

| 标准                 | 说明                                                         |
| -------------------- | ------------------------------------------------------------ |
| 结构（Structure）    | 结构用于对网页元素进行整理和分类，现阶段主要学的是HTML       |
| 表现（Presentation） | 表现用于设置网页元素的版式、颜色、大小等外观样式，主要是指CSS |
| 行为（Behavior）     | 行为是指网页模型的定义及交互的编写，现阶段主要学的是JavaScript |

Web 标准提出的最佳体验方案：结构、样式、行为相分离。

简单理解：结构写到HTML文件中，表现写到CSS文件中，行为写到JavaScript文件中。

# HTML

## 1. HTML语法规范

### 1.1 基本语法概述

1. HTML标签是由尖括号包围的关键词，例如\<html>。
2. HTML标签通常是成对出现的，例如\<html>和\</html>，我们称为双标签。标签对中的第一个标签是开始标签，第二个标签是结束标签
3. 有些特殊的标签必须是单个标签（极少情况），例如\<br />，我们称之为单标签。

### 1.2 标签关系

双标签关系可以分为两类：包含关系和并列关系

包含关系：

```html
<head>
	<title></title>
</head>
```

并列关系：

```html
<head></head>
<body></body>
```

## 2. HTML基本结构标签

### 2.1 第一个HTML网页

每个网页都会有一个基本的结构标签（也称为骨架标签），页面内容也是在这些基本标签上书写。

HTML页面也称为HTML文档

```html
<html>
	<head>
	<title>我是第一个页面</title>
	</head>
	<body>
		床前明月光，疑是地上霜。
	</body>
</html>
```

| 标签名            | 定义       | 说明                                                   |
| ----------------- | ---------- | ------------------------------------------------------ |
| \<html>\</html>   | HTML标签   | 页面中最大的标签，我们称为根标签                       |
| \<head>\</head>   | 文档的头部 | 注意在head标签中我们必须要设置的标签是title            |
| \<title>\</title> | 文档的标题 | 让页面拥有一个属于自己的网页标题                       |
| \<body>\</body>   | 文档的主体 | 元素包含文档的所有内容，页面内容基本都是放到body里面的 |

HTML文档的后缀必须是 .html 或 .htm，浏览器的作用是读取HTML文档，并以网页的形式显示它们。

### 2.2 基本结构标签总结

## 3. 网页开发工具

### 3.1 文档类型声明标签

\<!DOCTYPE>文档类型声明，作用就是告诉浏览器使用哪种HTML版本来显示网页。

```html
<!DOCTYPE html>
```

这句代码的意思是：当前页面采取的是HTML5版本来显示网页

**注意：**

1. \<!DOCTYPE>声明位于文档中的最前面位置，处于\<html>标签之前
2. \<!DOCTYPE>不是一个HTML标签，它就是文档类型声明标签

### 3.2 lang 语言种类

用来定义当前文档显示的语言。

1. en定义语言为语言
2. zh-cn定义语言文中文

简单来说，定义en就是英文网页，定义zh-cn就是中文网页

其实对于文档显示来说，定义为en的文档也可以显示中文，定义为zh-cn的文档也可以显示英文

这个属性对浏览器和搜索引擎（百度、谷歌等）有作用。

```html
<html lang="en">
</html>
```

### 3.3 字符集

字符集（Character set）是多个字符的集合。以便计算机能够识别和存储各类文字。

在\<head>标签内，可以通过\<meta>标签的charset属性来规定HTML文档应该使用哪种字符编码。

```html
<meta charset="UTF-8">
```

charset常用的值有：GB2312、BIG5、GBK 和 UTF-8，其中 UTF-8 也被称为万国码，基本包含了全世界所有国家需要用到的字符。

**注意：**

上面语法是必须要写的代码，否则可能引起乱码的情况。一般情况下，统一使用“UTF-8”编码，尽量统一写成标准的“UTF-8”，不要写成“utf8"或”UTF8“。

## 4. HTML常用标签

### 4.1 标签语义

标签的含义

### 4.2 标题标签 \<h1> - \<h6>

为了使网页更具有语义化，我们经常会在页面中用到标题标签。HTML提供了6个等级的网页标题，即\<h1> - \<h6>。

```html
<h1>一级标题</h1>
```

单词head的缩写，以为头部、标题。

标签语义：作为标题使用，并且依据重要性递减

**特点：**

1. 加了标题的文字会加粗，字号变大
2. 一个标题独占一行

### 4.3 段落和换行标签

在网页中，要把文字有条理的显示出来，就需要将这些文字分段显示。在HTML标签中，\<p>标签用于定义段落，它可以将整个网页分为若干个段落。

```html
<p>段落标签</p>
```

单词 paragraph 的缩写，意为段落。

标签语义：可以把HTML文档分割为若干个段落。

**特点：**

1. 文本在一个段落中会根据浏览器窗口的大小自动切换
2. 段落和段落中间保有空隙

在HTML中，一个段落中的文字从左到右会依次排列，直到浏览器窗口的右端，然后才自动换行。如果希望某段文本强制换行显示，就需要使用换行标签 \<br />。

```html
<br />
```

单词break的缩写，意为打断、换行

标签语义：强制换行

**特点：**

1. \<br />是单标签
2. \<br />标签只是简单的开始新的一行，和段落不一样，段落之间会插入一些垂直的间距

### 4.4 文本格式化标签

在网页中，有时需要为文字设置<b>粗体</b>、<i>斜体</i>或<ins>下划线</ins>等效果，这时就需要用到HTML中的文本格式化标签，使文字以特殊的方式显示。

标签语义：突出重要性，比普通文字更重要。

| 语义   | 标签                             |                                         |
| ------ | -------------------------------- | --------------------------------------- |
| 加粗   | \<strong>\</strong>或者\<b>\</b> | 更推荐使用\<strong>标签加粗，语义更强烈 |
| 倾斜   | \<em>\</em>或者\<i>\</i>         | 更推荐使用\<em>标签加粗，语义更强烈     |
| 删除线 | \<del>\</del>或者\<s>\</s>       | 更推荐使用\<del>标签加粗，语义更强烈    |
| 下划线 | \<ins>\</ins>或者\<u>\</u>       | 更推荐使用\<ins>标签加粗，语义更强烈    |

### 4.5 \<div>\</div> 和 \<span>\</span> 标签

\<div> 和 \<span> 是没有语义的，它们就是一个盒子，用来装内容的。

```html
<div>这是一个盒子</div>
<span>这也是一个盒子</span>
```

div 是 division 的缩写，表示分割、分区。

span 意为跨度、跨距。

**特点：**

1. \<div> 标签用来布局，但是在一行只能放一个 \<div>。大盒子
2. \<span> 标签用来布局，一行上可以多个\<span>。小盒子

### 4.6 图像标签和路径

#### 4.6.1 图像标签

在HTML标签中，\<img> 标签用于定义HTML页面中的图像。

```html
<img src="图像URL" />
```

单词 image 的缩写，意为图像。

src 是 \<img> 标签的必须属性，它用于指定图像文件的路径和文件名。

所谓属性：简单理解就是属于这个图像标签的特性。

图像标签的其他属性：

| 属性   | 属性值   | 说明                                 |
| ------ | -------- | ------------------------------------ |
| src    | 图片路径 | 必须属性                             |
| alt    | 文本     | 替换文本。图像不能显示的文字         |
| title  | 文本     | 提示文本。鼠标放到图像上，显示的文字 |
| width  | 像素     | 设置图像的宽度                       |
| height | 像素     | 设置图像的高度                       |
| border | 像素     | 设置图像的边框粗细                   |

```html
<body>
<div>图像</div>
<img src="imgs/img2.jpg" />
<div>alt 替换文本 图像显示不出来文字替换</div>
<img src="img/img2.jpg" alt="美女" />
<div>title 提示文本 图标放到图片上，提示的文字</div>
<img src="imgs/img2.jpg" alt="美女" title="美女西施" />
<div>width 设定宽度</div>
<img src="imgs/img2.jpg" alt="美女" title="美女西施" width="500" />
<div>height 设定高度</div>
<img src="imgs/img2.jpg" alt="美女" title="美女西施" height="200" />
<div>height 设定边框</div>
<img src="imgs/img2.jpg" alt="美女" title="美女西施" border="15" />
</body>
```

**图像标签属性注意点：**

1. 图像标签可以拥有多个属性，必须写在标签名的后面。

2. 属性之间不分先后顺序，标签名与属性、属性与属性之间均以空格分开。

3. 属性采取键值对形式，即 key = "value" 的格式，属性 = "属性值"。


#### 4.6.2 路径

**目录文件夹和根目录：**

- 实际工作中，文件不能随便乱放，否则用起来很难快速找到它们，因此需要一个文件夹来管理。

- 目录文件夹：就是普通文件夹，里面只不过存放了页面所需要的相关素材，比如html文件、图片等。

- 根目录：打开目录文件夹的第一次就是根目录

- 页面中的图片会非常多，通常我们会新建一个文件夹来存放这些图像文件（images），这时再查找图像，就需要采取“路径”的方式来指定图像文件的位置。


**路径可以分为：**

1. 相对路径
2. 绝对路径

**相对路径：**以引用文件所在位置为参考基础，而建立出的目录路径。

| 相对路径分类 | 符号 | 说明                                                         |
| ------------ | ---- | ------------------------------------------------------------ |
| 同一级路径   |      | 图像文件位于HTML文件的同一级 如\<img src="baidu.gif" />      |
| 下一级路径   | /    | 图像文件位于HTML文件的下一级 如\<img src="images/baidu.gif" /> |
| 上一级路径   | ../  | 图像文件位于HTML文件的上一级 如\<img src="../baidu.gif" />   |

**绝对路径：**是指目录下的绝对位置，直接到达目标位置，通常是从盘符开始的路径。

### 4.7 超链接标签

在HTML标签中，\<a> 标签用于定义超链接，作用是从一个页面链接到另一个页面

链接的语法格式

```javascript
<a href="跳转目标" target="目标窗口的弹出方式">文本或图像</a>
```

单词 anchor 的缩写，意为：锚

两个属性的作用如下：

| 属性   | 作用                                                         |
| ------ | ------------------------------------------------------------ |
| href   | 用于指定链接目标的地址，（必须属性）当为标签应用 href 属性时，它就具有了超链接的功能 |
| target | 用于指定链接页面的打开方式，其中 \_self 为默认值，\_blank 为在新窗口中打开方式 |

链接分类：

1. 外部链接，例如 `<a href="http://www.baidu.com">百度</a>`

2. 内部链接，网站内部页面之间的相互链接，直接链接内部页面名称即可，例如

   `<a href="index.html">首页</a>`

3. 空链接：如果当时没有确定链接目标时，`<a href="#">首页<a>`

   (点击链接，页面默认上滚到页的顶部， 但可以加上 onclick="return false"，防止上滚到页的顶部。)

   `<a href="javascript: void(0);">test</a>` `<a href="javascript:;">test</a>` 死链接，指向空事件

4. 下载链接：如果 href 里面地址是一个文件或者压缩包，会下载这个文件

5. 网页元素链接：在网页中的各种网页元素，如文本、图像、表格、音频、视频等都可以添加超链接

6. 锚点链接：点击链接，可以快速定位到页面中的某个位置

   - 在链接文本的 href 属性中，设置属性值为 #名字 的形式，如 `<a href="#two">第2集</a>`
   - 找到目标位置标签，里面添加一个 id属性 = 刚才的名字，如 `<h3 id="two">第2集介绍</h3>`

```html
<body>
<h4>1.外部链接</h4>
<a href="http://www.qq.com" target="_blank">tencent</a>
<!--target 打开窗口的方式，默认的值是_self，当前页面打开页面；_blank，新窗口打开页面-->
    
<h4>2.内部链接：网站内部页面之间相互链接</h4>
<a href="07_图像标签.html">图像标签</a>

<h4>3.空链接：#</h4>
<a href="#">空链接</a>

<h4>4.下载链接：地址链接是文件 .exe 或者是 zip 等压缩包</h4>
<a href="imgs/img2.rar">下载文件</a>

<h4>5.网页元素链接</h4>
<a href="http://www.baidu.com"><img src="imgs/img2.jpg"></a>
</body>
```

## 5. HTML中的注释和特殊字符

### 5.1 注释

如果需要在HTML文档中添加一些便于阅读和理解但又不需要显示的注释文字，就需要使用注释标签。

HTML的注释以 `<!--` 开头，以 `-->` 结束。

```html
<!--我是一个注释-->  <!--快捷键：ctrl + / -->
```

添加注释是为了更好的解释代码的功能，便于相关开发人员理解和阅读代码，程序是不会执行注释内容的。

### 5.2 特殊字符

在HTML页面中，一些特殊的符号很难或者不方便直接使用，此时我们就可以使用下面的字符来替代。

| 特殊字符 | 描述           | 字符的代码 |
| -------- | -------------- | ---------- |
|          | 空格符         | `&nbsp;`   |
| <        | 小于号         | `&lt;`     |
| >        | 大于号         | `&gt;`     |
| &        | 和号           | `&amp;`    |
| ￥       | 人民币         | `&yen;`    |
| ©        | 版权           | `&copy;`   |
| ®        | 注册商标       | `&reg;`    |
| °        | 摄氏度         | `&deg;`    |
| ±        | 正负号         | `&plusmn;` |
| ×        | 乘号           | `&times;`  |
| ÷        | 除号           | `&divide;` |
| ²        | 平方2（上标2） | `&sup2;`   |
| ³        | 立方3（上标3） | `&sup3;`   |

## 6. 表格标签

### 6.1 表格的主要作用

表格主要用来显示、展示数据，因为它可以让数据显示的非常的规整，可读性非常好。特别是后台展示数据的时候，能够熟练运用表格就显得很重要。一个清爽简约的表格能够把繁杂的数据表现得很有条理。

**表格用来展示数据。**

### 6.2 表格的基本语法

```html
<table>
    <tr>
    	<td>单元格内的文字</td>
		...
    </tr>
	...
</table>
```

1. `<table></table>` 是用来定义表格的标签

2. `<tr></tr>` 标签定义表格中的行，必须嵌套在 `<table></table>` 标签中
3. `<td></td>`用于定义表格中的单元格，必须嵌套在 `<tr></tr>` 标签中
4. 字母 td 指表格数据（table data），即数据单元格的内容

### 6.3 表头单元格标签

一般表头单元格位于表格的第一行或第一列，表头单元格里面的文字内容加粗居中显示。

`<th>` 标签表示 HTML 表格的表头部分（table head的缩写）

```html
<table>
    <tr>
    	<th>姓名</th>
		...
    </tr>
	...
</table>
```

### 6.4 表格属性

表格标签这部分属性我们实际开发中不常用，后面通过 CSS 来设置。

| 属性名      | 属性值              | 描述                                              |
| ----------- | ------------------- | ------------------------------------------------- |
| align       | left、center、right | 规定表格相对周围元素的对齐方式                    |
| border      | 1 或 ""             | 规定表格单元是否拥有边框，默认为 ""，表示没有边框 |
| cellpadding | 像素值              | 规定单元边沿与其内容之间的空白，默认1像素         |
| cellspacing | 像素值              | 规定单元格之间的空白，默认2像素                   |
| width       | 像素值或百分比      | 规定表格的宽度                                    |

小说排名案例

```html
<body>
<table align="center" cellspacing="0" cellpadding="10px" border="1px" width="700px">
    <thead>
        <tr>
            <th>排名</th>
            <th>关键词</th>
            <th>趋势</th>
            <th>今日搜索</th>
            <th>最近七日</th>
            <th>相关链接</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>鬼吹灯</td>
            <td>↓</td>
            <td>345</td>
            <td>123</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>2</td>
            <td>盗墓笔记</td>
            <td>↓</td>
            <td>124</td>
            <td>675423</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>3</td>
            <td>西游记</td>
            <td>↑</td>
            <td>321</td>
            <td>43242</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>4</td>
            <td>三国演义</td>
            <td>↑</td>
            <td>342</td>
            <td>43242</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>5</td>
            <td>甄嬛传</td>
            <td>↓</td>
            <td>11</td>
            <td>34325</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>6</td>
            <td>老人与海</td>
            <td>↑</td>
            <td>32</td>
            <td>231</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>7</td>
            <td>水浒传</td>
            <td>↑</td>
            <td>213</td>
            <td>43243</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
    </tbody>
</table>
</body>
```

### 6.5 表格结构标签

使用场景：因为表格可能很长，为了更好的表示表格的语义，可以将表格分割成表格头部和表格主体两大部分

在表格标签中，分别用：`<thead>` 标签 表格的头部区域、`<tbody>` 标签 表格的主体区域。

1. `<thead></thead>`：用于定义表格的头部。`<thead>` 内部必须拥有 `<tr>` 标签。一般是位于第一行。
2. `<tbody></tbody>`：用于定义表格的主题，主要用于放数据本体
3. 以上两个标签都是放在 `<table></table>` 标签中

```html
<table>
    <thead>
        <tr>
            <th></th>
            <td></td>
        </tr>
    </thead>
    <tbody>
        ...
    </tbody>
    <tfoot>
        ...
    </tfoot>
</table>
```

### 6.6 合并单元格

特殊情况下，可以把多个单元格合并为一个单元格。

**合并单元格方式：**

- 跨行合并：`rowspan="合并单元格的个数"`
- 跨列合并：`colspan="合并单元格的个数"`

**目标单元格：（写合并代码）**

- 跨行：最上侧单元格为目标单元格，写合并代码
- 跨列：最左侧单元格为目标单元格，写合并代码

**合并单元格三部曲：**

1. 先确定是跨行还是跨列合并
2. 找到目标单元格。写上合并方式 = 合并的单元格数量
3. 删除多余的单元格

## 7. 列表标签

列表用来布局

特点：整齐、整洁、有序，它作为布局会更加自由和方便

### 7.1 无序列表

`<ul>` 标签表示 HTML 页面中项目的无序列表，一般会以项目符号呈现列表项，而列表项使用 `<li>` 标签定义。

```html
<ul>
	<li>列表项1</li>
	<li>列表项2</li>
	<li>列表项3</li>
	...
</ul>
```

1. 无序列表的各个列表项之间没有顺序级别之分，是并列的
2. `<ul></ul>` 中只能嵌套 `<li></li>`，直接在 `<ul></ul>` 标签中输入其他标签或文字的做法是不被允许的
3. `<li>` 与 `</li>` 之间相当于一个容器，可以容纳所有元素
4. 无序列表会带有自己的样式属性，但在实际使用时，我们会使用 CSS 来设置

### 7.2 有序列表

有序列表即为有排列顺序的列表，其各个列表项会按照一定的顺序排列定义。

在HTML标签中，`<ol>` 标签用于定义有序列表，列表排序以数字来显示，并且使用 `<li>` 标签来定义列表项

```html
<ol>
	<li>列表项1</li>
	<li>列表项2</li>
	<li>列表项3</li>
	...
</ol>
```

1. `<ol></ol>` 中只能嵌套 `<li></li>`，直接在 `<ol></ol>` 标签中输入其他标签或文字的做法是不被允许的
2. `<li>` 与 `</li>` 之间相当于一个容器，可以容纳所有元素
3. 有序列表会带有自己的样式属性，但在实际使用时，我们会使用 CSS 来设置

### 7.3 自定义列表

自定义列表的使用场景

自定义列表常用于对术语或名词进行解释和描述，定义列表的列表项前没有任何项目符号

在 HTML 标签中，`<dl>` 标签用于定义描述列表（或定义列表），该标签会与 `<dt>`（定义项目/名字）和 `<dd>`（描述每一个项目/名字）一起使用。

```html
<dl>
	<dt>名词1</dt>
	<dd>名词1解释1</dd>
	<dd>名词1解释2</dd>
	...
</dl>
```

1. `<dl></dl>` 里面只能包含 `<dt>` 和 `<dd>` 
2. `<dt>` 和 `<dd>` 个数没有限制，经常是一个 `<dt>` 对应多个 `<dd> `

### 7.4 列表总结

| 标签名      | 定义       | 说明                                                         |
| ----------- | ---------- | ------------------------------------------------------------ |
| `<ul></ul>` | 无序列表   | 里面只能包含 li，没有顺序，使用较多。li 里面可以包含任何标签 |
| `<ol></ol>` | 有序列表   | 里面只能包含 li，有顺序，使用相对较少。li 里面可以包含任何标签 |
| `<dl></dl>` | 自定义列表 | 里面只能包含 dt 和 dd。dt 和dd 里面以包含任何标签            |

## 8. 表单标签

### 8.1 为什么需要表单

在网页中，需要与用户进行交互，收集用户资料，此时就需要表单

### 8.2 表单的组成

在HTML中，一个完整的表单通常由 **表单域、表单控件（也称为表单元素）**和 **提示信息** 3个部分组成

### 8.3 表单域

表单域是一个包含表单元素的区域

在HTML标签中，`<form>` 标签用于定义表单域，以实现用户信息的收集和传递

`<form>` 会把它范围内的表单元素信息提交给服务器

```html
<form action="url地址" method="提交方式" name="表单域的名称">
	各种表单元素控件
</form>
```

常用属性：

| 属性   | 属性值   | 作用                                               |
| ------ | -------- | -------------------------------------------------- |
| action | url 地址 | 用于指定接收并处理表单数据的服务器程序的 url 地址  |
| method | get/post | 用于设置表单数据的提交方式，其取值为 get 或 post   |
| name   | 名称     | 用于指定表单的名称，以区分同一个页面中的多个表单域 |

### 8.4 表单控件（表单元素）

在表单域中可以定义各种表单元素，这些表单元素就是允许用户在表单中输入或者选择的内容控件。

1. input 输入表单元素
2. select 下拉表单元素
3. textarea 文本域元素

#### 8.4.1 \<input>表单元素

在英文单词中，input 是输入的意思，而在表单元素中 `<input>` 标签用于收集用户信息。

在 `<input>` 标签中，包含一个 type 属性，根据不同的 type 属性值，输入字段拥有很多种形式（可以是文本字段、复选框、掩码后的文本控件、单选按钮、按钮等）。

```html
<input type="属性值" />
```

-  `<input />` 标签为单标签
- type 属性设置不同的属性值用来指定不同的控件类型

type属性的属性值及其描述如下：

| 属性值   | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| button   | 定义可单击按钮（多数情况下，通过 JavaScript 启动脚本）       |
| checkbox | 定义复选框                                                   |
| file     | 定义输入字段和“浏览”按钮，供文件上传                         |
| hidden   | 定义隐藏的输入字段                                           |
| image    | 定义图像形式的提交按钮                                       |
| password | 定义密码字段。该字段中的字符被掩码                           |
| radio    | 定义单选按钮                                                 |
| reset    | 定义重置按钮。重置按钮会清除表单中的所有数据                 |
| submit   | 定义提交按钮。提交按钮会把表单数据发送到服务器               |
| text     | 定义单行的输入字段，用户可在其中输入文本。默认宽度为20个字符 |

除 type 属性外，`<input>` 标签还有很多其他属性，其常用属性如下：

| 属性      | 属性值       | 描述                                  |
| --------- | ------------ | ------------------------------------- |
| name      | 由用户自定义 | 定义 input 元素的名称                 |
| value     | 由用户自定义 | 规定 input 元素的值                   |
| checked   | checked      | 规定此 input 元素首次加载时应当被选中 |
| maxlength | 正整数       | 规定输入字段中的字符的最大长度        |

1. name 和 value 是每个表单元素都有的属性值，主要给后台人员使用
2. **name 表单元素的名字，要求单选按钮和复选框要有相同的 name 值**
3. checked 属性主要针对单选按钮和复选框，主要作用为打开页面时，就可以默认选中这个表单元素
4. maxlength 是用户可以在表单元素输入的最大字符数，一般较少使用。

```html
<form action="xxx.php" method="get">
    <!--text 文本框，用户可以在里面输入任何字符-->
    用户名：<input type="text" name="username" value="请输入用户名" maxlength="6"><br />
    <!--password 密码框 用户看不到密码-->
    密码：<input type="password" name="pwd"><br />
    <!--radio 单选按钮 可以实现多选一-->
    <!--name 是表单元素名字 这里性别单选按钮必须有相同的名字name，才能实现多选一-->
    <!--单选按钮和复选框可以设置checked属性，当页面打开的时候就可以默认选中这个按钮-->
    性别：男 <input type="radio" name="sex" value="男" checked="checked"> 女 <input type="radio" name="sex" value="女"><br />
    <!--checkbox 复选框 可以实现多选-->
    爱好：吃饭 <input type="checkbox" name="hobby" value="吃饭">
    睡觉 <input type="checkbox" name="hobby" value="睡觉">
    打豆豆 <input type="checkbox" name="hobby" value="打豆豆"><br />
    <!--点击提交按钮，可以把表单域form里面的表单元素里面的值，提交给后台服务器-->
    <input type="submit" value="提交">
    <!--重置按钮可以还原表单元素的默认状态-->
    <input type="reset" value="重置">
    <!--普通按钮 button 后期结合js搭配使用-->
    <input type="button" value="获取短信验证码"><br />
    <!--文件域 上传文件使用-->
    上传头像：<input type="file">
</form>
```

### 8.4.2 \<label> 标签

`<label>` 标签为 input 元素定义标注（标签）。

`<label>` 标签用于绑定一个表单元素，当点击 `<label>` 标签内的文本时，浏览器就会自动将焦点（光标）转到或者选择对应的表单元素上，增加用户体验

语法：

```html
<label for="sex">男</label>
<input type="radio" name="sex" id="sex" />
```

核心：\<label> 标签的for属性应当与相关元素的id属性相同

```html
<body>
<label for="user">用户名：</label><input type="text" name="" id="user" />
<input type="radio" name="sex" id="male" /><label for="male">男</label>
<input type="radio" name="sex" id="famale" /><label for="famale">女</label>
</body>
```

### 8.4.3 \<select> 表单元素

使用场景：在页面中，如果有多个选项让用户选择，并且想要节约页面控件时，可以使用 `<select>` 标签控件定义下拉列表。

**语法：**

```html
<select>
	<option>选项1</option>
	<option>选项2</option>
	<option>选项3</option>
	...
</select>
```

1. \<select> 中至少包含一堆 \<option>
2. 在 \<option> 中定义 selected="selected" 时，当前项即为默认选中项

### 8.4.4 \<textarea> 表单元素

使用场景：当用户输入内容较多的情况下，我们就不能使用文本框表单了，此时可以使用 `<textarea>` 标签。

在表单元素中， `<textarea>` 标签时用于定义多行文本输入的控件

使用多行文本输入控件，可以输入更多的文字，该控件常见于留言板，评论。

语法：

```html
<textarea rows="3" cols="20">
    文本内容
<textarea>
```

1. 通过 `<textarea>` 标签可以轻松地创建多行文本输入框。
2. cols="每行中的字符数"，rows="显示的行数"，我们在实际开发中不会使用，都是用 css 来改变大小

### 8.5 表单元素总结

1. 表单元素 input 输入表单元素；select 下拉表单元素；textarea 文本域表单元素；
2. 这三组表单元素都应该包含在 form 表单域里面，并且有 name 属性

```html
<form>
	<input type="text" name="username">
	<select name="jiguan">
		<option>北京</option>
	</select>
	<textarea name="message"></textarea>
</form>
```

3. 有三个名字非常相似的标签：

   （1）表单域 form  使用场景：提交区域内表单元素给后台服务器

   （2）文件域 file，是input type属性值  使用场景：上传文件

   （3）文本域 textarea  使用场景：可以输入多行文字，比如留言板，网页介绍等

4. 我们当前阶段不需要提交表单元素，所以我们只负责表单元素的外观形态即可

注册页面案例

```html
<body>
<h4>青春不常在，抓紧谈恋爱</h4>
<table width="700px">
    <tr>
        <td>性别</td>
        <td>
            <input type="radio" name="sex" id="male">
            <label for="male"><img src="images/nan.svg"></label>
            <input type="radio" name="sex" id="female">
            <label for="female"><img src="images/nv.svg"></label>
        </td>
    </tr>
    <tr>
        <td>生日</td>
        <td>
            <select>
                <option>--请选择年--</option>
                <option>1990</option>
                <option>1991</option>
                <option>1992</option>
                <option>1993</option>
                <option>1994</option>
                <option>1995</option>
                <option>1996</option>
                <option>1997</option>
                <option>1998</option>
            </select>
            <select>
                <option>--请选择月--</option>
                <option>1</option>
                <option>2</option>
                <option>3</option>
                <option>4</option>
                <option>5</option>
                <option>6</option>
                <option>7</option>
                <option>8</option>
                <option>9</option>
            </select>
            <select>
                <option>--请选择日--</option>
                <option>1</option>
                <option>2</option>
                <option>3</option>
                <option>4</option>
                <option>5</option>
                <option>6</option>
                <option>7</option>
                <option>8</option>
                <option>9</option>
            </select>
        </td>
    </tr>
    <tr>
        <td>所在地区</td>
        <td><input type="text" value="北京"></td>
    </tr>
    <tr>
        <td>婚姻状况</td>
        <td>
            <input type="radio" name="marry" id="weihun" checked="checked"> <label for="weihun">未婚</label>
            <input type="radio" name="marry" id="yihun"> <label for="yihun">已婚</label>
            <input type="radio" name="marry" id="lihun"> <label for="lihun">离婚</label>
        </td>
    </tr>
    <tr>
        <td>学历</td>
        <td><input type="text" value="本科"></td>
    </tr>
    <tr>
        <td>喜欢的类型</td>
        <td>
            <input type="checkbox" name="type" id="wm"> <label for="wm">妩媚的</label>
            <input type="checkbox" name="type" id="ka"> <label for="ka">可爱的</label>
            <input type="checkbox" name="type" id="xxr"> <label for="xxr">小鲜肉</label>
            <input type="checkbox" name="type" id="llr"> <label for="llr">老腊肉</label>
            <input type="checkbox" name="type" id="all"> <label for="all">都喜欢</label>
        </td>
    </tr>
    <tr>
        <td>自我介绍</td>
        <td>
            <textarea cols="20" rows="2">自我介绍</textarea>
        </td>
    </tr>
    <tr>
        <td></td>
        <td>
            <input type="submit" value="免费注册">
        </td>
    </tr>
    <tr>
        <td></td>
        <td><input type="checkbox">我同意注册条款和会员加入标准</td>
    </tr>
    <tr>
        <td></td>
        <td><a href="#">我是会员，立即登录</a></td>
    </tr>
    <tr>
        <td></td>
        <td>
            <h4>我承诺</h4>
            <ul>
                <li>年满18岁、单身</li>
                <li>抱着严肃的态度</li>
                <li>真诚寻找另一半</li>
            </ul>
        </td>
    </tr>
</table>
</body>
```
