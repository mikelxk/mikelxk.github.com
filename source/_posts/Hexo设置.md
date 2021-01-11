---
title: Hexo设置
date: 2021-01-12 02:10:50
tags:
- 设置
- Hexo
- Next
categories:
- 设置
---
### Next设置
首先安装 [next-theme](https://theme-next.org/)
```bash
npm i hexo-theme-next
```
在_config.yml中：
```yaml
theme: next
```
将
Next主题的设置需要在根目录上面新建一个_config.[主题名].yml的文件，该文件会覆盖默认的文件。使用
``` bash
# Installed through npm
cp node_modules/hexo-theme-next/_config.yml _config.next.yml
# Installed through Git
cp theme/next/_config.yml _config.next.yml
```
将默认的theme拷贝过来：[参见](https://theme-next.js.org/docs/getting-started/configuration)
### 我的设置
- 将github banner打开
```yaml
github_banner:
  enable: true
  permalink: https://github.com/mikelxk
  title: Follow me on GitHub
```
- 将minify设置为true
```yaml
minify: true
```
- 使得hexo server自动打开网页(in package.json)
```json
"run": "hexo server -o"
```
添加-o 至命令行来直接打开url