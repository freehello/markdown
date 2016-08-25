
# markdown简介

## 前言
写这个算不上教程的文档说明，只是因为在我的小白进阶之路——学习github时，发现每个项目都会有一个readme.md。很好奇这.md后缀的是什么玩意，一探究竟之下，发现又学了点知识~，这里算是我的笔记吧~

md就是markdown缩写，GitHub 上每个项目要求提供Markdown格式的README.md文件，作为项目首页的说明文档。

## 宗旨
Markdown是一种轻量级标记语言，创始人为John Gruber。<br />
Markdown是为了更简单方便地书写 HTML ，使我们更加专注于内容写作本身。

# 兼容HTML
在markdown文本里可以直接加HTML标签，只要不是markdown本身的标签，都可以直接在文档里使用。

## 块状元素
需要注意的是一些块状元素，如`<div>`,`<table>`,`<pre>`,`<p>`等标签。必须在前后加上空行，与其他内容隔离开来，还需要要求他们的开始标签和与结尾标签不能用制表符或空格缩进。markdown的生成器很智能，不会在HTML区块标签外再加`<p>`标签。

例子如下，在markdown文档里加上一段HTML代码：

<ul>
    <li>这里是html标签语法</li>
    <li># 大标题</li>
    <li>## 二级标题</li>
    <li>### 三级标题</li>
    <li>#### 四级标题</li>
    <li>##### 五级标题</li>
    <li>###### 六级标题</li>
</ul>

以上代码要显示出来，该代码块上下都有一个空行，要注意的是，HTML模块化标签之间的markdown格式的语法将不会被处理，例如上例中markdown的标题语法标签并未被转译成标题文本。<br />

## 行内元素
HTML 的行内标签如 `<span>`、`<cite>`、`<del>` 可以在 Markdown 的段落、列表或是标题里随意使用。依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 <a> 或 <img> 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图像标签语法。

和处在 HTML 块状元素标签间不同，Markdown 语法在 HTML 行内元素标签间是有效的。

示例代码：
```
我是<del>**删除线**</del>，我在行内，且我不需要进行转义。也不需要想块元素那样需要在标签前后加空行
```
示例效果：

我是<del>**删除线**</del>，我在行内，且我不需要进行转义。也不需要想块元素那样需要在标签前后加空行

此示例中html标签`<del>`在行内直接起作用，而且markdown语法中的强调语法也是有效的。

# 强调语法
Markdown 使用星号（`*`）和底线（`_`）作为标记强调字词的符号，被 `*` 或 `_` 包围的字词会被转成用 `<em>` 标签包围，用两个 `*` 或 `_` 包起来的话，则会被转成 `<strong>`，用三个 `*` 或 `_` 包起来的话，则会被转成 `<strong><em></em></strong>`，而用两个 `~`包起来的话，则会被转成 `<del>`删除线。

示例语法：
```
*斜体*      |     _斜体_<br />
**粗体**    |   __粗体__<br />
***粗斜体*** | ___粗斜体___<br />
~~删除线~~    |<br />
***~~粗斜体删除线~~***  |  ___~~粗斜体删除线~~___<br />
~~***粗斜体删除线***~~  |  ~~___粗斜体删除线___~~
```

示例效果：

*斜体*      |     _斜体_<br />
**粗体**    |   __粗体__<br />
***粗斜体*** | ___粗斜体___<br />
~~删除线~~    |<br />
***~~粗斜体删除线~~***  |  ___~~粗斜体删除线~~___<br />
~~***粗斜体删除线***~~  |  ~~___粗斜体删除线___~~



斜体、粗体、删除线可混合使用

但是如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。就如此句中的 * 和 _ 两边都留有空白，而且并没有被反引号所包围，他们只会被认为是普通符号，而如果*和_两边没空白，就如这句话所显示。

如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：

示例语法：
```
\*这里的星号不起任何作用，只是普通符号\*
```
示例效果：

\*这里的星号不起任何作用，只是普通符号\*


# 源代码显示及高亮

那么如果是程序和标签相关的写作，你不希望你写的一段代码以列表或者段落的方式去排版，而是想要直接以源代码的形式显示，那么markdown会用 `<pre>` 和 `<code>` 标签把代码区块包起来。

