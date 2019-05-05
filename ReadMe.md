# Setting App with React 16.x, Webpack 4.0  (2019)

> Init the node app
```javascript
npm init -y
```

> Modules and React
```javascript
npm install -S react react-dom --registry=https://registry.npmjs.com/
```

> Dev Modules and Prop Types
```javascript
npm i -D  prop-types --registry=https://registry.npmjs.com/
```

> Webpack
```javascript
npm install -D webpack webpack-cli webpack-dev-server react-hot-loader --registry=https://registry.npmjs.com/
```
> CSS
```javascript
npm install -D css-loader style-loader --registry=https://registry.npmjs.com/
```
> HTML
```javascript
npm install -D html-webpack-plugin --registry=https://registry.npmjs.com/
```

> Babel
```javascsript
npm install -D @babel/core @babel/preset-env @babel/preset-react babel-loader --registry=https://registry.npmjs.com/
```
> Babel RC - create .babelrc file in the node app directory
```shell
vi .babelrc
```
add the below content, save and exit the file
```
{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}
```

> Add NPM Script to the package.json created by npm init in the first step.
```shell
vi package.json
```
add below snipett and make sure the "scripts" object in json looks like below
```javascript
"scripts": {
  "start": "webpack-dev-server --open --mode development",
  "build": "webpack --mode production"
},
```
> Add HTML - index.html
```shell
vi index.html
```
add below content, save and exit the file

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

> Hot Reloader
```javascript
npm i -D react-hot-loader --registry=https://registry.npmjs.com/
```
> Start the React app
```javascript
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

> Tags
* ES Lint
* Sonar Lint
* Gzip Compression
* Chunking
