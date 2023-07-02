---
title: 掌握 Markdown
date: 2016-07-03 11:00:16
categories:
    - markdown
tags:
    - md
toc: true
comments: false
---

Markdown 是一种标记语言，语法简单，容易编写和阅读。可用于编写文档或者文章，文章结构清晰且简单，比使用传统的 word 更能提高效率。

# 一 基础语法

## 1. 标题语法

下面是 6 个 markdown 的标题语法。

```markdown
# 展示一级标题

## 展示二级标题

### 展示三级标题

#### 展示四级标题

##### 展示五级标题

###### 展示六级标题
```

下面是不同标题等级的展示效果。

> # 展示一级标题
>
> ## 展示二级标题
>
> ### 展示三级标题
>
> #### 展示四级标题
>
> ##### 展示五级标题
>
> ###### 展示六级标题

按上面的语法，使用 # 进行写标题，能有 6 个级别的标题等级。

好的写标题方式：

> 1. #号与标题文字间有一个空格。
> 2. 标题上下有空行。

## 2. 段落语法

在 Markdown 文档中写段落时，独立的一段文字，上下使用空白行进行与其他段落进行分离即可。书写一段文字时，不要使用 tab 制表符或者空格进行段落的首字缩进。

```markdown
# 我是标题

这是第一段文字，与标题有一个空行,与下面第二段文字也有空行。

这是第二段文字。每段文字开头不需要缩进。
```

## 3. 新行语法（换行语法）

在一段文字中，需要将某句文字进行新行显示，只要在它的前一句末尾加两个空格（结尾空格）。

```markdown
这段文字中，需要将一句话使用新行显示。  
新行句子。这个新行句子与前面句子不要有空行。
```

## 4. 强调语法

用于对相关文本进行加粗和斜体设置。

### 4.1 加粗

使用 \*\* 星号对文本进行包裹。

```markdown
这句话中重要的是：**什么？**
```

> 这句话中重要的是：**什么？**

### 4.2 斜体

使用 \_ 下划线，或者 一个 \* 星号对文本进行包裹。

```markdown
这句话中重要的是：_什么？_
```

> 这句话中重要的是：_什么？_

### 4.3 加粗且斜体

```markdowm
这句话中重要的是：**_什么？_**
```

> 这句话中重要的是：**_什么？_**

## 5. 引用语法

将文本展示在引用块中，使用 > 创建一个引用块。

```markdowm
> 业精于勤，荒于嬉。
```

> 业精于勤，荒于嬉。

嵌套引用

```markdown
> 你喜欢的句子是什么？
>
> > 种一棵树最好的时间是十年前，其次是现在。
```

> 你喜欢的句子是什么？
>
> > 种一棵树最好的时间是十年前，其次是现在。

## 6. 列表语法

列表方式有两种，无序列表使用 \- 在每个项目前，有序列表使用数字。

### 6.1 无序列表

```markdown
-   html
-   css
-   js
```

> -   html
> -   css
> -   js

### 6.2 有序列表

```markdown
1.  vue
2.  react
3.  angular
```

> 1.  vue
> 2.  react
> 3.  angular

## 7. 链接语法

使用以下语法，可以使文本具有链接功能，点击后跳转到指定页面。

```markdown
[百度](www.baidu.com)
[GitHub](www.github.com)
```

> [百度](www.baidu.com)  
> [GitHub](www.github.com)

## 8. 图片语法

文章中引入图片，也是和链接语法类似，只需要在前面多加一个 感叹号 !。

```markdowm
本地图片
![avater](/images/avatar.jpg)

互联网图片
![avater](https://upload.wikimedia.org/wikipedia/commons/5/56/Tiger.50.jpg)
```

> 本地图片
> ![avatar](/images/avatar.jpg)
>
> 互联网图片
> ![avatar](https://upload.wikimedia.org/wikipedia/commons/5/56/Tiger.50.jpg)

## 9. 分割线语法

在文章中使用分割线，只要使用 `---` 三个中横线。

```markdown
段落 1，段落 1

---

段落 2，段落 2
```

> 段落 1，段落 1，下面有一条分隔线。
>
> ---
>
> 段落 2，段落 2

## 10. 代码语法

在文章中，显示代码块，使用 `` 反引号包裹代码。

```js
var http = require('http');
http.createServer(function (req, res) {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('Hello World\n');
}).listen(1337, '127.0.0.1');
console.log('Server running at http://127.0.0.1:1337/');
```

# 二 Markdown 编辑器

[在线编辑器](https://markdown.com.cn/editor/)

# 三 参考

[Markdown 官方教程](https://markdown.com.cn/)
[Markdown 指南中文版](https://www.markdown.xyz/)
[Markdown 基础语法](https://www.markdownguide.org/basic-syntax)
[Markdown 扩展语法](https://www.markdownguide.org/extended-syntax)
[markdowntutorial](https://www.markdowntutorial.com/zh-cn/)
