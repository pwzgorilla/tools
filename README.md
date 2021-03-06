
---------------------------------------------------------------------------------------------
# Markdown 语法
    以下是 Markdown 的常用语法！在以后的笔记中将持续使用 Markdown 语法进行编译，因此，将此分享给大家。
## 概述
 + Markdown 的目标是实现 【易读易写】
 + Markdown 语法全由一些符号所组成，这些符号经过精挑细选，其作用一目了然。

#### 兼容HTML
+ Markdown 语法的目标是：成为一种适用于网络书写的语言  
+ Markdown 语法的理念是：让文档更容易读、写和随意改
+ **HTML 是一种发布的格式，Markdown 是一种书写的格式**
+ Markdown 的格式语法只涵盖纯文本可以涵盖的范围  
+ 不在 Markdown 涵盖范围内的标签，都可以在文档里面用 HTML 撰写，直接加标签就可以了  

+ 要制约的只有一些 HTML 区块元素，如： &lt;div&gt;、 &lt;table&gt;、 &lt;pre&gt;、&lt;p&gt;标签等，必须在前后加上空行与其他内容区隔开，还要求它 们的开始标签与结尾标签不能用制表符或空格来缩进。  
*注意：在 HTML 区块标签间的 Markdown 格式语法将不会被处理*。  

+ HTML 的区段(行内)标签，如： &lt;span&gt;、 &lt;site&gt;、 &lt;del&gt;可以在 Markdown 的段落里边或是标题里随意使用，依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。    
*注意：在 HTML 区段标签间的 Markdown 格式语法是有效的*.

#### 特殊字符自动转换
  在 HTML文件中，有两个字符需要特殊处理：<span><</span> 和 <span>&</span>。
 <span><</span> 符号用于起始标签，<span>&</span> 符号则用于标记 HTML 实体                        
 如果你只是想要显示这些字符的原型，则需要使用实体字符的形式，像是:
 ```
 &lt; 和 &amp;。
 ```
 >> <span>&</span>字符：
 + 如果要输入 AT&T；，则必须写成：
 ```
 AT&amp;T
 ```
 + 如果输入网址中含有<span>&</span>，也同样需要换成实体字符：
 ```
 key&amp;value 
 ```
 才能放到链接标签的 href 属性里  
 + Merkdown 可以让你自然的书写字符，它可以处理字符转换。如果你使用的 <span>&</span> 字符是 HTML 字符实体的一部分，它会保留原状，否则它会被转换成 <span>&amp</span>
 + 类似的情况也会发生在 <span><</span> 符号上，因为 Markdown 允许兼容 HTML ，如果你是把 < 符号作为 HTML 标签的定界符使用，那 Markdown 也不会对它做任何转换
 + 但是如果把 <span><</span> 当成其他连接符号使用，如：
  ```
  4 < 5
  ```
  Markdown 将会把它转换为：
  ```
  4 &lt; 5
  ```
 不过*需要注意的是：code 范围内，不论是行内还是区块，<span><</span> 和 <span>&</span> 两个符号都一定会被转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML code(和 HTML 相对而言 HTML 语法中，你要把所有的 < 和 & 都转换为HTML实体，才能在HTML文件里面写出 HTML code)*。

>> **区块元素**

#### 段落和换行
 一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。    
 比方说，若某一行只包含空格和制表符，则该行也会被视为空行。普通段落不该用空格或制表符来缩进。  
 
+ 「由一个或多个连续的文本行组成」这句话其实暗示了 Markdown 允许段落内的强迫换行（插入换行符&lt;/br&gt;）
+ 如果你确实想要依赖 Markdown 来插入 &lt;br&gt;标签的话:
```
** 空格 + 空格 + enter = 换行 **
```
+ Markdown 中email式的区块引用和多段落的列表在使用换行来排版的时候，不但更好用，还更方便阅读。