markdown语法需要我们在代码的上一行和下一行用三个反引号来标记代码区块。反引号就是数字1左边，Tab键上面的键(注意使用英文输入法)。要实现语法高亮只要在三个反引号之后加上你的编程语言即可（忽略大小写）。如html代码只需在开头三个反引号之后加上html即可，c++语言可以写成c++也可以是cpp。看代码：

```html
<ul>
    <li>这里是html标签语法</li>
    <li># 大标题</li>
    <li>## 二级标题</li>
    <li>### 三级标题</li>
    <li>#### 四级标题</li>
    <li>##### 五级标题</li>
    <li>###### 六级标题</li>
</ul>
```

```java
public static void main(String[]args){} //Java
```

```c
int main(void)
{
    printf("Hello, world!");
    return 0;
} //C
```

```Bash
echo "hello GitHub" #Bash
```

```javascript
document.write("Hello World!") //javascript
```

```cpp
string &operator+(const string& A,const string& B) //cpp
```
# 显示文本

## 文本

### 普通文本
直接输入的文字就是普通文本。

### 单行文本
```
我是单行文本
```
### 多行文本
```
我是多行文本，我写在三个反引号的markdown语法中，属于源码输出，目的是让这段话高亮显示，
在这里我可以直接回车换行，
我换行了，文字太多了，我任性直接换行
```
### 文本换行
以上文本是在三个反引号内输出的，为源码输出，所以这段文本可以直接回车换行，<br />
而markdown中直接输入文字，不能回车换行，若想换行有三种办法：  
1.本段文本第二行换行是在第一行后面想要换行处加了`<br />`；

2.本段文本第三行换行是上一行文本后面补两个空格然后回车；

3.本段文本第四行和本行换行是在其上一行下面都直接加了一行空行，这样也能实现换行，只是行间距有点大。

### 文本首行缩进 空格
由于在markdown中空格大部分时候都是起着排版控制作用，因此没法在行首或格式控制符之后输入空格。

en space, U+2002 ISOpub<br />
半方大的空白`&ensp;`或`&#8194;`<br />
em space, U+2003 ISOpub<br />
  全方大的空白`&emsp;`或`&#8195;`<br />
no-break space = non-breaking space, U+00A0 ISOnum<br />
    不断行的空白格`&nbsp;`或`&#160;`<br />
一般行首输入两个全角空格（`&emsp;`）或八个半角空格（`&nbsp;`）进行缩进即可。

语法：
```
&emsp;&emsp;全角空格缩进
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;半角空格缩进
```

效果：<br />
&emsp;&emsp;全角空格缩进<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;半角空格缩进<br />
对比以上两行文本已经缩进两个汉字宽度。



### 部分文本高亮
如果你想使一段话中部分文字高亮显示，来起到突出强调的作用，那么可以把它用一对反引号把它包围起来。注意不是单引号，而是Tab上方，数字1左边的按键（注意使用英文输入法）。语法：

```
`markdown`,`<code>`,`文本高亮`,`&lt;div&gt;`,&lt;p&gt;
```
效果：`markdown`,`<code>`,`文本高亮`,`&lt;div&gt;`,&lt;p&gt;


#### 文本段中显示代码标签

文本段中如果要输出标签，不能直接写标签，markdown会转译为标签加上`<pre>``<code>`标签，并将该标签之后的文本解释到代码区块里，导致文本段显示排版出错。

从上诉`部分文本高亮`示例中的语法及效果中，可以看出要在文本段中正常显示标签，需要用一对反引号将标签包围起来，注意不是单引号，而是Tab上方，数字1左边的按键（注意使用英文输入法），这种方法不仅可以在文本段中正常显示标签，而且标签是高亮显示，为常用显示方法。

也可以通过特殊符号转义来显示标签，例如`部分文本高亮`示例中最后的div和p标签的写法，加反引号就不需要特殊字符再转义，因为反引号内的内容会直接输出，而不用反引号，则需要将标签的尖括号通过特殊字符转义。

# 特殊字符转义
语法：
```
© ， &copy; ， AT&T ，  AT&amp;T ，  4 < 5  ，   4 &lt; 5  ，  &lt; ，  &amp;  ，  &gt;
```
效果：

© ， &copy; ，  AT&T ，  AT&amp;T ，  4 < 5  ，   4 &lt; 5  ，  &lt; ，  &amp;  ，  &gt;

当`<`，`>`用于标签的起始和结束标签且在文本段内显示时，在不让其高亮显示的情况下，需要对这两个符号进行转义`&lt;`，`&gt;`。
