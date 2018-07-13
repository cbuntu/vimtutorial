# Vim插件

> 1. Vim 是一开源、自由的软件，其本身原代码公开，全世界的开发者可为其开发插件，从而实现某方面的应用，增强Vim功能；插件省去了我们手动配置的时间，可轻松实现Vim IDE的需求。
> 2. 我们介绍的第1个插件是：Vundle，Vundle 是帮助 Vim 安装和管理插件的插件。


## Vundle git仓库

### 下载
> Vundle 是开源软件，您可以去其 git 仓库下载

```
**[terminal]
~$ wgetu https://github.com/VundleVim/Vundle.vim/archive/master.zip
```
或通过浏览器下载：https://github.com/VundleVim/Vundle.vim/archive/master.zip

### 安装
> 新建 ~/.vim/bundle 安装目录

```
**[terminal]
~$ mkdir -p ~/.vim/bundle
```

> 解压缩下载的vundle.zip文件，将其移至 ~/.vim/bundle 文件夹中

```
**[terminal]
~$ mv vundle ~/.vim/bundle
```

## 配置 vundle
> 打开 配置文件 写出下面代码

```
**[terminal]
用命令打开配置文件
~
~
:e $MYVIMRC
```

> 在配置文件中配置 vundle

```
**[terminal]
用命令打开配置文件
" Configure Vundle {

	" 启用 Vim 模式，即不兼容 Vi 模式
		set nocompatible
	" 关闭filetype
		filetype off

	" 设置 Vim 运行时目录包含 vundle
		set rtp+=~/.vim/bundle/vundle

	" 定义 vundle 所管理的插件安装目录
		call vundle#begin('~/.vim/bundle/plugins')

	" 让 vundle 自行管理
		Plugin 'vundlevim/vundle.vim'


	" 插件管理列表
	" Configure Plugins {
	
		Plugin 'scrooloose/nerdtree'
		Plugin 'scrooloose/nerdcommenter'
		Plugin 'jiangmiao/auto-pairs'
		"Plugin 'Lokaltog/vim-powerline'
		Plugin 'vim-airline/vim-airline'
		Plugin 'vim-airline/vim-airline-themes'
		Plugin 'kien/ctrlp.vim'
		"Plugin 'Valloric/YouCompleteMe'
		"Plugin 'tpope/vim-surround'
		Plugin 'mattn/emmet-vim'
		Plugin 'Shougo/neocomplcache.vim'
		Plugin 'pangloss/vim-javascript'
		Plugin 'flazz/vim-colorschemes'
		Plugin 'yianwillis/vimcdoc'
		Plugin 'python-mode/python-mode'
		Plugin 'vim-syntastic/syntastic'

	" }

	call vundle#end()			" required
	filetype plugin indent on	" required
	
" }
~
~
"~/.vimrc"
```

## vundle 帮助

```
**[terminal]
~
~
:h vundle
```

## Vundle 命令

命令                    |说明
:----------------------:|:-----------------------------------:
:PluginInstall          |安装插件管理列表中的插件及更新 Vundle
:PluginList			    |列举插件管理列表中的所有插件
:PluginInstall!         |更新插件管理列表中的插件及更新 Vundle
:PluginSearch emmet-vim |查找 emmet-vim 插件
:PluginSearch! emmet-vim|刷新 emmet-vim 插件缓存
:PluginClean            |清除插件管理列表中没有用的插件
:PluginClean!           |强制清除插件管理列表中没有用的插件

> Vundle Installer

```
**[terminal]
" Installing plugins to ~/.vim/bundle/plugins   |
  Plugin 'scrooloose/nerdtree'                  |
  Plugin 'scrooloose/nerdcommenter'             |
  Plugin 'jiangmiao/auto-pairs'                 |
  Plugin 'vim-airline/vim-airline'              |
  Plugin 'vim-airline/vim-airline-themes'       |
  Plugin 'kien/ctrlp.vim'                       |
  Plugin 'mattn/emmet-vim'                      |
  Plugin 'Shougo/neocomplcache.vim'             |
  Plugin 'pangloss/vim-javascript'              |
> Plugin 'flazz/vim-colorschemes'               |
  Plugin 'yianwillis/vimcdoc'                   |
  Plugin 'python-mode/python-mode'              |
  Plugin 'vim-syntastic/syntastic'              |
~                                               |
~                                               |
~                                               |
~                                               |
~                                               |
[Vundle] Installer
Processing 'vim-colorschemes'
```

> Vundle Installer实例动画

![Vundle Installer](http://vimtutorial-1254400168.cossh.myqcloud.com/vim-vundle.gif)