#### 标题
 + Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。
 + 类 Setext 形式是用底线的形式，利用<span>=</span>（最高阶标题）和<span>-</span>（第二阶标题）
 + 类 Atx 形式则是在行首插入1到6个<span>#</span>，对应到标题1到6阶，例如：  
 ```
  # 这是H1标题  

  ## 这是H2标题  

  ### 这是H3标题  

  #### 这是H4标题  

  ##### 这是H5标题

  ###### 这是H6标题  
```
 + 我更推荐适用类 atx 样式的标题，这与我们平常的 html 标题标签基本上一致
 + 也可以选择性地「闭合」类 atx 样式的标题，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上<span>#</span>，而行尾的#数量也不用和开头一样。
 **行首的井字符数量决定标题的阶数**
#### 区块引用 Blockquotes
 + Markdown 标记区块引用是使用类似 email 中用 <span><</span> 的引用方式。
 + Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 > ：
```
 > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
 > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
```
 + Markdown 也允许你偷懒只在整个段落的第一行最前面加上 > ：
```
 > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
  consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
```
 + 区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：
```
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```
+ 引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：
```
> ## 这是一个标题。
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
```
任何像样的文本编辑器都能轻松地建立email型的引用。例如在 BBEdit 中，你可以选取文字后然后从选单中选择增加引用阶层。

#### 列表
   Markdown 支持有序列表和无序列表。
 + 无序列表使用星号、加号或是减号作为列表标记:
      * 这是一个无序列表
      + 这是一个无序列表
      - 这是一个无序列表  
 
 
+ 通过 table 键可以实现无序列表的嵌套:

   + 这是无序列表
        + 这是无序列表的嵌套
        + 这是无序列表的嵌套
            * 这是无序列表的嵌套的嵌套
            - 这是无序列表的嵌套的嵌套    
   * 这是无序列表
  
 + 有序列表则使用数字接着一个英文句点:
         1. 这是一个有序列表1
         2. 这是一个有序列表2
         3. 这是一个有序列表3
 
 **很重要的一点是，你在列表标记上使用的数字并不会影响 HTML 输出的顺序，上面的列表数字即使是胡乱排序的， HTML 也会按列表自上而下进行排列**   
 + Markdown 文件的列表数字和输出的结果不由编码的大小来决定,你可以懒一点，Markdown 可以完全不用在意数字的正确性。
 + 如果你使用懒惰的写法，建议第一个项目最好还是从 **1.** 开始，因为 Markdown 未来可能会支持有序列表的 start 属性。
 + 列表项目标记通常是放在最左边，也可以缩进最多3个空格，项目标记后面则一定要接着至少一个空格或制表符。

 + 要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：  
 ```
 * Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
   Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,  
   viverra nec, fringilla in, laoreet vitae, risus.
 ```
 + 但是如果你懒，那也行：  
 ```
*  Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
       Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
           viverra nec, fringilla in, laoreet vitae, risus.
 ```          
+ 列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符：  
 ```
1. This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.
2. Suspendisse id sem consectetuer libero luctus adipiscing.
 ```
+ 如果你每行都有缩进，看起来会整洁很多，当然，如果你很懒惰，Markdown 也允许：  
 ``` 
*  This is a list item with two paragraphs.
   This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
*      sit amet, consectetuer adipiscing elit.
 ```
+ 如果要在列表项目内放进引用，那 <span>></span>就需要缩进：  
 ```
 *  A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
 ```
 + 如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符：
 ```
*  一列表项包含一个列表区块：
        <代码写在这>
 ```
  当然，项目列表很可能会不小心产生，像是下面这样的写法：
  ```
  1986. What a great season. -->在行首出现数字-句点-空白的情况，避免这样的状况，你可以在句点前面加上反斜杠。
 ```
#### 代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用&lt;pre&gt;和&lt;code&gt;标签来把代码区块包起来。
要在 Markdown 中建立代码区块很简单，只要简单地缩进4个空格或是1个制表符就可以，例如，下面的输入：  
```
这是一个普通段落：

    这是一个代码区块。
```
Markdown 会转换成:
```
<p> 这是一个普通段落：</p>
  
<pre><code>这是一个代码区块。</pre></code>
```
这个每行一阶的缩进( 4 个空格或是 1 个制表符)，都会被移除，例如：
```
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```
会被转换为：
```
<p>Here is an example of AppleScript:</p>

<pre><code>tell application "Foo"
    beep
end tell
</pre></code>
```
一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。

