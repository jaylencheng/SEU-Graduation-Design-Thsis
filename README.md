# SEU-Graduation-Design-Thsis
 A LATEX module for Graduation design (thesis) in southeast university(China) .

# 1.介绍
seucata.cls提供了符合规范的东南大学本科毕业设计论文的$\LaTeX$模板。
模板的格式尽量满足东南大学教务处的要求，当然由于水平有限其中错
漏在所难免，我们欢迎东大的 $\LaTeX{er}$ 一起参加开发和完善。如果您对开发和完善seucata
感兴趣、有任何想法或建议，请与Cata联系。该项目主页[GitHub:](https://github.com/jaylencheng/SEU-Graduation-Design-Thsis)。
联系方式：Email(jaylencheng@outlook.com)or[网页留言：](https://jaylencheng.github.io).

本模板基于早期许元同学等人发布的\verb+seuthesix.cls+，其版本见网址：
[https://github.com/zhimengfan1990/seuthesix](https://github.com/zhimengfan1990/seuthesix)
由于其中只有硕博士论文的模板，个人将其修改为符合本科毕业设计内容的模板。

# 2.版权声明
这一程序是自由软件，你可以遵照自由软件基金会发布的《GNU 通用公共许可证条款第三版》来修改和重新发布这一程序，或者 (根据您的选择) 用任何更新的版本。发布这一程序的目的是希望它有用，但没有任何担保。甚至没有适合特定目的的隐含的担保。更详细的情况请参阅《GNU 通用公共许可证》
[http://www.gnu.org/licenses/gpl.html](http://www.gnu.org/licenses/gpl.html)

# 3.版本历史
> item[1.0] 

2016/01/11，基于\seuthesis 构建新的\seuthesix 文档类。放弃\seuthesis 
的xeCJK方案 ，直接采用\verb+ctexrep.cls+ 构建\verb+seuthesix.cls+。

>本项目

对本科学位论文的支持。

                   
# 4.下载和安装
## 下载  
本项目最新源码可以到本项目在 GitHub 中找到，访问
[https://github.com/jaylencheng/SEU-Graduation-Design-Thsis](https://github.com/jaylencheng/SEU-Graduation-Design-Thsis)下载。

## 安装
将宏包中的文件放在当前工作目录(与 \verb+.tex+ 文件放在同一目录下)即可，当然也可以安装到 \TeX 系统中，不过需要注意是参考文献样式文件 \verb+.bst+ 必须置于 \verb+TEXMF/bibtex/bst+ 目录或子目录下。

本模板在 $\TeX{Live}$ 2015(Windows 7 和 Linux Mint 17.1 环境下) 通过\hologo{XeLaTeX} 编译通过。注意，若在Linux 上编译，由于Linux缺少所依赖的字体(宋体、黑体、楷体、Times New Roman)，因此需要用户自己安装这些字体，否则编译时会报错。将Windows中的字体复制到Linux中安装即可。

原则上，只要安装了\TeX{Live} 2015和宋体、黑体、楷体、Times New Roman等字体，本模板也支持OS X。（已经做过OS X 上的测试。）

如有您在使用中有任何问题，欢迎与我们联系。

# 5.使用说明
## 内容

东南大学本科毕业设计论文应包括如下部分：
 \item 中文封面

 \item 中文页面

 \item 英文页面（可选）

 \item 论文独创性声明和使用授权声明

 \item 中文内容提要及关键词

 \item 英文内容提要及关键词

 \item 目录

 \item \fbox{符号、变量、缩略词等本论文专用术语的注释表}（可选）

 \item 正文

 \item \fbox{致谢}

 \item 参考文献

 \item  \fbox{附录}

 \end{enumerate}

 并按此顺序排列，其中\fbox{加方框的条目}为可选。

## 模板整体框架
使用 \seuthesix 模板的整体框架如下所示，其中\verb+<...>+表示可替换的文本(replaceable text)。
```latex
\documentclass[openany,masters]{seucata}
\usepackage{hologo}
\usepackage{pdfpages}
\begin{document}
\categorynumber{000} 
\UDC{000}            
\secretlevel{公开}   
\studentid{000000}   
\title{欢迎神仙们引用我的模板}{求星星}{Welcome my God}{STAR}
\author{Jaylen Cheng}{jaylencheng.github.io}
\advisor{爱因斯坦}{教授}{Donald E. Knuth}{Prof.}
\coadvisor{由乃}{副教授}{Leslie Lamport}{Associate Prof.} 
\degreetype{神学}{Master of \TeX}
\major{神的产生专业}
\submajor{天使降临系}
\defenddate{\today}
\authorizedate{\today}
\committeechair{朗道}
\reviewer{Newton}{Gauss}
\department{东南大学Cata学院}{School of Cata in SEU}
\seuthesisthanks{本课题的研究获God bless Cata project 赞助:%
\url{jaylencheng.github.io}}
%\makebigcover
\makecover
\begin{abstract}{<\TeX, \LaTeX, 文档类， 学位论文>}
<本文介绍如何使用\seuthesix 文档类撰写东南大学学位论文。>
\end{abstract}
%生成中文摘要和关键词
\begin{englishabstract}{<\TeX, \LaTeX, document class， thesis/dissertation>}
<This work presents an introduction of how to use \seuthesix document class to 
typeset the thesis/dissertation of Southeast University.>
\end{englishabstract}
%生成英文摘要和关键词
\tableofcontents%生成目录
\setnomname{<术语表名称>}%设置术语表的名称，用于\listofothers
\listofothers%生成图、表等目录，没有可以不写

\mainmatter
%开始正文

\chapter{<绪论>}
\section{<研究背景>}
\section{<本论文的工作>}
...


\chapter{<...>}
\section{<...>}
...


...


\chapter{<全文总结>}
...

\acknowledgement
<感谢每一个给予帮助的人...>
致谢，没有可以不写

\thesisbib{<bib文件名>}
参考文献

\appendix
\chapter{<...>}
...

\chapter{<...>}
...
%附录部分，没有可以不写

\resume{<作者简介>}
<简介内容...>
%作者简介，没有可以不写

\end{document}
%文档到此结束
```

# 5.注意事项
## 文献引用
根据要求，文献引用应为数字标签(numerical label)，上标形式。但是有时也会用到正常形式，即非上标形式，用于正文叙述。为此分别提供了两个命令来实现。

\cite{<citation_key>}


用于实现上标的数字形式文献引用\cite{knuth}。

\citen{<citation_key>}

用于实现正常(非上标，normal)的数字形式文献引用\citen{mittlebach}。

## 参考文献格式

## 图表格式处理

图名、表名字体字号已经有文档类 设定好，用户无需再次设定。但是，用户需要让它居中。图名位于图下方，
表名位于表上方。图片文件可直接置于当前工作目录，也可置于当前工作目录的\texttt{figures}子目录下(用户根据需要，自己创建该子目录)。
图片名称只需要给出名称和扩展名，无需给出完整的路径。图\ref{logo}给出了一个图的例子。表\ref{entrytable}给出了一个表的例子。

```latex
\begin{figure}
\centering
\includegraphics[...]{...}
\caption{...}
\label{...}
\end{figue}
...
\begin{table}
\centering
\caption{...}
\label{...}
\begin{tabular}{...}
...
\end{tabular}.
\end{table}

\end{verbatim}
}

\begin{figure}
\centering
\caption{\seuthesix logo\label{logo}}
\chuhao \seuthesix
\end{figure}
```

