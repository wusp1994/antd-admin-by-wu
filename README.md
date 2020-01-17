# antd-admin-by-wu
仿照修改 https://github.com/yezihaohao/react-admin 组装成自己的react后台管理系统模板。



### 扩展 Create React App 的 Webpack 配置

使用 CRA 创建完项目以后，项目在`package.json`里面提供了这样一个命令：

```json
{
  "scripts": {
    ...
    "eject": "react-scripts eject"
  }
}

```

执行完这个命令——`yarn run eject`后会将封装在 CRA 中的配置全部`反编译`到当前项目，这样用户就可以完全取得 webpack 文件的控制权，想怎么修改就怎么修改了。

```
# eject 后项目根目录下会出现 config 文件夹，里面就包含了 webpack 配置
config
├── env.js
├── jest
│   ├── cssTransform.js
│   └── fileTransform.js
├── paths.js
├── polyfills.js
├── webpack.config.dev.js // 开发环境配置
├── webpack.config.prod.js // 生产环境配置
└── webpackDevServer.config.js
```

CRA 与其他脚手架不同的另一个地方，就是可以通过升级其中的`react-scripts`包来升级 CRA 的特性。比如用老版本 CRA 创建了一个项目，这个项目不具备 [PWA](https://developers.google.com/web/progressive-web-apps/) 功能，但只要项目升级了`react-scripts`包的版本就可以具备 PWA 的功能，项目本身的代码不需要做任何修改。

缺点：

但如果我们使用了`eject`命令，就再也享受不到 CRA 升级带来的好处了，因为`react-scripts`已经是以文件的形式存在于你的项目，而不是以包的形式，所以无法对其升级。