## TmdTextEpub

> 把txt文本转成epub电子书的命令行工具

### 功能
- 自动识别书名和章节
- 自定义章节匹配
- 自动给章节正文生成加粗居中的标题
- 段落自动识别
- 段落自动缩进

### 使用方法
```$xslt
Usage of E:\Code\Go\bin\TmdTextEpub.exe:
  -author string
        作者 (default "YSTYLE")
  -bookname string
        书名: 默认为txt文件名
  -filename string
        txt 文件名
  -match string
        匹配标题的正则表达式, 例: -match 第.{1,8}章 表示第和章字之间可以有1-8个任意文字 (default "第.{1,8}章")
```

### 示例
1. [点击下载](https://github.com/ystyle/TmdTextEpub/releases)
1. 把小说和`TmdTextEpub.exe`放到`D`盘
1. 按以下其中一种方法打开命令行
    - 按`win + r` 输入 `cmd` 然后输入以下命令
    - 按`win + x + i` 输入以下命令

使用示例:
```shell
cd d:/
d:/TmdTextEpub.exe -author 乱 -filename d:/全职法师.txt
```

自定义章节匹配, 章节为`Section 1` ~ `Section 100` 这种: 
```shell
cd d:/
d:/TmdTextEpub.exe -filename d:/ebbok.txt -match "Section \d+"
```

自定义章节匹配, 章节为`第x节` ~ `Section 100` 这种: 
```shell
cd d:/
d:/TmdTextEpub.ex e-filename d:/ebbok.txt -match "第.{1,8}节"
```

### 手工构建
```$xslt
go build -ldflags "-s -w" -o TmdTextEpub.exe main.go
```