# webpack-demo-2
1,创建webpack-demo-2文件夹

```
$ mkdir webpack-demo-2

```
2，进入
```
$ cd webpack-demo-2
```

3，初始化
```
$ npm init -y
```
4，创建文件```src/index.js```,```src/bar.js```, ```webpack.config.js```,```page.htm```

src/index.js
```
import bar from './bar';

bar();
console.log('i am index.js')
```

src/bar.js
```
export default function bar() {
  console.log('i am bar.js')
}
```
webpack.config.js
```
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  }
};

```

page.html
```
<!doctype html>
<html>
  <head>
  <title>webpack demo</title>
  </head>
  <body>
    <div>
      hello webpack
    </div>
    <script src="dist/bundle.js"></script>
  </body>
</html>
```


5，安装webpack
```
$ npm i -D webpack
```
6，运行webpack,首先需要在package.josn里对webpack命令进行定义

```
"name": "webpack-demo-2",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    //两个命令
    "webpack":"webpack",  //运行webpack
    "build": "webpack -w"  // 监听文件，实时编译
  }
```
然后就可以 
```
$ npm run webpack
```
进行webpack编译打包。

7，输入npm run webpack之后，命令会提示安装webpack-cli， yes/no  .
直接yes就好了 ， 安装好之后就直接运行webpack了。
8，打开page.html,查看效果
```
$ srart/open page.html
```
