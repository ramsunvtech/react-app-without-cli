# Setting App with React 16.x, Webpack 4.0  (2019)

> Init the node app
```shell
npm init -y
```

> Add React and ReactDOM
```javascript
npm install -S react react-dom --registry=https://registry.npmjs.com/
npm i -D  prop-types --registry=https://registry.npmjs.com/
```
> Add Babel.
```shell
npm install -D @babel/core @babel/preset-env @babel/preset-react --registry=https://registry.npmjs.com/
```

> Add Webpack, Loaders.
```shell
npm install -D webpack webpack-cli webpack-dev-server --registry=https://registry.npmjs.com/
npm install -D css-loader style-loader --registry=https://registry.npmjs.com/
npm install -D html-webpack-plugin --registry=https://registry.npmjs.com/
npm install -D babel-loader --registry=https://registry.npmjs.com/
```

> Add Hot Loader.
```shell
npm install -D react-hot-loader --registry=https://registry.npmjs.com/
```

> Babel RunTime Configuration - create .babelrc.
```shell
vi .babelrc
```

> Add Content in `.babelrc`
```
{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}
```

> Edit `package.json`.
```shell
vi package.json
```

> `package.json` Content in Scripts.
```javascript
"scripts": {
  "start": "webpack-dev-server --open --mode development",
  "build": "webpack --mode production"
},
```
> Add `public` and `src` directory.
```shell
mkdir public src
```

> Create HTML - index.html
```shell
cd public/
vi index.html
```

> `index.html` Content.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta name="theme-color" content="#000000">
    <meta name="googlebot" content="noindex, noarchive" />
    <meta name="robots" content="noindex, nofollow" />

    <title>React App without CLI</title>
  </head>
  <body>
    <noscript>
      You need to enable JavaScript to run this app.
    </noscript>
    <div id="app-without-cli"></div>
    <script src="./app-bundle.js"></script>
  </body>
</html>
```

> Create App Component.
```shell
cd src/
vi App.js
```

> `App.js` Script.
```
import React from 'react';

function App () {
  return (
    <h1>
      Welcome to React App without CLI.
    </h1>
  );
}

export default App;
```

> Create Index File
```shell
cd src/
vi index.js
```

> `index.js` Script.
```
import React from 'react';
import ReactDOM from 'react-dom';

import App from './App';

ReactDOM.render(
  <App />,
  document.getElementById('app-without-cli')
); 
```

> Create Webpack Config.
```shell
vi webpack.config.js
```

> `webpack.config.js` Script.
```
const webpack = require('webpack');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  module: {
    rules: [
      {
        test: /\.(js)$/,
        exclude: /node_modules/,
        use: ['babel-loader']
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js']
  },
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'app-bundle.js'
  },
  plugins: [
    new webpack.HotModuleReplacementPlugin(),

    new HtmlWebpackPlugin({
      inject: true,
      template: './public/index.html',
    }),
  ],
  devServer: {
    contentBase: './dist',
    hot: true
  }
};
```

> Start the React app
```shell
npm start
```

> Referrences
* https://github.com/rwieruch/minimal-react-webpack-babel-setup
* https://www.robinwieruch.de/minimal-react-webpack-babel-setup/
* https://codeburst.io/4-four-ways-to-style-react-components-ac6f323da822
* https://medium.freecodecamp.org/how-to-set-up-deploy-your-react-app-from-scratch-using-webpack-and-babel-a669891033d4
* https://blog.bitsrc.io/setting-a-react-project-from-scratch-using-babel-and-webpack-5f26a525535d
* https://medium.com/@pioul/modular-css-with-react-61638ae9ea3e
* https://medium.com/@rossbulat/formik-for-react-introduction-to-form-management-done-right-971889b40f9f

> Comming Soon...
* ES Lint
* Sonar Lint
* Gzip Compression
* Chunking
