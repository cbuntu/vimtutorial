# Vim起步

## Vim 四种模式

* 普通模式（Normal Mode）

 > 1. Vim 启动后进入的模式(与其他编辑器相反，其他编辑器进入的是插入模式)，此模式下你可以按相应Vim命令执行：光标移动、删除、复制等操作。
 > 2. 普通模式下有大量的命令来对文档进行编辑，后续会讲解。
 > 3. 在普通模式下可按i、I、a、A等进入插入模式。


* 插入模式（Insert Mode）

 > 1. 插入模式中，键盘按键将所按文本向缓冲区插入。
 > 2. 在插入模式中，按 ESC 将返回普通模式。


* 命令模式（Command Mode）

 > 1. 在命令模式中，可输入会被解释并执行的文本，如：执行命令(:命令)，搜索(/或?)、 
 > 2. 命令执行完后，Vim返回之前模式，通常是普通模式。


* 可视模式（Visual Mode）

 > 1. 视模式与普通模式较为相似，移动命令会扩大高亮的文本区域，高亮区域可以是文本、行或文本块。当执行一个非移动的命令时，命令会作用在高亮区域上。
 > 2. 普通模式中，v 命令可进入文本可视模式，Ctrl + v 进入文本块可视模式，Shift + v 进入行可视模式；按 ESC 返回普通模式，或作用高亮区域上的命令执行完返回普通模式。


## 打开 Vim

### 用vim命令进入vim界面

 > 直接用vim命令打开vim编辑器，但不会打开任何文件。

```
**[terminal]
~$ vim
```
按 ENTER 后打开如下图的Vim界面

```
**[terminal]
-
~
~
~
~                                             VIM - Vi IMproved
~                                              version 7.4.1689
~                                          by Bram Moolenaar et al.
~                          Modified by pkg-vim-maintainers@lists.alioth.debian.org
~                                Vim is open source and freely distributable
~
~                                       Become a registered Vim user!
~                               type  :help register<Enter>   for information
~
~                               type  :q<Enter>               to exit
~                               type  :help<Enter>  or  <F1>  for on-line help
~                               type  :help version7<Enter>   for version info
~
~
~
~
~                                                                                     0, 0-1            All
```

 > vim命令后跟要新建的文件名，可在vim中打开新建文件

```
**[terminal]
~$ vim code/hello.c
```
按 ENTER 后新建hello.c文件 
```
**[terminal]
-
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
"code/hello.c" [New File]                                                             0, 0-1            All
```

 > vim命令后跟要打开的已存在的文件名，可在vim中打开这个文件

```
**[terminal]
~$ vim code/hello.c
```
按 ENTER 后打开已存在的hello.c文件 
```
**[terminal]
1 #include <stdio.h>
2 int main() {
3 	printf("Hello World!\n");
4	return 0;
5 }
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
"code/hello.c"                                                                        0, 0-1            All
```

 > 进入 Vim 后，可通过命令打开文件或新建文件

```
**[terminal]
~$ vim
```
按 ENTER 后打开 Vim 编辑器，再用 :e 命令打开或新建文件
```
**[terminal]
-
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
:e $MYVIMRC                                                                           0, 0-1            All
```

### 光标移动
进入Vim后，我们可按 i 键进入插入模式，再用方向键或h，j，k，l键移动光标。

按键  |说明
:----:|:-----------------:
h     |左
j     |下
k     |上
l     |右
w     |移动到下一个单词
b     |移动到上一个单词


## 进入插入模式
在普通模式下使用下面的键，可进入插入模式，并可在相应的位置开始输入。

按键  |说明
:----:|:------------------------:
i     |在当前光标处插入
I     |在行首插入
a     |在当前光标后插入
A     |在行尾插入
o     |在当前行后插入一新行
O     |在当前行前插入一新行
cw    |替换从光标所在位置到一个单词结尾的字符


## 保存文档
 * 仅保存文档

```
**[terminal]
:w                                                                                    5, 2-8          6 
```


## 退出Vim

### 命令模式下退出Vim

```
**[terminal]
强制退出，不保存
:q!                                                                                   5, 2-8          6 

退出
:q                                                                                    5, 2-8          6 

强制保存，并退出
:wq!                                                                                  5, 2-8          6 

保存并退出
:wq                                                                                   5, 2-8          6 

另存为
:w <新文件名>                                                                          5, 2-8          6 

保存并退出
:x                                                                                    5, 2-8          6 
```

### 普通模式下退出Vim
> shift + zz，可保存退出Vim


## 删除文本

### 普通模式下删除Vim文本
进入普通模式，使用下列命令快速删除文本

命令   |说明
:-----:|:----------------------------:
x      |删除光标所在处的字符
X      |删除光标所在处前的一个字符
Delete |同 x
dd     |删除当前行
dw     |删除一个单词（不适合中文）
d$或D  |从光标处删除至行尾
d^     |从光标处删除至行首
dG     |从光标处删除至文档结尾
d1G    |从光标处删除至文档头部

此外，还可在命令前加 数字 ，表示一次删除几倍命令的量。如：2dd，一次删除2行。


