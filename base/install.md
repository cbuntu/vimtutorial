# Vim安装

## MacOS

虽说Vim默认是安装的，但默认安装的可能有些特性不能使用或版本过低，因而有必要也自己安装。

### [Homebrew](https://brew.sh/)

Homebrew是为MacOS提供的软件包管理器，我们先按下列命令安装Homebrew

```
**[terminal]
~$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Homebrew 安装 Vim

一旦Homebrew安装完成，就可用Homebrew来安装Vim了

```
**[terminal]
~$ brew install vim --override-system-vim
```

通过 vim --version来查看Vim的特性，+表示可用，-表示不可用

```
**[terminal]
~$ vim --version
VIM - Vi IMproved 8.0 (2016 Sep 12, compiled Nov 29 2017 18:37:46)
Included patches: 1-503, 505-680, 682-1283
Compiled by root@apple.com
Normal version without GUI.  Features included (+) or not (-):
+acl             +file_in_path    -mouse_sgr       +tag_old_static
-arabic          +find_in_path    -mouse_sysmouse  -tag_any_white
+autocmd         +float           -mouse_urxvt     -tcl
-balloon_eval    +folding         +mouse_xterm     -termguicolors
-browse          -footer          +multi_byte      -terminal
+builtin_terms   +fork()          +multi_lang      +terminfo
+byte_offset     -gettext         -mzscheme        +termresponse
+channel         -hangul_input    +netbeans_intg   +textobjects
+cindent         +iconv           +num64           +timers
-clientserver    +insert_expand   +packages        +title
-clipboard       +job             +path_extra      -toolbar
+cmdline_compl   +jumplist        -perl            +user_commands
+cmdline_hist    -keymap          +persistent_undo +vertsplit
+cmdline_info    +lambda          +postscript      +virtualedit
+comments        -langmap         +printer         +visual
-conceal         +libcall         -profile         +visualextra
+cryptv          +linebreak       +python/dyn      +viminfo
+cscope          +lispindent      -python3         +vreplace
+cursorbind      +listcmds        +quickfix        +wildignore
+cursorshape     +localmap        +reltime         +wildmenu
+dialog_con      -lua             -rightleft       +windows
+diff            +menu            +ruby/dyn        +writebackup
+digraphs        +mksession       +scrollbind      -X11
-dnd             +modify_fname    +signs           -xfontset
-ebcdic          +mouse           +smartindent     -xim
-emacs_tags      -mouseshape      +startuptime     -xpm
+eval            -mouse_dec       +statusline      -xsmp
+ex_extra        -mouse_gpm       -sun_workshop    -xterm_clipboard
+extra_search    -mouse_jsbterm   +syntax          -xterm_save
-farsi           -mouse_netterm   +tag_binary
   system vimrc file: "$VIM/vimrc"
     user vimrc file: "$HOME/.vimrc"
 2nd user vimrc file: "~/.vim/vimrc"
      user exrc file: "$HOME/.exrc"
       defaults file: "$VIMRUNTIME/defaults.vim"
  fall-back for $VIM: "/usr/share/vim"
Compilation: gcc -c -I. -Iproto -DHAVE_CONFIG_H  -DMACOS_X_UNIX -g -O2 -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=1
Linking: gcc   -L/usr/local/lib -o vim        -lm -lncurses  -liconv -framework Cocoa
~$
```

## Linux
以Ubuntu发行版为例，用下面命令来安装

```
**[terminal]
~$ sudo apt install vim
```
## Windows
Windows下的Vim安装，下载安装程序或下载runtimefiles和vim##win32.zip进行安装配置

## 说明
Vim在各平台的安装在相应平台的程序安装中会有详细讲解。

## Vim安装后界面
![Vim7.4](http://vimtutorial-1254400168.cossh.myqcloud.com/vim7.4.png)
