##
这个项目是 一个react16 SPA单页项目的模板, 可以让你快速上手写 react全家桶相关项目而不太关心配置, 打包也进行了优化; 还在不断优化中; 支持 打包后 生成 Java项目需要的 
${ctx}字符串变量, 也支持本地express服务器查看 打包后的文件
甚至给你写了一点示例代码,效果如下:
![HTTPS站点](/doc/startkit.png)

#### 技术栈
> ES5/6/7 + react16 + react-router4 + redux + axios + less/sass/stylus + antd@3 + decorator + express本地服务器

### 打包优化
webpack@3.x + hackpack + dllplugin + CommonsChunkPlugin + GLoabal变量 

###
如果你喜欢, 请帮忙 Star 一下喔, 你的肯定是我持续更新的动力🙂!

#### 项目源码结构
😝 src: tree
![HTTPS站点](/doc/src-dir.png)

## usage使用指南
推荐首先安装 yarn (sudo npm i -g yarn), 安装软件更快速

#### 下载项目安装依赖
* 依赖环境 webpack@3.x, node@8.x
* 1.克隆代码仓库
https://github.com/iceyangcc/react-ant-design-dllplugin-startkit
* 2.sudo npm install / sudo yarn 安装依赖

##### 首次进入开发模式, 打包通用库到vendor.js中
> npm run vendor

##### 进入开发模式, 开启项目
> npm start 开启前端代码

##### 打包编译, 生成静态资源文件到 build目录下
> npm run dev

##### 打包编译, 生成Java项目所需 ${ctx}/static/,上线代码到 build目录下(和dev路径写法不一样)
> npm run prod
如果需要的代码不是这样的格式, 可以修改: `config/scripts/build.js:98`中的相关内容, 该代码只是替换生成后index.html和css代码中的图片路径

#### 编译后的 build目录
build: tree
![HTTPS站点](/doc/build-dir.png)


##### 在本地服务器中预览,打包后的效果, 即查看 build 中的静态文件, 自动打开浏览器, 端口为 3002
> npm run server

> 推荐使用 yarn 代替 npm 相关命令

***
PS: public/index.html中的js脚本, 声明 Ajax请求的 路径前缀, 你可以根据需要配置这个代码, 原因是: 本地的 Java项目在调试时需要加项目路径,例如: localhost:8080/projectName/restapi/list
而上线时使用的是
xxx.com/restapi/list,
所以 npm run dev 打包是针对第一种的, 
npm run prod 是针对上线代码的.
***