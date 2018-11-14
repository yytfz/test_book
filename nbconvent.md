# nbconvert：将笔记本转换为其他格式

`nbconvert`工具主要允许您将Jupyter`.ipynb`笔记本文档文件转换为另一种静态格式，包括HTML，LaTeX，PDF，Markdown，reStructuredText等。`nbconvert`当用于以编程方式执行笔记本时，还可以为您的工作流程增加工作效率。

如果用作Python库（），则在项目中添加笔记本转换。例如，用于在Jupyter Notebook Web应用程序中实现“下载为”功能。当用作命令行工具（调用为）时，用户可以方便地将一个或一批笔记本文件转换为另一种格式。`importnbconvertnbconvertnbconvertjupyternbconvert...`

## 一、安装

Nbconvert为pip和conda打包，因此您可以使用以下命令安装它：

```
pip install nbconvert 
# or
conda install nbconvert
```

如果您是Python新手，我们建议安装[Anaconda](https://www.continuum.io/downloads)，这是一个包含nbconvert和其他Jupyter组件的Python发行版。

> 重要：要解锁nbconvert的全部功能，需要Pandoc和TeX（特别是XeLaTeX）。这些必须单独安装。

### 安装Pandoc

为了将markdown转换为HTML以外的格式，nbconvert使用[Pandoc](http://pandoc.org/)（1.12.1或更高版本）。

要在Linux上安装pandoc，通常可以使用包管理器：

```
sudo apt-get install pandoc
```

### 安装

为了转换为PDF，nbconvert使用TeX文档准备生态系统。它生成一个中间`.tex`文件，由XeTeX引擎使用LaTeX2e格式（通过`xelatex`命令）编译以生成PDF输出。

5.0版中的新功能：我们使用XeTeX作为渲染引擎而不是pdfTeX（与早期版本一样）。XeTeX可以通过本机操作系统库访问字体，它更好地支持OpenType格式化字体和Unicode字符。

手动安装完整的TeX环境（包括XeLaTeX和必要的支持包）可能会非常棘手。幸运的是，有一些软件包使这更容易。这些包特定于不同的操作系统：

Linux：

* [TeX Live](http://tug.org/texlive/)
  * 例如在Debian或Ubuntu上：
    `sudo apt-get install texlive-xetex`
* macOS（OS X）：
  [MacTeX](http://tug.org/mactex/)
  。
* Windows：
  [MikTex](http://www.miktex.org/)

由于nbconvert依赖于标准TeX发行版中包含的包和字体，因此如果您没有完整安装，则可能无法使用nbconvert的标准工具将笔记本转换为PDF。

## 二、用作命令行工具

运行 `nbconvert`脚本的命令行语法是：

```
$ jupyter nbconvert --to FORMAT notebook.ipynb
```

这会将Jupyter笔记本文件`notebook.ipynb`转换为`FORMAT`字符串给出的输出格式。

### 默认输出格式：

默认输出格式为HTML，`--to`可省略参数：

```
$ jupyter nbconvert notebook.ipynb
```

### 目前支持的输出格式：

1，HTML

,2，LaTeX

3，PDF

4，Reveal.js HTML slideshow

5，Markdown

6，reStructuredText

7，executable script

8，notebook























