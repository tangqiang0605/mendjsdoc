## 历史记录

笔记组合：
Obsidian 是符合我预期的一款软件，正在替代 typora 作为我的主力笔记软件。
Obsidian 是本地化的，但是配合 github/gitee，可以很方便地实现云端储存。

我通过 docusaurus+github+netlify 的方式部署文档，编辑本地仓库并同步到 github 上，netlify 就会重新部署和更新网站上的内容。

本文档有两种编辑方式：使用 vscode，或者 obsidian。

Obsidian 可以直接打开文件作为工作区，其中的配置与其他工作区的配置是完全隔离开来的。Obsidian 界面美观，相比于 vscode，还可以实时预览 md 文件的渲染结果。工作区则让我更专注于文档的编写。同时，obsidian 可以方便地管理文档中使用到的图片。码代码使用 vscode，编辑文档使用 obsidian，是最佳实践。
然而在这种使用情景下，obsidian 具有以下缺点：
1. Obsidian 是实时保存的，所以可能会导致通过 npm run start 构建的项目预览因为错误而停止服务。或者让项目频繁刷新。
2. Obsidian 只能读取 md 文件和资源文件，既是优点也是缺点，但对我来说够用了。
3. 直接读取项目为仓库，会引入 node_modules 文件。解决方法是重新配置一个新的只存放 blog 和 docs 的文件夹，再通过 obsidian 打开。
然而，以上缺点可以完全忽视。在学习阶段我需要时常预览，所以开启服务器使用 obsidian 自动保存会经常报错，选用 vscode 进行修改文件效果测试。现在我不用开启服务器，直接在本地编辑，然后通过 vscode 的可视化 git 管理同步到 github 上，在网站上就可以查看到发布的结果了。

所以，后面的工作流中，vscode 写代码、测试项目、同步文章更新，obsidian 进行文章编辑，环境完好隔离。在 vscode 完成代码工作后，后期我打开 vscode 的原因就只是同步文章到网站上了（或许我可以不打开 vscode 而使用命令行工具）。

一开始我使用 obsidian 用于学习使用，需要时常观察页面渲染的情况，自动保存总是使程序出现错误，需要重启本地服务器服务。这是我切换为 vscode 编辑 md 文档的重要原因（保存的权力保留在自己手中）。而且为了不读取一大堆 node_modules 文件夹（除了 md 其他文件夹全是空的），我重新配置了 docusaurus 的路径配置。

现在，我直接通过 obsidian 打开项目进行文档编辑。并没有什么不好的地方。相比于 vscode，md 渲染预览和资源管理更方便。

说一下 obsidian。Obsidian 以后应该都会成为我编辑 md 文件的选择，原因是因为它足够美观，而且可以很方便地设置该工作区中项目图片资源的存放路径（右键文件夹，设置即可）。

Obsidian+github 实现云端保存。

Obsidian+github+netlify 实现公开博客创作。