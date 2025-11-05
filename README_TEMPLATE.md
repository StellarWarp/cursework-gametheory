# LaTeX Two-Column Template / LaTeX 双栏模板

这是一个符合学术论文格式要求的 LaTeX 双栏模板。

This is a LaTeX two-column template that meets academic paper formatting requirements.

## 特性 / Features

### 一、页面设置（A4纸）/ Page Setup (A4 Paper)

* **纸张大小 / Paper Size**: A4 (595.28 x 841.89 pts)
* **分栏 / Layout**: 双栏（Two-column）布局
* **页边距 / Margins**: 
  - 上边距 / Top: 20mm
  - 下边距 / Bottom: 20mm
  - 左边距 / Left: 15mm
  - 右边距 / Right: 15mm
  - 栏间距 / Column separation: 7mm

### 二、摘要与关键词 / Abstract and Keywords

1. **摘要 / Abstract**:
   - **位置 / Position**: 在作者信息下方，跨越两栏（全栏宽度显示）/ Below author info, spanning both columns (full width)
   - **标题 / Title**: 使用加粗字体 / Bold font ("**Abstract:**" or "**摘要:**")
   - **内容 / Content**: 
     - 使用比正文稍小的字号 / Smaller font size than body text
     - 首行不缩进 / No first-line indentation
     - 通常 150-250 字 / Typically 150-250 words

2. **关键词 / Keywords**:
   - **位置 / Position**: 摘要下方，跨越两栏 / Below abstract, spanning both columns
   - **样式 / Style**: 
     - 前置"Key words:"或"关键词：" / Prefixed with "Key words:" or "关键词："
     - 用分号或逗号分隔 / Separated by semicolons or commas

## 文件说明 / Files

- `template.sty`: LaTeX 样式包文件，定义了模板的格式设置 / Style package file defining template formatting
- `example.tex`: 示例文档，展示如何使用模板 / Example document showing how to use the template

## 使用方法 / Usage

### 基本用法 / Basic Usage

```latex
\documentclass[a4paper,twocolumn]{article}
\usepackage{template}

% 如果需要中文支持，添加以下包
% For Chinese support, add:
% \usepackage[UTF8]{ctex}

\title{Your Paper Title}
\author{Author Name\\Institution Name}
\date{}

\begin{document}

\maketitle

% 摘要和关键词需要跨越两栏
% Abstract and keywords should span both columns
\twocolumn[
\begin{@twocolumnfalse}

\begin{abstract}
\noindent
Your abstract text goes here. The abstract should be concise yet informative...
\end{abstract}

\keywords{keyword1; keyword2; keyword3}

\vspace{1em}
\end{@twocolumnfalse}
]

% 正文从这里开始双栏排版
% Main content starts here in two-column format
\section{Introduction}
Your content here...

\end{document}
```

### 中英文双语文档 / Bilingual Documents

对于需要中英文双语的文档，使用 `ctex` 包：

For bilingual Chinese-English documents, use the `ctex` package:

```latex
\documentclass[a4paper,twocolumn]{article}
\usepackage{template}
\usepackage[UTF8]{ctex}

\title{中文标题\\English Title}
\author{作者姓名\\Author Name\\
        单位名称\\Institution Name}
\date{}

\begin{document}

\maketitle

\twocolumn[
\begin{@twocolumnfalse}

\begin{abstract}
\noindent
English abstract text...

中文摘要文本...
\end{abstract}

\keywords{English keywords; Chinese keywords; 中文关键词}

\vspace{1em}
\end{@twocolumnfalse}
]

\section{引言 / Introduction}
正文内容...

\end{document}
```

## 编译 / Compilation

### 英文文档 / English Documents

```bash
pdflatex your-document.tex
```

### 中文文档 / Chinese Documents

使用 XeLaTeX 以获得更好的中文支持：

Use XeLaTeX for better Chinese support:

```bash
xelatex your-document.tex
```

## 依赖包 / Required Packages

- `geometry`: 页面设置 / Page layout
- `abstract`: 摘要格式化 / Abstract formatting
- `ctex` (可选): 中文支持 / Chinese support (optional)

## 自定义 / Customization

您可以通过修改 `template.sty` 文件来自定义模板：

You can customize the template by modifying `template.sty`:

- **页边距 / Margins**: 修改 `\geometry` 命令中的参数 / Modify parameters in `\geometry` command
- **字体大小 / Font sizes**: 修改 `\abstracttextfont` 等命令 / Modify commands like `\abstracttextfont`
- **栏间距 / Column separation**: 调整 `columnsep` 参数 / Adjust `columnsep` parameter

## 示例 / Example

参见 `example.tex` 文件，它展示了一个完整的双栏论文示例，包括：

See `example.tex` for a complete two-column paper example, including:

- 标题和作者信息 / Title and author information
- 全宽摘要和关键词 / Full-width abstract and keywords
- 多级章节标题 / Multi-level section headings
- 双栏正文内容 / Two-column body content
- 参考文献 / References

## 许可证 / License

该模板可以自由使用和修改。

This template is free to use and modify.
