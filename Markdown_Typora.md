# Markdown For Typora

## Overview

**Markdown** is created by [Daring Fireball](http://daringfireball.net/), the original guideline is [here](http://daringfireball.net/projects/markdown/syntax). Its syntax, however, varies between different parsers or editors. **Typora** is using [GitHub Flavored Markdown][GFM]. 

*Outline*

[TOC]

## 块元素

### 段落和空行

段落就是一个或多个连续的文本行。在markdown源代码中，段落由多个空行分隔。在Typora中，您只需要按下`Return`就可以创建一个新的段落。

`Shift` + `Return` 可以产生一个单换行符. 然而大多数`Markdown`编辑器不识别单换行符，所以此时可以在段落结尾敲两个`空格`，或插入`<br/>`

### 标题

页眉在行首使用1-6个哈希字符，对应于页眉级别1-6。例如:

```markdown
# 一级标题
## 二级标题
###### 六级标题
```

"#"后面要加空格，添加标题内容后回车即可。

### 引用

Markdown使用电子邮件样式的>字符进行块引用。它们表示为:

> 这是一个有两段话的引用，当前是第一段
>
> 这是第二段引用

> 这是另一个引用，

在typora中，只需输入' > '，然后生成一个块引号。Typora将为您插入适当的' > '或换行符。通过添加额外的“>”级别，可以在另一个块引用中添加块引用。

### 列表

输入“* 列表1”将会产生一个无序列表，"*"还可以可以替换为“+”或“-”。

输入“1. 列表1”将产生一个有序列表，具体使用方法如下：

**==无序列表==**

- 红
- 绿
- 蓝

**==有序列表==**

1. 红
2. 绿
3. 蓝

### 任务列表

任务列表是带有标记为[ ]或[x] (不完整或完整的项的列表)。例如:

- [ ] 一个任务列表的项
- [ ] 列表语法需要
- [ ] 加粗**格式化**，@mentions, #1234 refs
- [ ] 不完整
- [x] 完整

我们还可以直接用鼠标在- [ ] 上点击，来改变“完整”或“不完整”状态。

### 代码块

Typora仅支持Github类的Markdown语法，原始代码块不再支持。

使用“```”再回车，然后添加可选的语言类型，最后我们可以得到如下结果：

```ruby
reguire 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

### 数学公式

数学公式编辑格式与*LaTex*一致。举个例子：
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$
具体请参见*LaTex*语法。

### 表格

先用三个竖线（|表头1|表头2|）创建表格，然后用`Typora`来调整表格的属性（如左右对齐、行列数目）。

| 第一 | 第二 |
| :--: | :--: |
| abc  | def  |

### 脚注

你可以这样设置脚注[^abc]

[^abc]: 脚注的描述

### 水平线

输入“***”或者“---”并回车，即可得到一个水平线

-----

### YAML Front Matter

Typora support [YAML Front Matter](http://jekyllrb.com/docs/frontmatter/) now. Input `---` at the top of the article and then press `Enter` will introduce one. Or insert one metadata block from the menu.

### 目录

输入“[TOC]”，然后回车，就可以自动生成目录。

### 图表

Typora支持[sequence](https://bramp.github.io/js-sequence-diagrams/)、[flowchart](http://flowchart.js.org/) 和[mermaid](https://knsv.github.io/mermaid/#mermaid)。详见[这里](http://support.typora.io/Draw-Diagrams-With-Markdown/).

## Span元素

Span元素将在您键入后立即被解析和呈现。将光标移动到这些span元素的中间将会将这些元素展开为markdown 源码。下面将解释这些span元素的语法。

### 链接

Markdown支持两种链接：内嵌链接和参考链接。在这两种样式中，链接文本都用[方括号]分隔。

#### 内嵌链接

用于各章节之间的跳转。Ctrl+点击[这个链接](#块元素)即可跳转到`块元素`。

#### 参考链接

参考链接可以用指定标签来替代URL链接，使用方法如下：

这是一个[参考链接][eg]的例子。

[eg]: http:baidu.com/

隐式链接名称快捷方式允许您省略链接的名称，在这种情况下，链接文本本身用作名称。只需使用一组空白方括号-例如，要将“谷歌”一词连结至google.com网站，你只需写上:

[百度][]一下你就知道。

[百度]: https://www.baidu.com/

### URLs

在URL两端添加尖括号`< >`。如，<https://www.baidu.com>

### 图片

插入图片的方法与超链接一致，但需要在中括号前额外添加`！`字符，例如：

`![](./img/csdn.png)`

当然，如果想调整图片大小，则可以通过代码`<img src="./img/csdn.png" style="zoom:30%">` 设置成这样：<img src="./img/csdn.png" style="zoom:30%">

给图片插入题注：
```HTML
<center>
<img style="zoom:150%" 
src="pic1.gif">
<br>
压缩后的效果图
</center>
```
<center>
<img style="zoom:50%" 
src="./img/csdn.png">
<br>
压缩后的效果图
</center>

### 斜体字

Markdown可以用`*`或者`_`表示强调

```markdown
*single asterisks*
_single underscores_
```

输出：

*single asterisks*

_single underscores_

### 粗体字

用双星或者双下划线可对字体加粗：（Typora推荐使用前者）

``` markdown
**double asterisks**

__double underscores__
```

输出：

**double asterisks**

__double underscores__
