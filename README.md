# nodejs manual

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
   


