---
layout: "lesson"
lang: "zh-hans"
title: "更多内容：逻辑结构"
description: "本课展示了如何设置文档标题，以及如何制作描述列表。"
toc-anchor-text: "更多内容：逻辑结构"
---

## 文档标题

LaTeX 为文档标题提供了一些逻辑标记：三个用于设置"元数据"的命令和一个用于使用它的命令。

```latex
% !TEX program=lualatex

\documentclass{ctexart}
\begin{document}
\author{张三 \and 李四}
\title{我做的一些事情}
\date{2020年4月1日}
\maketitle

一些普通的文本。
\end{document}
```

如你所见，命令`\author`、`\title`和`\date`用于保存信息，而`\maketitle`则使用这些信息。你也可以用`\and`来分隔多个作者。命令`\author`、`\title`和`\date`需要在`\maketitle`之前使用。这里，我们把它们放在了文档正文中：它们也可以在导言区使用，但如果你使用babel宏包的快捷方式，它们在那里不会生效。

`\maketitle`提供的设计取决于文档类（参见[第5课](lesson-05)）。当你想要自定义设计时，可以使用`titlepage`环境，但这超出了本入门教程的范围。如果你想要自己设计文档，你可以使用一个可定制的文档类，如`memoir`，或者从 LaTeX 的基础类之一（如`book`）开始，将其作为起点。

## 描述列表

除了"有序"和"无序"类型的列表外，LaTeX 还提供了另一种不太常见的列表：描述列表。

```latex
% !TEX program=lualatex

\documentclass{ctexart}
\begin{document}

\begin{description}
\item[狗：] 犬属的成员，属于狼形犬科，是最广泛分布的陆地食肉动物。
\item[猫：] 小型食肉哺乳动物的家养物种。它是猫科中唯一的家养物种，通常被称为家猫，以区别于该科的野生成员。
\end{description}

\end{document}
```

## 练习

尝试设置不同的`\author`、`\title`和`\date`信息来测试`\maketitle`。你 _必须_ 提供哪些信息？这些命令中必须包含作者、标题和日期吗？

制作一些描述列表，并尝试将其中一些嵌套在其他列表（有序、无序或描述列表）中。
