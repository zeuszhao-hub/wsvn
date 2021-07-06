> wsvn

这个插件提供类似nodepad++ subversion功能,可以实现快速提交、更新等操作

![效果图](https://github.com/kisshc/wsvn/blob/master/wsvn.gif)

> Install

有一下几种安装方式

1. 使用Vundle
    添加`Bundle 'kisshc/wsvn'`并执行命令`BundleInstall`,Vundle包管理将处理好一切事情

2. 手动安装
    下载解压复制plugin文件夹中的wsvn.vim到vim74/plugin中

> USEING

增加以下配置到你的vimrc文件中

```
let g:wsvn_gui_path = "C:/\"Program Files\"/TortoiseSVN/bin/TortoiseProc.exe"
let g:wsvn_msg_type = 2

map foo :call UpdateObjectDir()<CR> "更新项目目录
map moo :call CommitObjectDir()<CR> "提交项目目录
map fdd :call UpdateCurDirAll()<CR> "更新当前文件所在目录
map mdd :call CommitCurDirAll()<CR> "提交当前所在文件目录
map faa :call UpdateCurOneFile()<CR>"更新当前编辑文件
map maa :call CommitCurOneFile()<CR>"提交当前编辑文件

```

注意这里的`wsvn_gui_path`路径中尽量不要使用空格,如果使用了空格则需要使用`""`进行包裹并且对`""`进行转义(如上),路径中使用`/`为分隔符,另外快捷键可以自定义

建议不要使用已存在的单键快捷键作为wsvn快捷键的开头，如:u回退上一步 这样会产生延时（vim会匹配按键，当输入u的的时候vim将等待输入下一个按键，直至监听结束以此造成延时）

`wsvn_msg_type`可能的值为以下几种

1. `0`不自动关闭svn gui窗口
2. `1`遇到错误不关闭窗口
3. `2`遇到错误或冲突文件不关闭窗口(推荐)
4. `3`遇到错误或冲突或有文件合并不关闭窗口

> Note

wsvn目前只支持window下使用

> v 0.0.2

1. 修复提交项目目录后，再次提交单个文件文件目录不正确的问题

