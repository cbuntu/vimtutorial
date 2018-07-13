# vimrc

以下是我的个人vimrc文件，供参考

```
**[terminal]

" Info {

	" Author your name
	" File ~/.vimrc
	" Plugin Manager Vundle
	
" }



" Configure Vundle {

	" be iMproved, required
		set nocompatible
	" turn off the filetype, required
		filetype off

	" set the runtime path to include vundle and initialize
		set rtp+=~/.vim/bundle/vundle

	" default vundle#begin
		"call vundle#begin()

	" define a path where vundle should install plugins
		call vundle#begin('~/.vim/bundle/plugins')

	" let vundle manage vundle, required
		Plugin 'vundlevim/vundle.vim'


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



" Configure Vim {

	" General {
	
		set history=1000
		set number
		"set relativenumber
		set numberwidth=1

		colorscheme wombat

		set nocp
		filetype indent on
		filetype plugin on
		filetype plugin indent on

		set autoread
		set shortmess=ati

		set nobackup
		set nowb
		set noswapfile

		set hlsearch
		set ignorecase
		set incsearch

		"set foldenable
		"set foldmethod=syntax

		set tabstop=4
		set shiftwidth=4
		set autoindent
		set cindent
		set smartindent
		set smarttab
		set wrap

		au FileType html,python,vim,javascript,java,php,qml setl shiftwidth=4
		au FileType html,python,vim,javascript,java,php,qml setl tabstop=4
		au FileType txt, setl shiftwidth=4
		au FileType txt, setl tabstop=4

		set ruler
		set showcmd
		set showmatch

		syntax enable
		syntax on

		set t_Co=256

		set encoding=utf-8
		set fileencodings=ucs-bom,utf-8,cp936,gb18030,big5,euc-jp,euc-kr,latin1

		cmap W w !sudo tee % >/dev/null<CR>

		nmap <F2> :source $MYVIMRC<CR>

	" }


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
	
	
	" NERDTCommnet {

		let mapleader=","
		let g:NERDSpaceDelims="1"

	" }


	" Vim-Airline {
	
		let g:airline#extensions#tabline#enabled = 1
		let g:airline_powerline_fonts = 1
		let g:airline_theme="wombat"

		if !exists('g:airline_symbols')
		  let g:airline_symbols = {}
		endif

		let g:airline_left_sep = '»'
		let g:airline_left_sep = '▶'
		let g:airline_right_sep = '«'
		let g:airline_right_sep = '◀'
		let g:airline_symbols.crypt = '🔒'
		let g:airline_symbols.linenr = '☰'
		let g:airline_symbols.linenr = '␊'
		let g:airline_symbols.linenr = '␤'
		let g:airline_symbols.linenr = '¶'
		let g:airline_symbols.maxlinenr = ''
		let g:airline_symbols.maxlinenr = '㏑'
		let g:airline_symbols.branch = '⎇'
		let g:airline_symbols.paste = 'ρ'
		let g:airline_symbols.paste = 'Þ'
		let g:airline_symbols.paste = '∥'
		let g:airline_symbols.spell = 'Ꞩ'
		let g:airline_symbols.notexists = '∄'
		let g:airline_symbols.whitespace = 'Ξ'

		"let g:airline_section_b = '%{strftime("%c")}'
		"let g:airline_section_y = 'BN: %{bufnr("%")}'

	" }
	

	" Vim-Neocomplcache {

		let g:neocomplcache_enable_at_startup = 1

	" }


	" Vim-Javascript {

		let g:javascript_plugin_jsdoc = 1
		let g:javascript_plugin_ngdoc = 1
		let g:javascript_plugin_flow = 1

	" }


	" Vimcdoc {
	
		set helplang=en

	" }


	" Python-Mode {
	
		let g:pymode = 1
		let g:pymode_python = 'python3'

	" }
	

	" Syntastic {
	
		set statusline+=%#warningmsg#
		set statusline+=%{SyntasticStatuslineFlag()}
		set statusline+=%*

		let g:syntastic_always_populate_loc_list = 1
		let g:syntastic_auto_loc_list = 1
		let g:syntastic_check_on_open = 1
		let g:syntastic_check_on_wq = 0		
	
	" }

" }
```
