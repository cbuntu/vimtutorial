# autopairs

## 简介
插入或删除成对的小括号、中括号、花括号、单引号、双引号及光标定位。

## 帮助

> :h AutoPairs

## 特性

>注：下方 | 均表示光标所在位置

* 成对插入 ()、[]、{}、''、""

```
**[terminal]
input: [
output: [|]
```

* 成对删除 ()、[]、{}、''、""

```
**[terminal]
input: foo(<BS>)
output: foo
```

* 回车后插入一行新的缩进行

```
**[terminal]
input: {|} (press <CR> at |)
output: {
	|
}
```

* 在关闭符号前插入空格，仅针对()、[]、{}有效

```
**[terminal]
input: {|} (press <SPACE> at |)
output: {  }

input: {|} (press <SPACE>foo at |)
output: { foo }

input: '|' (press <SPACE> at |)
output: ' |'
```

* 关闭符号 ()、[]、{}、''、""

```
**[terminal]
input: ""
output: ""

input: {}
output: {}
```

* 快速跳到配对符尾

```
**[terminal]
input:
{
	something;|
}

(press } at |)

output:
{
	something;
}|
```
