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

## 前言

一些 Next on Hexo 的初步设置，包括 Github banner :octocat:和 Emoji :smile:

## Next 设置

首先安装 [next-theme](https://theme-next.org/)

```bash
npm i hexo-theme-next
```

在\_config.yml 中：

```yaml
theme: next
```

将 Next 主题的设置需要在根目录上面新建一个\_config.[主题名].yml 的文件，该文件会覆盖默认的文件。使用

```bash
# Installed through npm
cp node_modules/hexo-theme-next/_config.yml _config.next.yml
# Installed through Git
cp theme/next/_config.yml _config.next.yml
```

将默认的 theme 拷贝过来：参见: https://theme-next.js.org/docs/getting-started/configuration

## 我的一些设置

- 打开 github banner(in `_config.next.yml`)

```yaml
github_banner:
  enable: true
  permalink: https://github.com/mikelxk
  title: Follow me on GitHub
```

- 将 minify 设置为 true

```yaml
minify: true
```

- 添加目录索引和图标

in `_config.next.yml`:

```yaml
menu:
  home: / || fa fa-home
  about: /about/ || fa fa-user
  tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive
```

然后在`source`下建立`/tags`和`/categories`, 其他的目录是自带的(`/about`自己写的)

在每个目录下面建立`index.md`, 例如`/tags`下就是:

```
---
title: tags
date: 2021-01-12 02:10:50
type: "tags"
---
```
参见：https://theme-next.js.org/docs/theme-settings/
- 使得 hexo server 自动打开网页(in `package.json`)

```json
"run": "hexo server -o"
```

添加-o 至命令行来直接打开 url

## 我的插件

- 使用[pretty quick](https://prettier.io/docs/en/precommit.html)添加 pre-commit hook

```bash
npm i pretty-quick husky
```

在 `package.json`中添加

```json
{
  "husky": {
    "hooks": {
      "pre-commit": "pretty-quick --staged"
    }
  }
}
```

- 使用 hexo-filter-github-emojis 来添加 emoji

```bash
npm i hexo-filter-github-emojis
```

在`_config.yml`中：

```yaml
emoji:
  enable: true
  className: github-emoji
  styles:
  customEmojis:
```

参见: https://www.npmjs.com/package/hexo-filter-github-emojis

第一篇水完了 逃） :running:
