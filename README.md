# nodejs manual

npm 官网、包搜索 https://www.npmjs.com/ (npmjs.org会跳转到这页面)

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
   


