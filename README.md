# GDUTreport
a report package for the report in GDUT.

广东工业大学报告LaTex模板。



## Installation

直接把这些文件复制到你要编译的tex的文件夹内。

### or 放到宏包文件夹中(推荐)

**LINUX users**

1.  把整个文件夹放到texlive的宏包安装目录下。

`cp -r GDUTreport/ /usr/local/texlive/texmf-local/tex/latex/local`

2.  自动补全文件(.cwl)放置到texdoc路径下

`cp gdutreport.cwl /usr/local/texlive/2016/texmf-dist/doc/latex/gdutreport`

>   具体路径请对照自己的实际情况修改

**Windows users**

>   尚未在Windows下尝试过

# How to use

## template

```latex
\documentclass{report}
\usepackage{gdutreport}
\begin{document}
	%先完善基本信息，由于没有做检查所以不填会报错
	%\GDUTstuinfo{学生姓名}{学号}{学院}{专业班级}
    \GDUTstuinfo{一轮}{311500xxxx}{自动化}{物联网工程3班}
    %\GDUTtheses{论文题目}
    \GDUTtheses{数据结构实验报告}
    %\GDUTfirstpage{指导老师}{学年}{\today}
    \GDUTfirstpage{钟灵最帅}{2016-2017}{2016-12-31}
    %此处可以按照需要添加摘要页
    \begin{abstract}
        hello,this is abstract!
    \end{abstract}
    %生成目录
    \GDUTcontents
    
    %下面可以开始正文
    \chapter{链表}
    blablabal吧啦吧啦...
    \section{什么是链表}
    \section{单项链表实现}
    \chapter{排序}
    \section{冒泡排序}
        \begin{lstlisting}[language=C, title=冒泡排序]
int main(void)
{
  printf("hello world!");
  return 0;
}
        \end{lstlisting}
\end{document}
```

## Notice

-   Default Compiler: XeLaTex

    Options->Configure->Build里设置

-   Encoding: UTF-8

      Options->Configure->Editor->Default Font Encoding

-   document class: report

      \documentclass{report} 如果不是report可能会报错



## use GDUTreport to do discrete math homework 

```latex
\documentclass{report}
\usepackage{gdutreport}

\newcommand\question[1]{\addcontentsline{toc}{section}{#1} \section*{#1}}
\newcommand\Chapter[1]{\addcontentsline{toc}{chapter}{#1} \chapter*{#1}}

%由于\quesiton 和 \chapter 导致的页眉显示章节bug暂时没修复所以将就改一下页眉吧
\fancyhead[ER,OR]{\thesesname}
\fancyhead[EL,OL]{作者：\name}
\begin{document}
	\GDUTstuinfo{一轮}{311500xxxx}{自动化}{物联网工程3班}
	\GDUTtheses{离散数学作业}
    \GDUTfirstpage{张钢手把手教你学Tex}{2016-2017}{\today}
    \GDUTcontents
    %某一章用\chapter
    \Chapter{第四章 \quad 二元关系和函数}
    \每个小问题用\question
    \question{4.13}
    \question{4.14}
    \Chapter{第5，6章 \quad 图论 }
    \question{5.2}
    由于$d(v)=d^+(v) + d^-(v)$，所以$d^+(v) = d(v) - d^-(v)$。已知$D$的度数列为$2,2,3,3$，入度列为$0,0,2,3$ ，故$D$的出度列为2,2,1,0 。
```



# Contact

mail: daielun@outlook.com
