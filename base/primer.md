# Vim入门

## 什么是Vim?
Vim 是一个自由、开源的文本编辑器；Vim 发布于1991年是基于类Unix的系统平台，是在Vi(发布于1976年)的基础上加以改良的版本。

* **NOTE:** Vim的意思是“Vi Improved”，Vim中大多数的编辑命令是来源于Vi的。

* 在一些Unix或类Linux系统（苹果Macintosh系统也是基于Unix）中，你会发现Vim是默认安装的。

* 传统的Vim并不像你过去用户的文本或代码编辑器(Sublime Text, Visual Studio Code, Eclipse, DreamWeaver等 )一样有GUI(图像用户界面)，然而另外一个安装版本Gvim提供了GUI。

* Vim的标准安装是在控制台或终端环境中进行，而不是采用安装程序。因为终端(terminal)是为超级用户而设计的，如滥用会损害系统。

## 为什么选择Vim?

### IDEs(Integrated Development Environments)

* 首先用到较多的是sublimetext(www.sublimetext.com)，之后是Atom(https://atom.io) ；这些IDE较Vim是重量级的代码编辑器，我们需要花大量的时间来记忆这些现代编辑器的按键绑定及特性。当我们要使用下个强大的编辑器时，之前所记忆的知识也随之而失效，这并不像Vim一样自从Vi创立就固定了下来。

* IDEs 相对Vim比较的重量级，Vim的轻便也是它受欢迎的原因，即便在一些旧版的操作系统中也是默认安装，运用自如，能快速启动，不必去考虑安装其他编辑器。

* 如用IDEs你是无法改变其特性的，而Vim的高度可定制性可让你随心所欲，打造成专属你个人的Vim版的IDE。

### Emacs？
我们在讨论Vim的同时，你肯定听过了Emacs，它在编辑器中与Vim旗鼓相当。

* Emacs像Vim一样也有图形界面，也能在终端中运行，也可高度可定制，甚至能成为系统级的组件，因Emacs是用elisp的脚语言写的，可定制它的每一个细节。

* Vim是用C语言写的，Vim的插件是用Vimscript写，通过接口来增强其功能，因插件是通过接口来使用，因而对Vim的改变是有限制的；但Vim默认安装在Unix及类Unix系统中，是常用编辑器，其轻便，高度可定制让其成为编辑器之神。

* Emacser们通常有自己的Emacs生活方式，他们可使用Emacs的内建的终端、文件系统，甚至可以发邮件、上网等。
