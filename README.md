# init-template

> Vue的初始化模板

这个模板在vue-cli提供的webpack模板上做了以下配置：

- 在创建时选择了使用`vue-router`、单元测试和端到端测试。
- 没有开启默认的`eslint`，因为推荐使用[Standard JS](https://standardjs.com/index.html#install)来进行语法检查。
- 安装`axios`来调用ajax。
- 安装`vuex`来管理状态。
- `src`目录下新建`views`文件夹，用来存放页面。原有`components`文件夹专用于存放组件。
- `src`目录下新增`vuex`文件夹，用于存放`vuex`相关信息。
- `src`目录下新增`api`文件夹，用于存放ajax调用相关函数。
- `src`目录下新增`utils`文件夹，用于存放可能用到的工具函数。
- **没有**配置`sass`，因为经讨论只打算用原生css。
- 引入normalize.css统一不同浏览器渲染的形式。


## 项目结构

```
|-- build                            // Webpack相关配置
|-- config                           // 项目开发环境配置
|-- src                              // 源码目录
|   |-- api                          // ajax调用相关函数，，以后根据需要可能还要分文件夹管理
|   |-- assets                       // 静态资源
|   |-- components                   // 组件
|   |-- router                       // 路由配置，以后根据需要可能还要分文件夹管理
|   |-- vuex                         // Vuex状态管理
|       |-- index.js                 // 根级别的状态管理，以后东西多了可能还要分成action.js, mutation.js等等
|       |-- modules                  // 各业务模块的局部状态管理
|   |-- utils                        // 工具集合
|   |-- App.vue                      // 页面入口
|   |-- main.js                      // 程序入口，加载各种公共组件
|-- static                           // 静态文件
|-- .babelrc                         // babel-loader 配置
|-- .editorconfig                    // 定义代码格式
|-- package.json                     // 项目基本信息
```

### 关于src/assets和static

它们存放的都是静态资源。不过在webpack构建的时候，前者里的东西会随着vue文件一起各种被打包，而后者里的东西是直接复制的。

以设定图片的`src`属性为例，如果`src`里写`assets/xxx`是行不通的，因为构建出来根本没有`assets`这样一个文件夹，而只有`static`这个文件夹。解决方案有2个，一个就是使用`require`的方式引用图片，另外一个比较简单的就是把图片放到`static`文件夹再引用了。

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
