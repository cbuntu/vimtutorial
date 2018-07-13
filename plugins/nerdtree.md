# nerdtree

## 简介
NerdTree 是一个 Vim 编辑器文件系统管理器，用户可以直观的浏览复杂的、多层的目录，能够快速打开文件进行查看、编辑及完成文件系统的基础操作。

这个插件还可以通过特定接口来定制映射增加功能，接口细节和NerdTree的其他特性都包含在了内置的文档中，可通过 :h NERDTree 来查看。

## NerdTree配置
> 在 vimrc 中配置 NerdTree

```
**[terminal]

" 插件管理列表中加入 nerdtree
Plugin 'scrooloose/nerdtree'

" NERDTree {

	" open NERDTree automatically when vim starts up
		"autocmd vimenter * NERDTree

	" NERDTree Window Position
		"let NERDTreeWinPos=0

	" open NERDTree automatically when vim starts up if no files were specified
		autocmd stdinreadpre * let s:std_in=1
		autocmd vimenter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
	" open NERDTree automatically when vim starts up on opening directory
		autocmd vimenter * if argc() == 1 && isdirectory(argv()[0]) && !exists("s:std_in") | exe 'NERDTree' argv()[0] | wincmd p | ene | endif

	" close vim when the only window left open is a NERDTree
		autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

	" use F3 to open and close NERDTree
		map <F3> :NERDTreeToggle<CR>

	" default arrow symbols
		let g:NERDTreeDirArrowExpandable = '▸'
		let g:NERDTreeDirArrowCollapsible = '▾'
		"let g:NERDTreeDirArrowExpandable = '+'
		"let g:NERDTreeDirArrowCollapsible = '~'

	" NERDTree file highlighting
		function! NERDTreeHighlightFile(extension, fg, bg, guifg, guibg)
			exec 'autocmd filetype nerdtree highlight ' . a:extension .' ctermbg='. a:bg .' ctermfg='. a:fg .' guibg='. a:guibg .' guifg='. a:guifg
			exec 'autocmd filetype nerdtree syn match ' . a:extension .' #^\s\+.*'. a:extension .'$#'
		endfunction

		call NERDTreeHighlightFile('css', 'blue', 'none', 'blue', '#151515')
		call NERDTreeHighlightFile('php', 'red', 'none', 'red', '#151515')
		call NERDTreeHighlightFile('html', 'blue', 'none', 'blue', '#151515')
		call NERDTreeHighlightFile('js', 'blue', 'none', 'blue', '#151515')
		call NERDTreeHighlightFile('json', 'magenta', 'none', 'magenta', '#151515')
		call NERDTreeHighlightFile('cpp', 'green', 'none', 'green', '#151515')

" }
```

## NerdTree 操作

> 切换工作台和目录

命令                |说明
:-------------------|:----------------------------------------------------
ctrl + w + h        |光标定位左侧树形目录
ctrl + w + l        |光标定位右侧文件显示窗口
ctrl + w + w        |光标自动在左右侧窗口切换
ctrl + w + r        |移动当前窗口的布局位置
o                   |在已有窗口中打开文件、目录或书签，并跳到该窗口
go                  |在已有窗口中打开文件、目录或书签，但不跳到该窗口
t                   |在新 Tab 中打开选中的文件、书签，并跳到该 Tab
T                   |在新 Tab 中打开选中的文件、书签，但不跳到该 Tab
i                   |split 一个新窗口打开选中的文件，并跳到该窗口
gi                  |split 一个新窗口打开选中的文件，但不跳到该窗口
s                   |vsplit 一个新窗口打开选中文件，并跳到该窗口
gs                  |vsplit 一个新窗口打开选中文件，但不跳到该窗口
!                   |执行当前文件
o                   |打开或合拢选中结点
O                   |递归打开选中结点下的所有目录
x                   |合拢选中结点的父目录
X                   |递归合拢选中结点下的所有目录
D                   |删除当前书签
P(大写)             |转到根结点
p                   |转到父结点
K(大写)             |转到当前目录下同级的第一个结点
J(大写)             |转到当前目录下同级的最后一个结点
k                   |转到当前目录下同级的前一个结点
j                   |转到当前目录下同级的后一个结点
C(大写)             |将选中目录或选中文件的父目录设为根结点
u                   |将当前根结点的父目录设为根目录，并变成合拢原根结点
U(大写)             |将当前根结点的父目录设为根目录，但保持展开原根结点
r                   |递归刷新选中目录
R                   |递归刷新根结点
m                   |显示文件系统菜单
cd                  |将 CWD 设为选中目录
I(大写)             |切换是否显示隐藏文件
f                   |切换是否使用文件过滤器
F                   |切换是否显示文件
B                   |切换是否显示书签
q(小写)             |关闭 NerdTree 窗口
?                   |切换是否显示 Quick Help

> 切换标签页

命令                |说明
:-------------------|:----------------------------------------------------
:tabnew [filename]  |建立对指定文件的新 Tab
:tabc               |关闭当前的 Tab
:tabo               |关闭所有其他的 Tab
:tabs               |查看所有打开的 Tab
:tabp               |切换至前一个 Tab
:tabn               |切换至后一个 Tab
gT                  |切换至前一个 Tab
gt                  |切换至后一个 Tab


![NerdTree插件界面](http://vimtutorial-1254400168.cossh.myqcloud.com/vim-nerdtree.png)
