> wsvn

这个插件提供类似nodepad++ subversion功能可以实现快速提交、更新等操作

> Install

有一下几种安装方式

1. 使用Vundle
    添加`Bundle 'kisshc/wsvn'`并执行命令`BundleInstall`,Vundle包管理将处理好一切事情

2. 手动安装
    下载解压复制plugin文件夹中的wsvn.vim到vim74/plugin中

> Note

wsvn目前只支持window下使用

> USEING

增加以下配置到你的vimrc文件中

```
let g:wsvn\_gui\_path = "C:/\"Program Files\"/TortoiseSVN/bin/TortoiseProc.exe"
let g:wsvn\_msg\_type = 2

map uoo :call UpdateObjectDir()<CR> "更新项目目录
map coo :call CommitObjectDir()<CR> "提交项目目录
map udd :call UpdateCurDirAll()<CR> "更新当前文件所在目录
map cdd :call CommitCurDirAll()<CR> "提交当前所在文件目录
map uaa :call UpdateCurOneFile()<CR>"更新当前编辑文件
map caa :call CommitCurOneFile()<CR>"提交当前编辑文件

```

注意这里的`wsvn\_gui\_path`路径中尽量不要使用空格,如果使用了空格则需要使用`""`进行包裹并且对`""`进行转义(如上),路径中使用`/`为分隔符,另外快捷键可以自定义

`wsvn\_msg\_type`可能的值为以下几种

1. `0`不自动关闭svn gui窗口
2. `1`遇到错误不关闭窗口
3. `2`遇到错误或冲突文件不关闭窗口(推荐)
4. `3`遇到错误或冲突或有文件合并不关闭窗口


