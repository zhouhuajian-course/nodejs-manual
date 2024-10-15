![image](https://github.com/user-attachments/assets/9e59c621-2ede-4200-ae6d-b7119357a012)# nodejs manual

npm 官网、包搜索 https://www.npmjs.com/ (npmjs.org会跳转到这页面)

## Node.js

1. Node.js® 是一个免费、开源、跨平台的 JavaScript 运行时环境，它让开发人员能够创建服务器、Web 应用、命令行工具和脚本。不是一门编程语言，更准确的说法是 JS 运行时环境；`浏览器和 Node.js 都使用 JavaScript 作为编程语言。`
2. 可以使用 `require` (CJS) 或 `import` (MJS) 来导入模块；
3. Node.js 在浏览器之外运行 V8 JavaScript 引擎（Google Chrome 的核心）。这使得 Node.js 的性能非常出色。`https://nodejs.org/zh-cn/learn/getting-started/introduction-to-nodejs`
4. 在 Node.js 中，可以毫无问题地使用新的 ECMAScript 标准，因为您不必等待所有用户更新他们的浏览器 - 您可以通过更改 Node.js 版本来决定使用哪个 ECMAScript 版本，并且您还可以通过使用标志运行 Node.js 来启用特定的实验性功能。
5. 进程 线程
```text
Node.js 应用程序在单个进程中运行，无需为每个请求创建新线程。Node.js 在其标准库中提供了一组异步 I/O 原语，可防止 JavaScript 代码阻塞，并且通常，Node.js 中的库是使用非阻塞范例编写的，这使得阻塞行为成为例外而不是常态。

当 Node.js 执行 I/O 操作（如从网络读取、访问数据库或文件系统）时，Node.js 不会阻塞线程并浪费 CPU 周期等待，而是会在响应返回时恢复操作。

这使得 Node.js 能够使用单个服务器处理数千个并发连接，而​​不会引入管理线程并发的负担，而这可能是一个重要的错误来源。
```
6. nvm是运行 Node.js 的一种流行方式。它允许您轻松切换 Node.js 版本，并安装新版本以尝试并在出现问题时轻松回滚。使用旧 Node.js 版本测试您的代码也非常有用。 `https://nodejs.org/zh-cn/learn/getting-started/how-to-install-nodejs`
7. 异步编程 `https://nodejs.org/zh-cn/learn/getting-started/how-much-javascript-do-you-need-to-know-to-use-nodejs`
```text
以下概念对于理解异步编程也是关键，异步编程是 Node.js 的基本部分之一：

- 异步编程和回调
- 计时器
- 承诺
- Async 和 Await
- 闭包
- 事件循环
```
8. Node.js 和浏览器之间的区别 `https://nodejs.org/zh-cn/learn/getting-started/differences-between-nodejs-and-the-browser`
```text
浏览器和 Node.js 都使用 JavaScript 作为编程语言。构建在浏览器中运行的应用程序与构建 Node.js 应用程序完全不同。尽管它们始终都是 JavaScript，但仍存在一些关键差异，这些差异使体验截然不同。

在浏览器中，您大部分时间都在与 DOM 或其他 Web 平台 API（如 Cookies）进行交互。当然，这些在 Node.js 中并不存在。您没有document以及window浏览器提供的所有其他对象。
而在浏览器中，我们没有 Node.js 通过其模块提供的所有优良 API，例如文件系统访问功能。
另一个很大的区别是，在 Node.js 中，您可以控制环境。除非您正在构建任何人都可以部署到任何地方的开源应用程序，否则您知道将在哪个版本的 Node.js 上运行该应用程序。与浏览器环境相比，您无法选择访问者将使用哪种浏览器，这非常方便。

另一个区别是 Node.js 同时支持 CommonJS 和 ES 模块系统（自 Node.js v12 起），而在浏览器中，我们开始看到 ES 模块标准正在实施。

In practice, this means that you can use both require() and import in Node.js, while you are limited to import in the browser.
```
9. V8 引擎 `V8的名字来源于汽车的“V型8缸发动机”` `V8最初是由 Lars Bak 团队开发的，以汽车的 V8 发动机（有八个气缸的V型发动机）进行命名，预示着这将是一款性能极高的 JavaScript 引擎，在 2008年9月2号 同 chrome 一同开源发布。` `V8 是 JavaScript 引擎，即它解析并执行 JavaScript 代码。DOM 和其他 Web 平台 API（它们都构成了运行时环境）由浏览器提供。` `https://nodejs.org/zh-cn/learn/getting-started/the-v8-javascript-engine` `V8发动机是有八个气缸的V型发动机，八个气缸分成两排，一排四个，两排气缸之间成一定的角度，这个角度一般为90°，亦有较窄夹角八个活塞驱动单一曲轴的例子[1]。` `https://zh.wikipedia.org/wiki/V8%E5%8F%91%E5%8A%A8%E6%9C%BA`
10. V8 引擎 2008 年发布，Node.js 2009 选择 V8 引擎，`V8 于 2009 年被选为 Node.js 的引擎，随着 Node.js 的流行度激增，V8 成为现在为大量用 JavaScript 编写的服务器端代码提供支持的引擎。`
11. Node.js 除了 开发 服务端，还可以桌面应用程序。`Node.js 生态系统非常庞大，这要归功于 V8，它还为桌面应用程序和 Electron 等项目提供支持。`
12. npm是 Node.js 的标准包管理器。

## npm Nodejs 包管理工具

1. npm install 安装项目依赖 (package.json) 出现，表示有四个包正在寻找资金支持
    ```text
    4 packages are looking for funding
      run `npm fund` for details
    ```
2. npm login 可以登录，npm whoami 可以看登录名，npm publish 发布包，npm unpublish 取消发布包 `使用该npm search命令显示公共注册表中可用的所有内容。使用npm ls显示您已安装的所有内容。`    
3. npm registry 软件注册中心，是一个 JavaScript 软件包数据库，每个软件包都包含软件和元数据。 `https://docs.npmjs.com/about-the-public-npm-registry`
4. 要更新到最新版本的 npm，请在命令行上运行`npm install npm@latest -g` `https://docs.npmjs.com/about-npm-versions`
5. 目前无法更改您的 npm 用户名。您需要创建一个新帐户并手动将数据迁移到新帐户。删除您的原始帐户。请注意，这是永久性的，30 天后，此帐户名可供其他人认领。
6. `downgrading-to-a-free-user-account` `upgrading-to-a-paid-user-account` 降级 升级
7. 我们强烈建议使用nvm等 Node 版本管理器来安装 Node.js 和 npm。我们不建议使用 Node 安装程序，因为 Node 安装过程会将 npm 安装在具有本地权限的目录中，并且在全局运行 npm 软件包时可能会导致权限错误。 `https://docs.npmjs.com/downloading-and-installing-node-js-and-npm`
8. A package is a file or directory that is described by a package.json file. A package must contain a package.json file in order to be published to the npm registry. For more information on creating a package.json file, see "Creating a package.json file". `https://docs.npmjs.com/about-packages-and-modules/`
```text
About modules

A module is any file or directory in the node_modules directory that can be loaded by the Node.js require() function.

To be loaded by the Node.js require() function, a module must be one of the following:

A folder with a package.json file containing a "main" field.
A JavaScript file.
Note: Since modules are not required to have a package.json file, not all modules are packages. Only modules that have a package.json file are also packages.

In the context of a Node program, the module is also the thing that was loaded from a file. For example, in the following program:

var req = require('request')
The req variable refers to the request module returned by the require() function.
```
9. @ scope `https://docs.npmjs.com/about-scopes`
10. 创建 `package.json` `https://docs.npmjs.com/creating-a-package-json-file`
11. Node.js 模块是一种可以发布到 npm的包。
12. 项目依赖包 `dependencies` `devDependencies` `https://docs.npmjs.com/specifying-dependencies-and-devdependencies-in-a-package-json-file`
13. 版本定义 `https://docs.npmjs.com/about-semantic-versioning`
14. 软件包的 tag `lastest` 是 `npm publish` 默认创建的 tag `https://docs.npmjs.com/adding-dist-tags-to-packages` `分发标签 (dist-tags) 是人类可读的标签，可用于组织和标记您发布的软件包的不同版本。dist-tags 是对语义版本控制的补充。除了比语义版本编号更易于阅读之外，标签还允许发布者更有效地分发其软件包。`
15. `注意：我们强烈建议弃用软件包或软件包版本，而不是取消发布它们，因为取消发布会将软件包从注册表中完全删除，这意味着依赖它的任何人都将无法再使用它，并且不会收到任何警告。`
16. 搜索 安装 软件包 `https://docs.npmjs.com/searching-for-and-choosing-packages-to-download`
```text
使用 dist-tags 安装包

例如npm publish，npm install <package_name>将latest默认使用标签。

要覆盖此行为，请使用npm install <package_name>@<tag>。例如，要安装example-package带有 标记的版本的beta，请运行以下命令：

npm install example-package@beta
```
17. 全局安装 安装工具 如果是偶尔使用，建议 `npx` `https://docs.npmjs.com/downloading-and-installing-packages-globally` `提示：如果您使用的是 npm 5.2 或更高版本，我们建议使用npx全局运行包。` `如果您使用的是 npm 5.2 或更高版本，您可能需要考虑使用npx作为运行全局命令的替代方法，尤其是当您只是偶尔需要命令时。` `https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally`
```text
全局安装包允许您将包中的代码用作本地计算机上的一组工具。

要全局下载并安装程序包，请在命令行上运行以下命令：

npm install -g <package_name>
```
18. `npm update` 更新包 `-g` 更新全局包 `<package_name>` `https://docs.npmjs.com/updating-packages-downloaded-from-the-registry`
19. `require` 使用 npm 下载的 包 `https://docs.npmjs.com/using-npm-packages-in-your-projects` `要使用范围包，只需在使用包名称的任何位置包含范围即可。`
20. 移除包 `https://docs.npmjs.com/uninstalling-packages-and-dependencies` `package-lock.json` 是对包的保存 `--save`
```text
无作用域的包
npm uninstall <package_name>
作用域包
npm uninstall <@scope/package_name>

卸载全局包

要卸载无范围的全局包，请在命令行上使用uninstall带有-g标志的命令。如果包有范围，则包括范围。

无作用域的包
npm uninstall -g <package_name>
作用域包
npm uninstall -g <@scope/package_name>

删除本地包但不将其从 package.json 中删除
使用--no-save将告诉 npm 不要从您的package.json、npm-shrinkwrap.json或package-lock.json文件中删除该包。
```
21. `Creating and publishing an organization scoped package` 每个组织都被授予一个组织范围，即与组织名称匹配的组织所拥有的软件包的唯一命名空间。例如，名为“wombat”的组织将具有范围@wombat。`https://docs.npmjs.com/about-organization-scopes-and-packages` `https://docs.npmjs.com/creating-and-publishing-an-organization-scoped-package`
22. npm 命令 `https://docs.npmjs.com/cli/v10/commands/npm`
```text
目录
查看folders以了解 npm 放置内容的位置。

具体来说，npm 有两种操作模式：

本地模式：npm 将包安装到当前项目目录中，默认为当前工作目录。包安装到./node_modules，bins 安装到./node_modules/.bin。
全局模式：npm 将包安装到 install 前缀中，$npm_config_prefix/lib/node_modules并将 bins 安装到 中$npm_config_prefix/bin。
本地模式是默认模式。在任何命令上使用-g或--global可改为在全局模式下运行。

Developer Usage
If you're using npm to develop and publish your code, check out the following help topics:

json: Make a package.json file. See package.json.
link: Links your current working code into Node's path, so that you don't have to reinstall every time you make a change. Use npm link to do this.
install: It's a good idea to install things if you don't need the symbolic link. Especially, installing other peoples code from the registry is done via npm install
adduser: Create an account or log in. When you do this, npm will store credentials in the user config file.
publish: Use the npm publish command to upload your code to the registry
```
23. npm init `https://docs.npmjs.com/cli/v10/commands/npm-init`
24. npm install `https://docs.npmjs.com/cli/v10/commands/npm-install`
25. npm uninstall `https://docs.npmjs.com/cli/v10/commands/npm-uninstall`  `别名：unlink、remove、rm、r、un`
26. npm update `https://docs.npmjs.com/cli/v10/commands/npm-update`
27. npm 文件夹结构 `https://docs.npmjs.com/cli/v10/configuring-npm/folders`
```text
npm 将各种东西放到你的计算机上。这就是它的工作。

本文档将告诉您它将什么放在哪里。

总结
本地安装（默认）：将内容放入./node_modules当前包根目录中。
全局安装（使用-g）：将内容放在 /usr/local 或者安装节点的任何位置。
如果要使用它，请在本地安装它require()。
如果您要在命令行上运行它，请全局安装它。
如果两者都需要，则在两个地方安装，或者使用npm link。
```
28. `package.json` `package-lock.json` `https://docs.npmjs.com/cli/v10/configuring-npm/package-json` `https://docs.npmjs.com/cli/v10/configuring-npm/package-lock-json` 固定依赖树
```text
package-lock.json

A manifestation of the manifest

Description

package-lock.json is automatically generated for any operations where npm modifies either the node_modules tree, or package.json. It describes the exact tree that was generated, such that subsequent installs are able to generate identical trees, regardless of intermediate dependency updates.

This file is intended to be committed into source repositories, and serves various purposes:

- Describe a single representation of a dependency tree such that teammates, deployments, and continuous integration are guaranteed to install exactly the same dependencies.
- Provide a facility for users to "time-travel" to previous states of node_modules without having to commit the directory itself.
- Facilitate greater visibility of tree changes through readable source control diffs.
- Optimize the installation process by allowing npm to skip repeated metadata resolutions for previously-installed packages.
- As of npm v7, lockfiles include enough information to gain a complete picture of the package tree, reducing the need to read package.json files, and allowing for significant performance improvements.

When npm creates or updates package-lock.json, it will infer line endings and indentation from package.json so that the formatting of both files matches.
```
29. 注册中心 `https://docs.npmjs.com/cli/v10/using-npm/registry` `npm 默认配置为使用https://registry.npmjs.org上的npm 公共注册中心。使用 npm 公共注册中心 须遵守https://docs.npmjs.com/policies/terms上的使用条款。`
30. 安装包时，包名称 `https://docs.npmjs.com/cli/v10/using-npm/package-spec`
```text
Package name

- [<@scope>/]<pkg>
- [<@scope>/]<pkg>@<tag>
- [<@scope>/]<pkg>@<version>
- [<@scope>/]<pkg>@<version range>

Refers to a package by name, with or without a scope, and optionally tag, version, or version range. This is typically used in combination with the registry config to refer to a package in a registry.

Examples:

- npm
- @npmcli/arborist
- @npmcli/arborist@latest
- npm@6.13.1
- npm@^4.0.0
```
31. scope `https://docs.npmjs.com/cli/v10/using-npm/scope`
32. !!! 这块内容注意，好像跟很多老师讲的内容，不是特别符合。!!! scripts 生命周期脚本 `Life Cycle Scripts` `These all can be executed by running npm run-script <stage> or npm run <stage> for short.` `https://docs.npmjs.com/cli/v10/using-npm/scripts` 
```text
npm start
prestart
start
poststart
If there is a server.js file in the root of your package, then npm will default the start command to node server.js. prestart and poststart will still run in this case.
```
33. 卸载 npm `sudo npm uninstall npm -g` `https://docs.npmjs.com/cli/v10/using-npm/removal`
34. 三个非常重要的文档模块 `https://docs.npmjs.com/cli/v10`
```text
npm CLI

- CLI Commands
- Configuring npm
- Using npm (这块要特别留意，很重要)
```

## import & export 导入 导出

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export

Every module can have two different types of export, named export and default export. You can have multiple named exports per module but only one default export.   
有两种不同的导出方式，具名导出和默认导出。你能够在每一个模块中定义多个具名导出，但是只允许有一个默认导出。

```javascript
// test2.js
export const name = "xiaoming"
var age = 18

function intro() {
    return name + age
}
export { age, intro }
const info = {
    name,
    age
}
export default info  // 默认导出，导入时可以自定义变量名
```

```javascript
// test1.js
import {name, age, intro} from "./test2.js"
import thisIsATest from "./test2.js"   // 导入时可以自定义变量名

console.log(name, age, intro, thisIsATest)
```

```shell
$ node .\test1.js
xiaoming 18 [Function: intro] { name: 'xiaoming', age: 18 }
```


## 模块名 module_name

避免模块名冲突

http 核心模块  
@someorganization/http 某个组织的http模块    
node:http nodejs官方的http模块  

## 非常方便的启动只有静态页面的 Web 服务器

在静态页面的根目录，运行 npx serve 即可，非常方便，而且还自动帮你复制了URL。

## Windows 安装多个 NodeJS

问题：使用msi安装，有低版本时，会自动卸载低版本；有高版本时，低版本无法安装。

解决：  

https://github.com/coreybutler/nvm-windows  
https://github.com/coreybutler/nvm-windows/releases  
A node.js version management utility for Windows. Ironically written in Go.  
NodeJS 版本管理管理器

NVM NodeJS Version Manager

1. 安装前卸载已安装的NodeJS
2. 下载nvm-setup.exe，并执行，填 D:\nvm D:\nodejs
3. 执行nvm install lts (To install the latest stable version, run nvm install lts.)
   ```
   PS C:\Users\zhouhuajian> nvm list
       20.15.0
   PS C:\Users\zhouhuajian> nvm use 20.15.0
   Now using node v20.15.0 (64-bit)
   PS C:\Users\zhouhuajian> node -v
   v20.15.0
   ```
5. 执行nvm install 12.14.0
   ```
   PS C:\Users\zhouhuajian> nvm use 12.14.0
   Now using node v12.14.0 (64-bit)
   PS C:\Users\zhouhuajian> node -v
   v12.14.0
   PS C:\Users\zhouhuajian> nvm list
  
       20.15.0
     * 12.14.0 (Currently using 64-bit executable)
   ```
   


