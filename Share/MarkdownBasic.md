**目录**

[TOC]

markdown 是一个轻量级标记语言[^1]，它的名称是为了对应 HTML 中的 Markup 对应的语言，提供了简介快速的语法来实现 Markup 的功能。因此 markdown 兼容了 HTML 的标签，此外还可以直接用任何常规的文本编辑器编辑。而本文档的内容主要是描述一些常用 markdown 语法，包括两个方面的内容：1）基本格式语法；2）常用的数学表达式。

**Note**：所有的文件是使用的 [Typora — a markdown editor](https://typora.io/) 来书写的，没有进行额外的设置—— Typora 的功能是所写即所得，不用添加额外预览功能。如果需要查看原生格式可以使用快捷键 `Command + /` (MacOS) 或者 `Ctrl + /` (Windows)。



# $\rm I$. 基本格式语法

在进行常规书写的时候，常用的格式包括 `Heading`——可以用描述标题内容， 有序和无序列表，斜体，加粗，表格，代码块等格式。

## 1.1 Heading

`Heading` 的标签模式和 HTML 中 `<h>` 标签具有同样功能。HTML 中通过添加数字来表示 `heading` 等级，在 markdown 中通过 `#` 的个数表示同样的功能——例如上面的 `# 基本格式语法` 就是 `H1` 等级的 `heading`，而上面的 `## Heading` 就是 `H2` 等级的 `heading`。常见的语法如下：

```markdown
# h1 的 heading
## h2 的 heading
### h3 的 heading
#### h4 的 heading
##### h5 的 heading
###### h6 的 heading
```

下面是在 [MacDown:  open source Markdown editor for macOS](https://macdown.uranusjr.com/) 中的书写和表现对比：

![image-20181226225518677](https://ws2.sinaimg.cn/large/006tNbRwgy1fykjfe6yoqj30ua0iqtbe.jpg)

## 1.2 常见文字格式

常见的文字格式就是分别为斜体、加粗，这两个可以通过添加 `*` 或者 `_` 来进行调整文字格式。其中一个 `*` 或者 `_` 是将字体变为斜体，添加两个 `*` 或者 `__` 可以将字体调整为粗体，下面是语法演示：

```markdown
*字体变为斜体*
**字体加粗**

_字体变为斜体_
__字体加粗__
```

以上内容得到的效果如下：

*字体变为斜体*
**字体加粗**

## 1.3 列表

列表分为有序列表和无序列表两种形式，其主要的书写方式存在差异。有序列表需要使用**数字**加**点号**及**空格**来表示——`1. ` ；而无序列表可以通过**星号**或者**减号**加**空格**来表示——`* ` 或者 `-  ` 。下面是语法演示：

```markdown
1. 第一个有序列表 list
2. 第二个有序列表 list
3. 第三个有序列表 list


* 第一个无序列表 list
* 第二个无序列表 list
* 第三个无序列表 list

- 第一个无序列表 list
- 第二个无序列表 list
- 第三个无序列表 list
```

得到的效果如下：

1. 第一个有序列表 list
2. 第二个有序列表 list
3. 第三个有序列表 list


* 第一个无序列表 list
* 第二个无序列表 list
* 第三个无序列表 list

## 1.4 表格

在 markdown 中同样可以插入表格内容，插入的方式如下：

```markdown
| 第一列 | 第二列 |
| ------ | ------ |
| 内容一 | 内容二 |
```

得到的小如过下：

| 第一列 | 第二列 |
| ------ | ------ |
| 内容一 | 内容二 |

上面的效果是没有进行格式调整，如果需要对内容的对齐方式调整可以通过在第二行中添加冒号（`:`）来说明对齐方式：

```markdown
| 第一列左对齐 | 第二列居中齐 | 第三列有对齐 |
| :--------- | :--------: | ---------: |
| 内容一      | 内容二      |   内容三    |
```

下面是得到的效果，分别对第一列进行做对齐，第二列居中对齐和第三列右对齐处理：

| 第一列左对齐 | 第二列居中齐 | 第三列有对齐 |
| :----------- | :----------: | -----------: |
| 内容一       |    内容二    |       内容三 |

## 1.5 代码

代码可以分为行内代码和行间代码，行内的代码可以表示是一个简单的表达式或者语句。如果是需要在行内插入代码可以通过 \`\` （即**反引号**，一般是 Tab 键上面的那个键或者说是在数字 1 之前那个键），在反引号内书写内容；当需要添加大量的代码块内容时，那么就需要使用三个反引号换行书写内容之后换行添加另三个反引号——注意可以在第一行中添加  `{}` 以及语言类型来说明是哪种语言的代码，⚠️这点在 Rstudio 中使用 `RMD` 文件，即 `R` 的 markdown 文件中尤其重要。演示如下：

```markdown
这个是一个行内的代码 `python [option] filename.py`，下面是一个行间代码块：

​```{R}
# 加载 test.csv 文件为 data.frame
df <- read.csv("./test.csv")
​```
```

这个是一个行内的代码 `python [option] filename.py`，下面是一个行间代码块：
```{R}
# 加载 test.csv 文件为 data.frame
df <- read.csv("./test.csv")
```

## 1.6 其他格式

在书写 markdwn 的过程中，可能还需要进行添加一个链接、图片等内容。当然可以通过写 HTML 的方式来进行添加，需要以 markdown 的语法来进行书写的话可以通过 `[]()` 的格式来添加链接，`![]()` 来添加一个图片——注意图片可以是本地的文件也可以是一个图片链接，格式语法如下：

```markdown
[这个是 Udacity 的中文网站链接](https://cn.udacity.com)

![这个是 Udacity 本地文件](../img/udacity_logo.svg)
![这个是 Udacity 图片网页链接](https://classroom.udacity.com/images/word-mark-78490.svg)
```

[这个是 Udacity 的中文网站链接](https://cn.udacity.com)
![这个是 Udacity 本地文件](../img/udacity_logo.svg)





# $\rm II$. 数学表达式





# $\rm A$. 参考

[^1]: [Markdown 维基百科](https://zh.wikipedia.org/wiki/Markdown) 
[^2]: [教程-MarkDown](http://www.markdown.cn/)

​	markdown 中文语法详细内容，对应了 [Daring Fireball: Markdown Syntax Documentation](https://daringfireball.net/projects/markdown/syntax) 的内容


