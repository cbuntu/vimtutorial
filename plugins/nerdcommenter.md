# nerdcommenter

## 简介
nerdcommenter 是一个快速注释插件，些插件可快速对选中行、区域进行注释，也可进行智能判断。

## NERDCommenter 帮助
> 命令打开 NERDCommenter 的帮助

```
**[terminal]
~
~
:h NERDCommenter
```

```
**[terminal]

*NERD_commenter.txt*         Plugin for commenting code


                        NERD COMMENTER REFERENCE MANUAL~

==============================================================================
CONTENTS                                               *NERDCommenterContents*

    1.Intro...................................|NERDCommenter|
    2.Installation............................|NERDComInstallation|
    3.Functionality provided..................|NERDComFunctionality|
        3.1 Functionality Summary.............|NERDComFunctionalitySummary|
        3.2 Functionality Details.............|NERDComFunctionalityDetails|
            3.2.1 Comment map.................|NERDComComment|
            3.2.2 Nested comment map..........|NERDComNestedComment|
            3.2.3 Toggle comment map..........|NERDComToggleComment|
            3.2.4 Minimal comment map.........|NERDComMinimalComment|
            3.2.5 Invert comment map..........|NERDComInvertComment|
            3.2.6 Sexy comment map............|NERDComSexyComment|
            3.2.7 Yank comment map............|NERDComYankComment|
            3.2.8 Comment to EOL map..........|NERDComEOLComment|
            3.2.9 Append com to line map......|NERDComAppendComment|
            3.2.10 Insert comment map.........|NERDComInsertComment|
            3.2.11 Use alternate delims map...|NERDComAltDelim|
            3.2.12 Comment aligned maps.......|NERDComAlignedComment|
            3.2.13 Uncomment line map.........|NERDComUncommentLine|
        3.3 Sexy Comments.....................|NERDComSexyComments|
        3.4 The NERDComment function..........|NERDComNERDComment|
        3.5 The Hooks.........................|NERDComHooks|
    4.Options.................................|NERDComOptions|
        4.1 Options summary...................|NERDComOptionsSummary|
        4.2 Options details...................|NERDComOptionsDetails|
        4.3 Default delimiter Options.........|NERDComDefaultDelims|
    5. Customising key mappings...............|NERDComMappings|
    6. Issues with the script.................|NERDComIssues|
        6.1 Delimiter detection heuristics....|NERDComHeuristics|
        6.2 Nesting issues....................|NERDComNesting|
    7.About..     ............................|NERDComAbout|
    8.Changelog...............................|NERDComChangelog|
    9.Credits.................................|NERDComCredits|
    10.License................................|NERDComLicense|
```

## nerdcommenter 配置
> 在 vimrc 配置文件中设置

```
**[terminal]
" 将 nerdcommenter 加入插件管理列表
Plugin 'scrooloose/nerdcommenter'

" 设置映射符为 ,
let mapleader=','

" 设置注释符与内容间空格数
let g:NERDSpaceDelims="1"
```

## nerdcommenter 使用

> 1. ,cc 注释当前行和选中行；
> 2. ,cn 未发现与 ,cc 的不同；
> 3. ,c<空格> 如果被选区域有部分被注释，则对被选区域执行取消注释操作，其它情况执行反转注释操作
> 4. ,cm 对被选区域用一对注释符进行注释，前面的注释对每一行都会添加注释
> 5. ,ci 执行反转注释操作，选中区域注释部分取消注释，非注释部分添加注释
> 6. ,cs 添加性感的注释，代码开头介绍部分通常使用该注释
> 7. ,cy 添加注释，并复制被添加注释的部分
> 8. ,c$ 注释当前光标到改行结尾的内容
> 9. ,cA 跳转到该行结尾添加注释，并进入编辑模式
> 10. ,ca 转换注释的方式，比如： /**/和//
> 11. ,cl ,cb 左对齐和左右对其，左右对其主要针对/**/
> 12. ,cu 取消注释
