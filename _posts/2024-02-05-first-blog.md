---
title: first blog
date: 2024-02-05 17:25:36
tags: Hexo
categories: 技术 
description: 简单的记录，用于后续博客的记录。
---

### 创建一篇博文
执行如下命令：
`$ hexo new 'blog_name' # blog_name自定义博客名`

hexo 会帮我们在`..\hexo\source\_posts`下生成相关md文件，之间使用编辑器进行编辑即可。

#### scaffolds
模版文件夹。新建文章时，Hexo 会根据 scaffold 来建立文件。默认的模板有三种 `draft.md` 、 `page.md` 和 `post.md`，我们自己也可以在该文件夹下创建属于自己定制的模板，推荐格式如下：

- title: GitHub + Hexo 从零开始搭建个人博客
- date: 1544357859000
- tags:
- categories：
- description：
然后，输入 `hexo new blog "文章名"` 进行测试。

#### public
该文件夹中的内容将被最终 `push` 到 GitHub 仓库中。

#### source
资源文件夹是存放用户资源的地方。除 `_posts` 文件夹之外，开头命名为 `_ (下划线)` 的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝到 public 文件夹。

### 主题配置
主题的配置也有很多高级技巧，这里附上 [Next 主题官方的配置文档教程](http://theme-next.iissnan.com/getting-started.html)。

还有许多个性化设置，如SEO、评论系统、个人头像、博客分享、订阅功能High功能、404网页设置等，可以参看：

- [主题配置 - NexT 使用文档](http://theme-next.iissnan.com/theme-settings.html)
- [第三方服务集成 - NexT 使用文档](http://theme-next.iissnan.com/third-party-services.html)
- [内置标签 - NexT 使用文](http://theme-next.iissnan.com/tag-plugins.html)
- [档进阶设定 - NexT 使用文档](http://theme-next.iissnan.com/advanced-settings.html)
- [High功能特效 - Next 主题网站推荐博主的文章](http://www.iamlj.com/2016/08/add-special-effect-harlem-shake-for-hexo/)


### 图床
图床，当博文中有图片时，若是少量图片，可以直接把图片存放在 `source` 文件夹中，但这显然不合理的，因为图片会占据大量的存储的空间，加载的时候相对缓慢 ，这时考虑把博文里的图片上传到某一网站，然后获得外部链接，使用 `Markdown` 语法，`![图片信息](外部链接)` 完成图片的插入，这种网站就被成为图床。

其实也可以直接在 GitHub 中新建一个仓库，专门用来存放博客的图片


### hexo 常用命令
1. hexo new “postName” # 新建文章
2. hexo clean # 清除缓存
3. hexo generate # 生成静态页面至 public 目录
4. hexo server # 开启预览访问端口（默认端口 4000，’ctrl + c’关闭 server）
5. hexo deploy # 部署到 GitHub
6. hexo help # 查看帮助
7. hexo version # 查看 Hexo 的版本
#### 缩写
1. hexo n == hexo new
2. hexo g == hexo generate
3. hexo s == hexo server
4. hexo d == hexo deploy
#### 组合命令
1. hexo s -g # 生成并本地预览
2. hexo d -g # 生成并上传


### 官方指令记录
#### new
```$ hexo new [layout] <title>```: 新建一篇文章。

如果没有设置` layout` 的话，默认使用` _config.yml` 中的 `default_layout` 参数代替。如果标题包含空格的话，请使用**引号**括起来。如`$ hexo new "post title with whitespace"`

#### generate
`$ hexo generate` ，简写为`$ hexo g `: 生成静态文件。

| 选项                  | 描述                                                         |
| :-------------------- | ------------------------------------------------------------ |
| `-d`, `--deploy`      | 文件生成后立即部署网站                                       |
| `-w`, `--watch`       | 监视文件变动                                                 |
| `-b`, `--bail`        | 生成过程中如果发生任何未处理的异常则抛出异常                 |
| `-f`, `--force`       | 强制重新生成文件 Hexo 引入了差分机制，如果 `public` 目录存在，那么 `hexo g` 只会重新生成改动的文件。 使用该参数的效果接近 `hexo clean && hexo generate` |
| `-c`, `--concurrency` | 最大同时生成文件的数量，默认无限制                           |

#### publish
`$ hexo publish [layout] <filename>` : 发表草稿。
<br>

#### server
`$ hexo server` :启动服务器。默认情况下，访问网址为：` http://localhost:4000/`。

| 选项             | 描述                           |
| :--------------- | :----------------------------- |
| `-p`, `--port`   | 重设端口                       |
| `-s`, `--static` | 只使用静态文件                 |
| `-l`, `--log`    | 启动日记记录，使用覆盖记录格式 |
<br>
#### deploy
`$ hexo deploy` ，简写为`$ hexo d`: 部署网站。

| 参数               | 描述                     |
| :----------------- | :----------------------- |
| `-g`, `--generate` | 部署之前预先生成静态文件 |
<br>
#### render
`$ hexo render <file1> [file2] ...` : 渲染文件。

| 参数             | 描述         |
| :--------------- | :----------- |
| `-o`, `--output` | 设置输出路径 |
<br>
#### clean
`$ hexo clean` : 清除缓存文件 (`db.json`) 和已生成的静态文件 (`public`)。
在某些情况（尤其是更换主题后），如果发现您对站点的更改无论如何也不生效，您可能需要运行该命令。



___
### 参考链接
[GitHub + Hexo 从零开始搭建个人博客](https://mumaxu.github.io/2018/12/09/GitHub-Hexo-%E4%BB%8E%E9%9B%B6%E5%BC%80%E5%A7%8B%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/)
[hexo官方文档](https://hexo.io/zh-cn/docs/commands)