在代码区块里面，<span>&</span>、<span><</span>、<span>></span>会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的HTML原始码，只需要复制贴上，再加上缩进就可以了，剩下的Markdown都会帮你处理，例如：
```
 <div class="footer">
        &copy; 2004 Foo Corporation
 </div>
 ```
 会被转换为：
```
<pre><code>&lt;div class="footer"&gt;
    &amp;copy; 2004 Foo Corporation
&lt;/div&gt;
</code></pre>
```
代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号，这表示你可以很容易地以 Markdown 语法撰写 Markdown 语法相关的文件。

#### 表格
Markdown语法的表格同样简单，由英文输入状态下的 \| 、： 和 \- 组成
+ 两行及以上的  \|  构成一个边框完整的单元格
+ \|  \|  之间输入文本内容
+ <span>：-----</span> 放在第二排，可以定义表头，是制作表格的必须元素
+ ：的位置决定文本的对齐方式：
  + 左对齐： ：------
  + 右对齐： -------：
  + 两端对齐：：------：
```
|   head    |   head    |   head    |
| :-------- |  -------: |   :---:   |
|   left    |   right   |   center  |
|   left    |   right   |   center  |
|   left    |   right   |   center  |
```

HTML输出    

|   head    |   head    |   head    |
| :-------- |  -------: |   :---:   |
|   left    |   right   |   center  |
|   left    |   right   |   center  |
|   left    |   right   |   center  |


#### 流程图
Markdown语法的流程图构成：
+ 和所有语言代码块一样流程图要写在代码块中 由<span>```</span>开始、闭合，所有符号都是在英文输入状态下输入
+ flow紧随在<span>```</span>之后
+ 一般上面写结构，下面写流程  
+ -\> ->控制流程的操作符，就是指向下一步操作的
+ 每一条代码都是一个流程

+ st=>start: 开始 
  + st 是变量名，变量名尽量语义化  
  + start 操作模块名，如：开始，结束，判断。命名严格，区别大小写。  
  + : 后面是要显示的文字 *注意：冒号后要加空格*  

+ st=>start: 开始   
  + st 是变量名，变量名尽量语义化  
  + start 操作模块名，如：开始，结束，判断。命名严格，区别大小写。  
  + : 后面是要显示的文字 *注意：冒号后要加空格*  
+ 可用模块都是 **变量名 => 对应模块 ： 关键字**
```
  + 开始 stert
            st=>start: 开始
  + 结束 end
            e=>end: 结束
  + 普通操作块 opration
            op1=>operation: 我的操作
            op2=>operation: 我的操作
  + 输入输出块 inputoutput
            io1=>inputoutput: 输入输出块1
            io2=>inputoutput: 输入输出块2
  + 子任务块
            sub1=>subroutine: 子任务1
            sub2=>subroutine: 子任务2
 
``` 
+ 判断位置和位置控制 
```
    + 判断流程控制
            cond1(yes)->op1  #yes 的时候回到 op1
            cond1(no)->e     #no 的时候 去结束
    + 位置指定
            cond1(no)->op2(right)->op1 #控制 op2 位置置于右边，再由op2 返回 op1 (好像不能向左)
            #还可以这样 cond1(no,right) cond1(yes)->e  
```
如：
```
```flow
st=>start: 开始
e=>end: 结束
op=>operation: 我的操作
cond=>condition: 确认？

