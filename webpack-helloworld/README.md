https://webpack.js.org/guides/getting-started/

npm init -y
npm install webpack webpack-cli --save-dev
npm install --save lodash

```json
{
  "name": "webpack-helloworld",
  "version": "1.0.0",
  "description": "npm init -y\r npm install webpack webpack-cli --save-dev",
  "main": "index.js",
  "private": true,
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^5.78.0",
    "webpack-cli": "^5.0.1"
  }
}
```

```json
{
  "name": "webpack-demo",
  "version": "1.0.0",
  "description": "",
  "private": true,
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "MIT",
  "devDependencies": {
    "webpack": "^5.38.1",
    "webpack-cli": "^4.7.2"
  }
}
```

## 运行
执行:
npx webpack

会将我们的脚本 src/index.js 作为 入口起点，也会生成 dist/main.js 作为。

在浏览器中打开 dist 目录下的 index.html，如果一切正常，你应该能看到以下文本：'Hello webpack'。

## 使用一个配置文件
webpack.config.js
```javaScript
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist'),
  },
};
```

执行：
npx webpack --config webpack.config.js
```
如果 webpack.config.js 存在，则 webpack 命令将默认选择使用它。我们在这里使用 --config 选项只是向你表明，可以传递任何名称的配置文件。这对于需要拆分成多个文件的复杂配置是非常有用的。
```

## npm scripts
考虑到用 CLI 这种方式来运行本地的 webpack 副本并不是特别方便，我们可以设置一个快捷方式。调整 package.json 文件，添加一个 npm script：
```javaScript
 {
   "name": "webpack-demo",
   "version": "1.0.0",
   "description": "",
   "private": true,
   "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack"
   },
   "keywords": [],
   "author": "",
   "license": "ISC",
   "devDependencies": {
     "webpack": "^5.4.0",
     "webpack-cli": "^4.2.0"
   },
   "dependencies": {
     "lodash": "^4.17.20"
   }
 }
```

现在，可以使用:
npm run build
命令，来替代我们之前使用的 npx 命令