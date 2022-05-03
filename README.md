# Webpack React


## 1. Instalacion y configuracionn de React
```bash
  npm i react react-dom
```

## 2. Configuracion de webpack para react

### Instalacion de babel

```bash
npm install @babel/core @babel/preset-env @babel/preset-react babel-loader -D
```
.babelrc
```js
{
  "presets":[
    "@babel/preset-env",
    "@babel/preset-react"
  ]
}
```

### Instalacion de webpack

```bash
npm install webpack webpack-cli webpack-dev-server -D
```
webpack.config.js
```js
const path = require('path')
/**@type {import('webpack').Configuration} */
module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  resolve: {
    extensions: ['.js', '.jsx']
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        loader: 'babel-loader'
      }
    ]
  },
  devServer: {
    static: path.join(__dirname, 'dist'),
    compress: true,
    historyApiFallback: true,
    port: 3006,
    open: true
  }
}
```

## 3. Configuracion de plugins y loader para React

```bash
npm i html-webpack-plugin html-loader -D
```

## 4. CSS en React

```bash
npm install -D mini-css-extract-plugin css-loader style-loader sass sass-loader
```

## 5. Optimizacion de webpack para React
```bash
npm install -D npm install css-minimizer-webpack-plugin
```