# Docsify-lordyao

- [官方手册](https://docsify.js.org/#/zh-cn/)
- [docsify，一个神奇的文档网站生成器](https://cloud.tencent.com/developer/article/2376291?areaId=106001)
- [「docsify」学习笔记](https://cloud.tencent.com/developer/article/2288015?areaId=106001)
- [docsify的配置+全插件列表](https://cloud.tencent.com/developer/article/2177009)
  - index.html是最核心的一个文件，它里面加载了docsify的css、js，而且像网站的名字、ico、等基本的信息，还有插件的配置参数都是在这个文件当中。
  - docs文件夹里面装的都是md文件，网站会渲染这些用markdown语法写成的文章在前台展示出来。
  - 其他的md文件是与index.html衔接的有联系的一些文件，比如说侧边栏的目录、页脚文件等。
  - ```<meta charset="UTF-8">```应该就是声明一下字符编码
  - http-equiv不是很了解，说是http的请求头，我顺便在下面加了一行，是从handsome那里加过来的，据说是针对国内浏览器的优化
  - viewport应该是搞那个什么移动设备适配的，我还去查了哪个参数是对应锁定宽度，哪个参数是不允许放大缩小之类的
- [Docsify快速搭建个人博客](https://cloud.tencent.com/developer/article/1462429?from=article.detail.1669802)
  - Docsify 是一个动态生成文档网站的工具。不同于 GitBook、Hexo 的地方是它不会生成将 .md 转成 .html 文件，所有转换工作都是在运行时进行。这将非常实用，如果只是需要快速的搭建一个小型的文档网站，或者不想因为生成的一堆 .html 文件“污染” commit 记录，只需要创建一个 index.html 就可以开始写文档而且直接部署在 GitHub Pages。
  - docsify 中文文档：https://docsify.js.org/#/zh-cn/
  - 全局安装
    - npm i docsify-cli -g
  - 初始化文档
    - 注意这里的文件名约定为 docs 也是官方推荐，请按照规则设置，否则发到 Github 可能会出现一些问题
    - docsify init docs
      - index.html：入口文件
      - README.md：会做为主页内容渲染
      - .nojekyll：用于阻止 GitHub Pages 会忽略掉下划线开头的文件
  - 启动本地服务预览
    - docs 同级目录下执行以下命令，打开本地服务器，默认地址为：http://localhost:3000
    - docsify serve docs
  - 搭建博客
    - 设置封面
      - 设置我们的封面图，需要两步，首先在 docs/index.html 文件中将设置 coverpage:true，之后创建 docs/_coverpage.md文件docs/index.html
    - 定制导航栏
      - 官方支持两种方式，可以在 HTML 里设置，但是链接要以 #/ 开头，另外一种通过 Markdown 配置导航，我们这里用的也是后者
      - 首先配置 loadNavbar:true，之后创建 docs/_navbar.md文件.
- [基于nginx + docsify搭建文档中心](https://cloud.tencent.com/developer/article/2349183?areaId=106001)
  - homepage: 'README.md'设置了markdown文件。
  - search.min.js是提供搜索使用，可以去掉。docsify.min.js必须保留。vue.css美化样式。
  - prism-java.min.js是美化Java代码使用，可以去掉。
  - coverpage: true是否需要提供一个覆盖页，就是会先显示这个覆盖页，下划后显示README.md。如果设置为true，需要提供一个_coverpage.md文件，内容随意。
  - loadNavbar: true是否提供导航条，如果设置为true，需要提供一个_navbar.md文件，内容随意。