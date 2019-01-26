#开发者文档维护与Mark Down 工具链安装使用

 By：晋正宇

2019年1月24日



1. 安装Rust：

 [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)

```bash
$ curl https://sh.rustup.rs -sSf | sh
```

更新到新版本：

```bash
$ rustup update stable
$ rustup default stable
```

2. 安装MDBook：

[https://github.com/rust-lang-nursery/mdBook](https://github.com/rust-lang-nursery/mdBook)
```bash
$ cargo install mdbook --vers "0.2.1"
```
创建MDBook项目目录，初始化MDBook：

```bash
$ mkdir tryit

$ cd tryit

$ mdbook init
```
3. 安装VSCode Markdown插件：

    在VSCode插件中搜索，并安装：
```
Markdown All in One
```
在mdbook项目目录中启动vscode
```
tryit$ code .
```
编辑src中的SUMMARY.md 添加新的章节 .md

4. 安装 word-to-markdown

    [https://www.jianshu.com/p/b0be43b03015](https://www.jianshu.com/p/b0be43b03015)

安装LibreOffice

安装word-to-markdown
```
$ gem install word-to-markdown

$ w2m 1.docx \> 1.md
```
5. 开发者文档维护与发布

   通过w2m将既有doc文档转换为 md

   在项目中创建doc/developer目录，使用mdbook创建文档项目

   文档依据章节将文档拆分为多个md，放入{developer}/src/

   在{developer}/src/SUMMARY.md中，添加各章节目录

   将文档目录添加到项目目录中，置于git管理之下

   开发者文档，通过md格式维护

   在构建脚本中，添加mdbook构建过程：
```
$ mdbook build
```
   将mdbook构建结果，添加到开发者门户
