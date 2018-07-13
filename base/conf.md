# Vim配置

Vim安装好就像notepad一样的简单，还需进行配置，才能达到作为代码编辑器的要求，下面先来看下Vim的配置文件。

## Vimrc

### 配置文件说明 
Vim共有3个配置文件，分别是系统级、用户级、第2层用户级。

vimrc类别    |vimrc文件名
:-----------:|:---------------:
系统级       |$VIM/vimrc
用户级       |$HOME/.vimrc
第2层用户级  |~/.vim/vimrc

vimrc文件类别可用以下命令查看：
```
**[terminal]
**[path ~]**[delimiter $ ]**[command vim --version]
VIM - Vi IMproved 7.4 (2013 Aug 10, compiled Nov 24 2016 16:44:48)
Included patches: 1-1689
Extra patches: 8.0.0056
Modified by pkg-vim-maintainers@lists.alioth.debian.org
Compiled by pkg-vim-maintainers@lists.alioth.debian.org
Huge version without GUI.  Features included (+) or not (-):
	+acl             +farsi           +mouse_netterm   +tag_binary
	+arabic          +file_in_path    +mouse_sgr       +tag_old_static

此处省略一万行……

+extra_search    -mouse_jsbterm   +syntax
	   system vimrc file: "$VIM/vimrc"
	      user vimrc file: "$HOME/.vimrc"
	  2nd user vimrc file: "~/.vim/vimrc"
	       user exrc file: "$HOME/.exrc"
	   fall-back for $VIM: "/usr/share/vim"

-- More --
```

### 用户级配置文件
1. 建立用户级配置文件：~/.vimrc
2. 用文本编辑器打开~/.vimrc
3. 配置文件中用英文的单双引号表示注释"
4. 配置参数及注释如下：

```
**[terminal]
" {
	set nocompatible

		" 这条命令让Vim不兼容Vi，操作完全Vim化；
		" 也可简化命令为：set nocp；
		" 打开兼容命令为：set cp;
" }


" {
	set nobackup
	set nowritebackup
	set noswapfile

		" 这3条命令让Vim不产生无关的备份文件等；
" }


" {
	set ruler
		
		" 设置行号显示，对长文件非常有作用；
"}


" {
	set ignorecase
	set smartcase
	set hlsearch
	set incsearch
		
		" 1. 搜索模式里忽略大小写；
		" 2. 智能忽略大小写；
		" 3. 高亮显示搜索内容；
		" 4. 边输入搜索边显示结果；
"}


" {
	set autoread
		
		" 当文件在Vim之外修改后，Vim会自动更新读取；
"}


" {
	set autowrite
		
		" 当文件修改时，自动将内容写回文件；
"}


" {
	set autoindent
	set smartindent
	set tabstop=4
	set softtabstop=4
	set shiftwidth=4
	set cindent
	set wrap
	set linebreak
	set smarttab
		
		" 1. 设置缩进自动对齐，即缩进值与上一行一致；
		" 2. 设置自动缩进方式；
		" 3. 设置自表符(tab键)的宽度为4；
		" 4. 设置软自表符(tab键)的宽度为4；
		" 5. 自动缩进使用4个空格宽度；
		" 6. 使用C/C++语言的自动缩进方式；
		" 7. 设置软折行；
		" 8. 设置整词换行；
		" 9. 设置自动自表符缩进；
"}


" {
	set showmatch 
	set showcmd
	set showmode
	set history=1000
		
		" 1. 设置匹配模式，显示匹配的括号；
		" 2. 命令行显示正在输入的命令；
		" 3. 命令行显示当前Vim模式；
		" 4. 设置历史记录1000条；
"}


" {
	syntax enable
	syntax on

		" 设置语法高亮；
"}


" {
	filetype indent on
	filetype plugin on
	filetype plugin indent on
		
		" 文件类型/缩进打开；
"}


" {
	set encoding=utf-8
	set fileencodings=ucs-bom,utf-8,cp936,gb18030,big5,euc-jp,euc-kr,latin1
		
		" 设置Vim编码；
"}


" {
	cmap W w !sudo tee % >/dev/null<CR>
		
		" 大写W临时启用sudo权限保存无权限文件；
"}


" {
	nmap <F2> :source $MYVIMRC<CR>
		
		" F2 更新配置文件；
"}

```
