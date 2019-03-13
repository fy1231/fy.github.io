---
layout: post
title: Markdown
date:   2018-12-17 13:31:55 +0800
---

{{ page.title }}
================
Markdown: Syntax
================
## Overview 概述
### Philosophy 哲学思想
Markdown is intended to be as easy-to-read and easy-to-write as is feasible. 设计尽可能的易于读写

可读性 Readability, however, is emphasized above all else.

### Inline 内联 HTML
HTML is a *publishing* format; Markdown is a *writing*
format. 

由于Markdown是为了便于书写设计，必要时候直接使用HTML本身。

Block-level HTML elements must be separated.  
Markdown formatting syntax is not processed within block-level HTML tags.  
Span-level HTML tags can be used anywhere.  
Unlike block-level HTML tags, Markdown syntax *is* processed within span-level tags.  
与块级元素不同，内联元素中可以使用Markdown语法。

### Automatic Escaping for Special Characters 特殊字符自动转义
In HTML, there are two characters that demand special treatment: `<` and `&`. Left angle brackets are used to start tags; ampersands are used to denote HTML entities. If you want to use them as literal characters, you must escape them as entities, e.g. `&lt;`, and `&amp;`.

两个特殊字符：left angle bracket `<` 作为标签起始；ampersand `&` 表示转义。

Markdown allows you to use these characters naturally, taking care of all the necessary escaping for you. If you use an ampersand as part of an HTML entity, it remains unchanged; otherwise it will be translated into `&amp;`.

Markdown会根据情况自动判断是否转义。

However, inside Markdown code spans and blocks, angle brackets and ampersands are *always* encoded automatically. This makes it easy to use Markdown to write about HTML code. (As opposed to raw HTML, which is a terrible format for writing about HTML syntax, because every single `<` and `&` in your example code needs to be escaped.)

代码标签内总是转义，记录HTML代码比直接用HTML更加方便。

## Block Elements 块元素
### Paragraphs and Line Breaks 段落与换行
A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. (A blank line is any line that looks like a blank line -- a line containing nothing but spaces or tabs is considered blank.) Normal paragraphs should not be indented with spaces or tabs.

段落之间以空行隔开。

When you *do* want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

行末两个或两个以上空格换行。

### Headers 标题
Markdown supports two styles of headers, Setext and atx. 两种风格

Setext-style headers are "underlined" using equal signs (for first-level headers) and dashes (for second-level headers).

标题下方划等号和破折号作为一级标题和二级标题。

Any number of underlining `=`'s or `-`'s will work. 任意数量等号或破折号都行。

Atx-style headers use 1-6 hash characters at the start of the line, corresponding to header levels 1-6.

行前置1-6个井号对应1-6级标题。

### Blockquotes 块级引用
Markdown uses email-style `>` characters for blockquoting. 

段落或行前置 `>` 表示块级引用。

Blockquotes can be nested (i.e. a blockquote-in-a-blockquote) by adding additional levels of `>`.

块级引用可以嵌套。

Blockquotes can contain other Markdown elements, including headers, lists, and code blocks.

块级引用内可以包含Markdown元素。

### Lists 列表
Markdown supports ordered (numbered) and unordered (bulleted) lists. 有序列表和无序列表。

Unordered lists use asterisks, pluses, and hyphens -- interchangably.

无序列表可以用星号、加号、连号之一表示。

Ordered lists use numbers followed by periods.

有序列表则使用数字与句号的组合。

It's important to note that the actual numbers you use to mark the list have no effect on the HTML output Markdown produces.

转换得到的有序列表与标记列表的数字数值无关。

List markers typically start at the left margin, but may be indented by up to three spaces. List markers must be followed by one or more spaces or a tab.

If list items are separated by blank lines, Markdown will wrap the items in `<p>` tags in the HTML output.

List items may consist of multiple paragraphs. Each subsequent paragraph in a list item must be indented by either 4 spaces or one tab.

列表内容缩进。

To avoid triggering an ordered list by accident, you can backslash-escape the period.

### Code Blocks 代码块
Markdown wraps a code block in both `<pre>` and `<code>` tags.

To produce a code block in Markdown, simply indent every line of the block by at least 4 spaces or 1 tab. 每行缩进4个空格形成代码块。

One level of indentation -- 4 spaces or 1 tab -- is removed from each line of the code block.

A code block continues until it reaches a line that is not indented (or the end of the article). 代码块在非缩进行结束。

Regular Markdown syntax is not processed within code blocks. 常规Markdown语法在代码块在中不起作用。

### Horizontal Rules 水平线
You can produce a horizontal rule tag (`<hr />`) by placing three or more hyphens, asterisks, or underscores on a line by themselves. 行中只有三个或三个以上连号或星号为水平线。

## Span Elements
### Links 链接
Markdown supports two style of links: *inline* and *reference*. 两种链接方式。

To create an inline link, use a set of regular parentheses immediately after the link text's closing square bracket. Inside the parentheses, put the URL where you want the link to point, along with an *optional* title for the link, surrounded in quotes.

在一个包含链接文字的方括号后跟一个包含链接地址的括号创建内联链接。

Reference-style links use a second set of square brackets, inside which you place a label of your choosing to identify the link.

用第二个包含标签的方括号创建引用链接，并在文档任意地方定义。

The point of reference-style links is not that they're easier to write. The point is that with reference-style links, your document source is vastly more readable. In the raw HTML, there's more markup than there is text. 引用方式的链接更加可读。

### Emphasis 强调
Markdown treats asterisks (`*`) and underscores (`_`) as indicators of emphasis. Text wrapped with one `*` or `_` will be wrapped with an HTML `<em>` tag; double `*`'s or `_`'s will be wrapped with an HTML `<strong>` tag.

一个星号或下划线包裹表示斜体，两个表示加粗。

### Code 代码
To indicate a span of code, wrap it with backtick quotes (`` ` ``). Unlike a pre-formatted code block, a code span indicates code within a normal paragraph. 

使用反引号包裹形成代码段，可在段落中显示。

The backtick delimiters surrounding a code span may include spaces -- one after the opening, one before the closing. This allows you to place literal backtick characters at the beginning or end of a code span.

如以反引号开头或结尾应当添加空格。

### Images 图片
Markdown uses an image syntax that is intended to resemble the syntax for links, allowing for two styles: *inline* and *reference*.

插入图片语法与链接类似，以叹号开头。

## Miscellaneous
### Automatic Links
Markdown supports a shortcut style for creating "automatic" links for URLs and email addresses: simply surround the URL or email address with angle brackets. What this means is that if you want to show the actual text of a URL or email address, and also have it be a clickable link>.

尖括号包围的网址或邮箱自动形成链接。

### Backslash Escapes
Markdown allows you to use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown's formatting syntax. For example, if you wanted to surround a word with literal asterisks (instead of an HTML `<em>` tag), you can use backslashes before the asterisks.

Markdown provides backslash escapes for the following characters:

    \   backslash
    `   backtick
    *   asterisk
    _   underscore
    {}  curly braces
    []  square brackets
    ()  parentheses
    #   hash mark
	+	plus sign
	-	minus sign (hyphen)
    .   dot
    !   exclamation mark
