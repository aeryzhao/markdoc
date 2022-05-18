# Vuepress快速构建文档

## 创建项目

1. 创建并进入一个新目录

   ```bash
   mkdir vuepress-starter && cd vuepress-starter
   ```

2. 使用你喜欢的包管理器进行初始化

   ```bash
   yarn init # npm init
   ```

3. 将 VuePress 安装为本地依赖

   我们已经不再推荐全局安装 VuePress

   ```bash
   yarn add -D vuepress # npm install -D vuepress
   ```

4. 创建你的第一篇文档

	```bash
	mkdir docs && echo '# Hello VuePress' > docs/README.md
	```

5. 在 `package.json` 中添加一些 [scripts(opens new window)](https://classic.yarnpkg.com/zh-Hans/docs/package-json#toc-scripts)

  这一步骤是可选的，但我们推荐你完成它。在下文中，我们会默认这些 scripts 已经被添加。

  ```bash
  {
  	"scripts": {
  	"docs:dev": "vuepress dev docs",
  	"docs:build": "vuepress build docs"
  	}
  }
  ```

6. 在本地启动服务器

	```bash
	yarn docs:dev # npm run docs:dev
	```
	
	VuePress 会在 [http://localhost:8080 (opens new window)](http://localhost:8080/)启动一个热重载的开发服务器。

## 目录结构

基础简洁版配置参考

```
.
├── docs
│   ├── .vuepress
│   │   ├── config.js
│   │ 
│   ├── README.md
│ 
└── package.json
```

config.js

``` javascript
// .vuepress/config.js
module.exports = {
  // 网站的标题
  title: "<title>",
  // 上下文根
  base: "/<root>/",
  themeConfig: {
    // 假定是 GitHub. 同时也可以是一个完整的 GitLab URL
    repo: "<github username>/<repo name>",
    // 自定义仓库链接文字。默认从 `themeConfig.repo` 中自动推断为
    // "GitHub"/"GitLab"/"Bitbucket" 其中之一，或是 "Source"。
    repoLabel: "Github",
    // 以下为可选的编辑链接选项
    // 假如你的文档仓库和项目本身不在一个仓库：
    docsRepo: "<github username>/<repo name>",
    // 假如文档放在一个特定的分支下：
    docsBranch: "master/docs",
    // 默认是 false, 设置为 true 来启用
    editLinks: true,
    // 默认为 "Edit this page"
    editLinkText: "帮助我们改善此页面！",
    // 最后更新时间
    lastUpdated: "Last Updated",
    // 最大深度
    sidebarDepth: 2,
    // 导航栏
    nav: [],
    // 侧边栏
    sidebar: {
      "/": [
        "",
        "ch1.md",
        "ch2.md",
        "ch3.md",
        "ch4.md",
        "ch5.md",
        "apA.md"
      ]
    }
  }
};

```

## 部署

### 部署到Github Page

在项目根目录建立`deploy.sh` 脚本

``` shell
#!/usr/bin/env sh

# 确保脚本抛出遇到的错误
set -e

# 生成静态文件
yarn run docs:build

# 进入生成的文件夹
cd docs/.vuepress/dist

# 如果是发布到自定义域名
# echo 'www.example.com' > CNAME

git init
git add -A
git commit -m 'deploy'

# 如果发布到 https://<USERNAME>.github.io
# git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git master

# 如果发布到 https://<USERNAME>.github.io/<REPO>
git push -f https://github.com/<USERNAME>/<REPO>.git master:gh-pages

cd -
```

通过Git终端git bash，执行sh deploy.sh即可。部署的文件会被推送gh-pages分支，在Github Page中指定部署该分支即可。



- 以上内容参考[Vuepress官网][vuepress]

[vuepress]:https://vuepress.vuejs.org/zh/guide/)	"vuepress官网"