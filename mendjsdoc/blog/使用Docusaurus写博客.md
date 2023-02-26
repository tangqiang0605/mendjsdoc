---
# slug: welcome
title: 使用Docusaurus写博客
authors: tangqiang
tags: [docusaurus]
---

最佳实践是，配置显示所有博客。然后新建一个md就可以开始写。纯md中一个井号可以替换标题。新建作为url的文件名。然后一个井号标题，就可以开始正文了。
参考：https://www.docusaurus.cn/docs/blog
<!--truncate-->

## 首部

前端内容（front matter）用于将元数据添加到 Markdown 文件中。所有内容插件都有自己的前端模式，并使用前端模式来丰富从内容或其他配置推断出的默认元数据。前面的内容位于文件的最顶端，用三个破折号包围。内容被解析为 YAML。（在 yaml 中井号表示注释）

所有字段以及默认值：https://www.docusaurus.cn/docs/api/plugins/@docusaurus/plugin-content-blog#markdown-front-matter

title作为文章的标题，而md文件的名字将作为url上的路由（去除了data前缀）。如果存在slug字段，则使用该字段生成路由。

### 常用字段
一般来说，首部都可以不用。
title、
data（缺省）、tags、
keywords和description用于seo。
、img显示文章链接时将使用的封面或缩略图图像。
#### author
在blog目录下新建文件 authors.yml 并进行配置。
``` yaml
tangqiang:
  name: tangqiang
  title: description
  url: https://tqblogs.netlify.app/
  image_url: https://avatars.githubusercontent.com/u/94268117
```
引用示例：
``` yaml
authors: tangqiang
authors: [tangqiang]
authors: [zhangsam,lisi]

authors:
  name: Joel Marcey
  title: Co-creator of Docusaurus 1
  url: https://github.com/JoelMarcey
  image_url: https://github.com/JoelMarcey.png
authors:
  - name: Joel Marcey
    title: Co-creator of Docusaurus 1
    url: https://github.com/JoelMarcey
    image_url: https://github.com/JoelMarcey.png
  - name: Sébastien Lorber
    title: Docusaurus maintainer
    url: https://sebastienlorber.com
    image_url: https://github.com/slorber.png
```

#### data
可以以文件名YYYY-MM-DD-my-blog-post-title.md自动读取。
或者
``` yaml
---
date: 2021-09-13T18:00
---
```

## 正文

`<!--truncate-->`将前面所有内容作为摘要。

`##`设置井号（少于四个）标题显示在侧边栏中。

## 配置
配置侧边栏
``` json
module.exports = {
  presets: [
    [
      '@docusaurus/preset-classic',
      {
        blog: {
          blogSidebarTitle: 'All posts',
          blogSidebarCount: 'ALL',
        },
      },
    ],
  ],
};
```
配置读取路径
``` json
module.exports = {
  presets: [
    [
      '@docusaurus/preset-classic',
      {
        blog: {
          path: './mendjsdoc/blog',
        },
      },
    ],
  ],
};
```
根据字数生成阅读时间
``` yaml
module.exports = {
  presets: [
    [
      '@docusaurus/preset-classic',
      {
        blog: {
          showReadingTime: true, // When set to false, the "x min read" won't be shown
          readingTime: ({content, frontMatter, defaultReadingTime}) =>
            defaultReadingTime({content, options: {wordsPerMinute: 300}}),
        },
      },
    ],
  ],
};
```