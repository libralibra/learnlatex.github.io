---
layout: "page"
lang: "zh"
title: "使用learnlatex.org网站"
description: "本页介绍learnlatex.org网站及如何最好地使用它。"
permalink: /zh/help
---
<script>
  function acesettings() {
      editors['pre0'].execCommand("showSettingsMenu");
  }
</script>

# 帮助

## 网站导航

本课程包含16个核心课程，可以从[首页](./)的[目录]({{ "/" | absolute_url | append: page.lang | append: "/#toc" }})进入。

每个课程都有一个链接指向相同主题的相关课程，这些相关课程会更深入地探讨该主题。您应该能够在_无需_阅读额外课程的情况下完成全部16个课程。

在课程结束时，有一个或多个针对当前所用语言的特定课程，最后还有一个展示各种宏包的示例库，展示了本课程未涵盖的LaTeX用法。

---

## 示例

### 运行示例

每个示例都是一个完整的小型LaTeX文档，在页面中显示如下：

```latex
% !TEX program=lualatex

\documentclass[UTF8]{ctexart}
\begin{document}
示例文本。
\end{document}
```

<p class="hint">当您使用ctexart（或其他ctex文档类）时，无需加载xeCJK宏包（`\usepackage{xeCJK}`）。现代TeX引擎会根据需要自动加载对应的CJK宏包，简单的ctexart文档应该在所有引擎上都能正常工作。在编译LaTeX文档时最好使用LuaLaTeX引擎，不仅因为它在处理大型文档时更快，而且它是被推荐的编译引擎(https://www.texdev.net/2024/11/05/engine-news-from-the-latex-project)。</p>

每个示例都是完整的。但是您可能希望编辑它来做一些小的改动，也许是作为课程末尾的练习集的一部分。

编辑器使用的是[ACE](https://ace.c9.io/)。

您可以在[网站设置](settings)页面自定义编辑器使用的主题（例如使用深色主题，即在深色背景上显示浅色文本）。在网站的任何示例中使用<kbd>Ctrl</kbd>+<kbd>,</kbd>（Mac上使用<kbd>⌘</kbd>+<kbd>,</kbd>）是一种尝试不同主题的便捷方式。[这会显示一个面板](javascript:acesettings())，允许您更改所有ACE设置。

ACE代码库有一个[有用的编辑器快捷键页面](https://github.com/ajaxorg/ace/wiki/Default-Keyboard-Shortcuts)。

#### 运行示例的三种方式

* 使用Overleaf服务
* 使用TeXLive.net服务
* 使用本地安装的TeX系统

##### 使用Overleaf服务

Overleaf是最受欢迎的在线LaTeX编辑服务之一。示例下方的<button>在Overleaf中打开</button>按钮会将代码提交到[Overleaf](https://www.overleaf.com/about)。

如果您没有账号，或者浏览器中没有缓存账号信息，您将被重定向到登录页面，在那里您可以登录或注册Overleaf。这是一个免费服务，但需要您提供一些详细信息并同意使用条款和条件。

如果您的Overleaf账号已经在浏览器中缓存，Overleaf将在新标签页中打开，其中包含代码的新项目。您可以在Overleaf中编辑它，Overleaf会同时运行LaTeX处理您的代码，显示输出结果或错误日志。

与在TeXLive.net处理的文档不同，您可以将项目保存在Overleaf账号中，以后再回来继续编辑。

##### 使用TeXLive.net服务

示例下方的<button>在TeXLive.net运行</button>按钮会将代码提交到[TeXLive.net](https://texlive.net)服务[^1]。

TeXLive.net服务是专门为支持本网站而开发的，特别是利用了[PDF.js](https://mozilla.github.io/pdf.js/)来实现在移动设备和其他没有内置PDF阅读器的浏览器上显示PDF。

生成的PDF文档（或错误日志的部分内容）将立即显示在示例下方。会提供一个<button>删除输出文件</button>按钮，这样您可以移除这个输出（或者您可以将它留在原处，继续学习下面的课程内容）。

注意，**TeXLive.net**不需要任何登录或注册，所以它对小型示例来说非常方便，但本网站不提供保存您文档的机制。如果您离开页面，您对示例所做的任何更改都会丢失。

##### 本地安装的TeX系统

如果您已经在本地安装了TeX系统，那么您可以复制示例代码，可以通过显式选择它，也可以使用编辑器中的全选键盘快捷键（例如在Windows中使用<kbd>Ctrl</kbd>+<kbd>A</kbd> <kbd>Ctrl</kbd>+<kbd>C</kbd>）。这会将代码放入您的操作系统剪贴板，这样您就可以使用本地编辑器启动一个空白文档，然后粘贴文本。

### 故障排除

我们的示例是基于使用最新的LaTeX安装。它们都能在我们的两个在线演示系统中运行，所以如果您在我们提供的示例中遇到错误，您可能需要检查您的LaTeX系统是否需要更新。

---

## 选择TeX引擎

提交示例文档时，默认将使用`pdflatex`引擎。

您可以通过使用以下形式的注释来强制选择`latex`、`pdflatex`、`xelatex`、`lualatex`、`platex`或`uplatex`：

`% !TEX ` _任意文本_ `lualatex`

其中开头的空格是可选的，大小写不敏感，第一个和最后一个单词之间的_任意文本_也会被忽略。

这允许使用某些TeX编辑器使用的形式`% !TEX program=pdflatex`，但不要求`program=`，目前仅限于指定在线系统支持的引擎之一。

您可以在[本网站的一些示例](more-14)中看到使用注释来指定LuaLaTeX的例子。

如果指定了`platex`或`uplatex`，那么还会使用`dvipdfmx`程序来从这些变体生成的DVI文件生成PDF结果。类似地，如果指定了`latex`，则会使用`dvips`和`ps2pdf`。

如果在`% !TeX`注释中未指定引擎，则将使用`pdflatex`，除非您在[网站设置](settings)页面上指定了默认TeX引擎。

---

## 选择如何显示输出

如果您使用TeXLive.net系统，则默认情况下使用[PDF.js](https://mozilla.github.io/pdf.js/)显示运行示例的PDF输出。这在各种浏览器中提供了一致的行为。

如果您更喜欢使用浏览器的默认PDF阅读器（无论是内置的还是您配置的外部应用程序），请添加以下形式的注释：

`% !TEX ` _任意文本_ `pdf`

默认行为可以通过使用`pdfjs`作为最后一个标记来显式指定。出于调试目的，即使文档没有错误地生成了PDF，有时您也可能想要返回日志文件。这可以通过在注释中使用`log`作为最后一个标记来指定。

作为使用`% !TeX`注释的替代方法，您可以在[网站设置](settings)页面上指定网站默认返回参数。这些设置是特定于每个浏览器的，因此例如您可以在移动设备上使用默认的`pdfjs`设置，但在桌面浏览器上使用`pdf`来使用其默认的PDF渲染。

---

## HTML输出（make4ht、LaTeXML、lwarp）

如果使用TeXLive.net系统，则可以指定额外的返回选项：`make4ht`、`LaTeXML`或`lwarp`。这些会在页面内的框架中返回一个或多个HTML页面。它们可以与`xelatex`或`lualatex`以及默认的`pdflatex`处理一起指定。

要启用此输出，请添加以下形式的注释：

```
% !TeX make4ht
```
{: .noedit :}

将`make4ht`替换为`LaTeXML`或`lwarp`来指定这些系统。

或者，您可以在[网站设置](settings)页面上将`make4ht`、`LaTeXML`或`lwarp`指定为默认返回选项。

如果使用本地安装的TeX系统，可以通过执行以下命令获得与`make4ht`选项相同的输出：

```
make4ht  document.tex "learnlatex4ht,2,mathml,mathjax,svg"
```
{: .noedit :}

如果指定了XeLaTeX或LuaLaTeX，则需要添加`-x`或`-l`选项。

在本地运行时，可以使用其他配置。请参阅[make4ht手册](https://texdoc.org/pkg/make4ht)。

对于`LaTeXML`，您需要安装LaTeXML（它不是TeX Live或MiKTeX的一部分）并使用：

```
latexml document.tex > document.xml
latexmlpost --format=html5 \
   --javascript='https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js' \
   --destination=document.html" document.tex
```
{: .noedit :}

可以使用许多其他LaTeXML配置，[如手册中所述](https://dlmf.nist.gov/LaTeXML/manual/)。

`lwarp`配置在这里没有记录，它有点实验性并且可能会改变。当前版本可以在[源代码库](https://github.com/davidcarlisle/latexcgi/blob/main/lwarp/latexcgilwarp)中看到。

---

[^1]: 注意，在网站开发期间，我们还使用了[LaTeX.Online](https://latexonline.cc/)和[LaTeX-on-HTTP](https://github.com/YtoTech/latex-on-http)，我们感谢这些服务的开发者在早期阶段使本网站的示例可用。


