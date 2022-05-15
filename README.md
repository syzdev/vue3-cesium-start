# vue3-cesium-start

一个基于Vue3的简易Cesium开发模板

## 效果

![demo](/screenshot/demo.png)

## 项目初始化

```
npm install
```
### 配置
注：以下配置非必须，根据实际情况选择。

补全`src/common/js/config.js`中的`Token`信息：

- `CesiumIonDefaultAccessToken`：前往 https://cesium.com/ 中注册账号，[详细教程](https://syzdev.cn/2021/08/10/注册Cesiumion教程/)，并且创建`Token`；

### 注意事项
第一次`npm run serve`编译项目时会报错，错误信息如下：
![error](/screenshot/error.png)

报错原因为`node_modules`中的`cesium`库并没有导出`widget.css`文件，导致在引入`widget.css`时找不到该文件，究其原因为Cesium在模块化导出方面没有做的很完善，解决方法如下：
1. 在项目目录下的`node_modules`文件夹中找到`cesium`文件夹；
2. 在`node_modules/cesium`文件夹下找到`package.json`文件；
3. 在`package.json`文件中的`"exports"`字段下添加`"./widgets.css": "./Source/Widgets/widgets.css"`。

具体代码如下：
```diff
"exports": {
  "./package.json": "./package.json",
  ".": {
    "require": "./index.cjs",
    "import": "./Source/Cesium.js"
  },
+  "./widgets.css": "./Source/Widgets/widgets.css"
},
```

### 编译

```
npm run serve
```

### 打包
```
npm run build
```

