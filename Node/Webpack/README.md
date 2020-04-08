# Getting started in learning webpack

I am learning step-by-step by looking at webpack doc. from top to bottom


# Getting started



# Asset mgmt

# Output mgmt

# Dev

## Sourcemap

### Why sourcemap?

Consider you have three JS files (`a.js`, `b.js`, `c.js`) in a `bundle.js` module. If there is an issue in b.js, the stack trace will point to `bundle.js` and not `b.js`.

In order to track down errors, JS provides **source maps**, which maps your compiled code to your source code.

### Chose dev. tool

1. webpack's Watch Mode
2. webpack-dev-server (Important; Used in VM/Vagrant/Prod. like env)
3. webpack-dev-middleware


#### Watch mode

`package.json`:

    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "watch": "webpack --watch",
        "build": "webpack"
    }

In watch mode, if you make a change to a file, developer does not need to build again. Webpack builds automatically.

#### webpack-dev-server

- Allows live reloading
- Used in prod-like VM/Vagrant/nginx setup

    npm install --save-dev webpack-dev-server

`package.json`:

    "scripts": {
          "test": "echo \"Error: no test specified\" && exit 1",
          "watch": "webpack --watch",
        + "start": "webpack-dev-server --open",
          "build": "webpack"
        }, 

`webpack.config.json`:

      const path = require('path');
      const HtmlWebpackPlugin = require('html-webpack-plugin');
      const { CleanWebpackPlugin } = require('clean-webpack-plugin');
    
      module.exports = {
        mode: 'development',
        entry: {
          app: './src/index.js',
          print: './src/print.js',
        },
        devtool: 'inline-source-map',
        /*
            devServer config tells the webpack-dev-server to serve files 
            from the dist directory on localhost:8080
        */
    +   devServer: { 
    +     contentBase: './dist',
    +   },
        plugins: [
          // new CleanWebpackPlugin(['dist/*']) for < v2 versions of CleanWebpackPlugin
          new CleanWebpackPlugin(),
          new HtmlWebpackPlugin({
            title: 'Development',
          }),
        ],
        output: {
          filename: '[name].bundle.js',
          path: path.resolve(__dirname, 'dist'),
        },
      }; 

More doc. for [devServer](https://webpack.js.org/configuration/dev-server/) config.

#### webpack-dev-middleware

A middleware that emits files from webpack to server. webpack-dev-server uses webpack-dev-middleware internally, but seperate webpack-dev-middleware is used for custom config.

Example: Connectiong the middleware to epxress server. 

`webpack-config.js`:

    const path = require('path');
      const HtmlWebpackPlugin = require('html-webpack-plugin');
      const { CleanWebpackPlugin } = require('clean-webpack-plugin');
    
      module.exports = {
        mode: 'development',
        entry: {
          app: './src/index.js',
          print: './src/print.js',
        },
        devtool: 'inline-source-map',
        devServer: {
          contentBase: './dist',
        },
        plugins: [
          new CleanWebpackPlugin(),
          new HtmlWebpackPlugin({
            title: 'Output Management',
          }),
        ],
        output: {
          filename: '[name].bundle.js',
          path: path.resolve(__dirname, 'dist'),
    +     publicPath: '/',
        },
      }; 

`server.js`

    const express = require('express');
    const webpack = require('webpack');
    const webpackDevMiddleware = require('webpack-dev-middleware');
    
    const app = express();
    const config = require('./webpack.config.js');
    const compiler = webpack(config);
    
    // Tell express to use the webpack-dev-middleware and use the webpack.config.js
    // configuration file as a base.
    app.use(webpackDevMiddleware(compiler, {
      publicPath: config.output.publicPath,
    }));
    
    // Serve the files on port 3000.
    app.listen(3000, function () {
      console.log('Example app listening on port 3000!\n');
    }); 


Run `node server.js`





# Code splitting


# Caching

# Authoring libraries


# Build performance

# Content security policies

    __webpack_nonce__ = 'c29tZSBjb29sIHN0cmluZyB3aWxsIHBvcCB1cCAxMjM=';// base-64 encoded string

## Why nonce attribute?

`nonce` attribute tells that the script or tag is served from the server and not injected fro ma 3rd party site.
Eg:

    <script nonce="fdfgyjhny7wuijmdv">

## Enabling CSP

- CSPs are not enabled by default. 
- A corresponding header `Content-Security-Policy` or tag `<meta http-equiv="Content-Security-Policy" ...>` needs to be sent with the document to instruct the browser to enable the CSP. 
- Here's an example of what a CSP header including a CDN white-listed URL might look like:
  
      Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com;

# Dev. -- Vagrant   

Prod. like env


# Dependency mgmt

# Installation

# Scaffolding

# Hot module replacement


# Tree shaking

# Production

# Lazy Loading  

# Shimming

# Typescript



**KIM** that when you are using 3rd party libraries, you need to intall type infromation for that library.

Example: For lodash, install its Typescript defn. for use in our TS project.

    npm install --save @types/lodash


# PWA

# Public Path

# Integrations

# Asset modules

# Advanced entry