st->op->cond
cond(yes)->e
cond(no)->op
```

HTML输出：

        ```flow
        st=>start: 开始
        e=>end: 结束
        op=>operation: 我的操作
        cond=>condition: 确认？

        st->op->cond
        cond(yes)->e
        cond(no)->op
        ```




#### 分隔线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：  
```
***  
* * *  
******  
- - -  
————————————————————————————  
```
### 区段元素
#### 链接
Markdown 支持两种形式的链接语法：**行内式**和**参考式**两种形式。
不管是哪一种，链接文字都是用 \[ 方括号 \] 来标记。 

>>** 行内式链接
+ 行内式的链接是用一个方括号紧跟着一个圆括号标识的：\[链接文字\]\(链接地址)
+ \[\]  是 &lt;a&gt;标签包含着的链接文字&lt;/a&gt;
+ \(\)  是 &lt;a&gt;标签 href 指向的链接地址
+ 链接后可跟 title 属性，title 不是必须属性，根据需来设置**

```
This is [an example](http://example.com/ "Title") inline link.

```
例如：
```
[Maekdown语法](https://github.com/WinSolstice/tools/blob/master/README.md title="WinSolstice的markdown语法总结")
+ 注释：[链接文字](链接地址 title)
```
Markdown会自动转换为：
```
<p><a href="https://github.com/WinSolstice/tools/blob/master/README.md" title="WinSolstice的markdown语法总结">
Maekdown语法</a></p>
```
HTML输出为：  
<p><a href="https://github.com/WinSolstice/tools/blob/master/README.md" title="Title">
Maekdown语法</a></p>  
如果你是要链接到同样主机的资源，你可以使用相对路径：

 ```
See my [About](/about/) page for details
```

>> **参考式链接  
+ 参考式链接是用两个方括号标识的：\[链接文字\]\[用以辨识链接的id\]
+ 然后在文件的任意处，你可以把这个id对应的链接地址定义出来：
+ 链接后可跟 title 属性，title 不是必须属性，根据需来设置**
```
This is [an example][id] reference-style link.
[id]: http://example.com/  "Optional Title Here"
```
例如：
```
[Maekdown语法][WinSolstice title="WinSolstice的markdown语法总结"] 
+ [链接文字][用以辨识链接的id title]

[WinSolstice]:https://github.com/WinSolstice/tools/blob/master/README.md
+ 定义 idid对应的链接地址 

```
Markdown会自动转换为：
```
<p><a href="https://github.com/WinSolstice/tools/blob/master/README.md" title="WinSolstice的markdown语法总结">
Maekdown语法</a></p>
```
+ 定义id对应的链接地址定义出来
```
[WinSolstice]:https://github.com/WinSolstice/tools/blob/master/README.md
```
HTML输出：  
[Maekdown语法][WinSolstice] 
[WinSolstice]:https://github.com/WinSolstice/tools/blob/master/README.md

**链接内容定义的形式为**

- 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字，
- 接着一个冒号，
- 接着一个以上的空格或制表符，
- 接着链接的网址，
- 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着,或者将title 属性放到下一行，也可以加一些缩进，若网址太长的话，这样会比较好看： 
+ 链接网址也可以用尖括号包起来：
+ 链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写，因此下面两个链接是一样的：  
下面这三种链接的定义都是相同：
```
[foo]: http://example.com/  Optional "Title Here"
[foo]: http://example.com/  Optional 'Title Here'
[foo]: http://example.com/  (Optional Title Here)
[id]: <http://example.com/>  "Optional Title Here"
```
*请注意：有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title。* 

+ 隐式链接标记功能让你可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要 让 "Google" 链接到 google.com，你可以简化成：
```
[Google]: []
```
然后定义链接内容：
```
[Google]: http://google.com/
```
由于链接文字可能包含空白，所以这种简化型的标记内也许包含多个单词：
```
Visit [Daring Fireball][] for more information.
```
然后接着定义链接：
```
[Daring Fireball]: http://daringfireball.net/
```
链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：
```
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```
如果改成用链接名称的方式写：
```
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```
上面两种写法都会产生下面的 HTML。
```
<p>I get 10 times more traffic from <a href="http://google.com/"
title="Google">Google</a> than from
<a href="http://search.yahoo.com/" title="Yahoo Search">Yahoo</a>
or <a href="http://search.msn.com/" title="MSN Search">MSN</a>.</p>
```
下面是用行内式写的同样一段内容的 Markdown 文件，提供作为比较之用：
```
I get 10 times more traffic from [Google](http://google.com/ "Google")
than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
[MSN](http://search.msn.com/ "MSN Search").
```
参考式的链接其实重点不在于它比较好写，而是它比较好读，比较一下上面的范例，使用参考式的文章本身只有 81 个字符，但是用行内形式的却会增加到 176 个字元，如果是用纯 HTML 格式来写，会有 234 个字元，在 HTML 格式中，标签比文本还要多。

使用 Markdown 的参考式链接，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的元数据移到段落文字之外，你就可以增加链接而不让文章的阅读感觉被打断。



#### 强调
Markdown 使用星号 \* 和底线 \_ 作为标记强调字词的符号，被 \* 或 \_ 包围的字词会被转成用&lt;em&gt;
标签包围，用两个 \** 或 \__ 包起来的话，则会被转成&lt;strong&gt;，例如：
```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores___
```

会转成：

```
<em>single asterisks</em>

<em>single underscores</em>

<strong>double asterisks</strong>

<strong>double underscores</strong>
```
你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。

强调也可以直接插在文字中间：
```
un*frigging*believable
```
但是**如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。**

如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：
```
\*this text is surrounded by literal asterisks\*
```
#### 代码

如果要标记一小段行内代码，你可以用反引号把它包起来（`），例如：
```
Use the `printf()` function.
```
会产生：
```
<p>Use the <code>printf()</code> function.</p>
```
如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：
```
``There is a literal backtick (`) here.``
```
这段语法会产生：
```
<p><code>There is a literal backtick (`) here.</code></p>
```
代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：
```
A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
```
会产生：
```
<p>A single backtick in a code span: <code>`</code></p>

<p>A backtick-delimited string in a code span: <code>`foo`</code></p>
```
在代码区段内，<span>&</span>和<span><</span>都会被自动地转成 HTML 实体，这使得插入 HTML 原始码变得很容易，Markdown 会把下面这段：
```
Please don't use any `<blink>` tags.
```
转为：
```
<p>Please don't use any <code>&lt;blink&gt;</code> tags.</p>
```
你也可以这样写：
```
`&#8212;` is the decimal-encoded equivalent of `&mdash;`.
```
以产生：
```
<p><code>&amp;#8212;</code> is the decimal-encoded
equivalent of <code>&amp;mdash;</code>.</p>
```

#### 图片

很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。

Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

>> + 行内式的图片语法:
+ 行内式的图片语法由：![图片名称]（图片地址)组成
+ 图片名称没有的情况选可以只写空格
+ 图片地址可以是图片的 url 或者是本地图片路径
+ 图片地址后可跟 title 属性，title 不是必须属性，根据需来设置
```
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```


>> + 参考式的图片语法则长得像这样：
```
![Alt text][id]
```
+ [id」是图片参考的名称，图片参考的定义方式则和连结参考一样：
```
[id]: url/to/image  "Optional title attribute"
```

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <&lt;img&gt;标签

_______________________________________________________________________________________________________________________________________
### 其它

#### 自动链接

+ Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用尖括号包起来， Markdown 就会自动把它转成链接。
一般网址的链接文字就和链接地址一样，例如：
```
<wawacai.xin.com>
```
Markdown 会转为：
```
<a href="http://wawacai.xin.com">http://wawacai.xin.com</a>
```
邮址的自动链接也很类似，只是 Markdown 会先做一个编码转换的过程，把文字字符转成 16 进位码的 HTML 实体，这样的格式可以糊弄一些不好的邮址收集机器人，例如：
```
<address@example.com>
```
Markdown 会转成：
```
<a href="&#x6D;&#x61;i&#x6C;&#x74;&#x6F;:&#x61;&#x64;&#x64;&#x72;&#x65;
&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;
&#109;">&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;
&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;</a>
```
在浏览器里面，这段字串（其实是 &lt;a href="mailto:address@example.com"&gt;address@example.com &lt;/a&gt;）会变成一个可以点击的「address@example.com」链接。

（这种作法虽然可以糊弄不少的机器人，但并不能全部挡下来，不过总比什么都不做好些。不管怎样，公开你的信箱终究会引来广告信件的。）

#### 反斜杠
Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 &lt;em&gt; 标签），你可以在星号的前面加上反斜杠：
```
\*literal asterisks\*
```
Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```
