# Development Configuration

## `Express`

Express.js, or simply Express, is a web application framework for Node.js, released as free and open-source software under the MIT License. It is designed for building web applications and APIs. It has been called the de facto standard server framework for Node.js. [`More Info`](https://expressjs.com/)

## `Express Middleware`

Express middleware are functions that execute during the lifecycle of a request to the Express server. Each middleware has access to the HTTP request and response for each route (or path) it's attached to. In fact, Express itself is compromised wholly of middleware functions. [`More Info`](https://expressjs.com/en/guide/writing-middleware.html)

    // make express server
    const app = express();

    // static files
    app.use(express.static(PUBLIC_PATH));

## `CookieParser`

Parse Cookie header and populate req.cookies with an object keyed by the cookie names. Optionally you may enable signed cookie support by passing a secret string, which assigns req.secret so it may be used by other middleware. [`More info`](https://www.npmjs.com/package/cookie-parser)

    // cookie
    app.use(cookieParser())

## `webpack`

webpack is an open-source JavaScript module bundler. It is a module bundler primarily for JavaScript, but it can transform front-end assets like HTML, CSS, and images if the corresponding loaders are included. webpack takes modules with dependencies and generates static assets representing those modules. [`More info`](https://webpack.js.org/)

    // create webpack compiler
    const compiler = webpack(config);

## `webpackDevMiddleware`

An express-style development middleware for use with webpack bundles and allows for serving of the files emitted from webpack. This should be used for development only.

    // make bundled project source files accessable from memory
    app.use(webpackDevMiddleware(compiler, {
        serverSideRender: true,
        publicPath: DIST_ROUTE
    }));

Some of the benefits of using this middleware include:

- No files are written to disk, rather it handles files in memory
- If files changed in watch mode, the middleware delays requests until compiling has completed.
- Supports hot module reload (HMR).

## `webpackHotMiddleware`

Webpack hot reloading using only webpack-dev-middleware. This allows you to add hot reloading into an existing server without webpack-dev-server.
This module is only concerned with the mechanisms to connect a browser client to a webpack server & receive updates. It will subscribe to changes from the server and execute those changes using webpack's HMR API. Actually making your application capable of using hot reloading to make seamless changes is out of scope, and usually handled by another library.

    // recompile webpack when file changes
    app.use(webpackHotMiddleware(compiler.compilers.find(compiler => compiler.name === 'client')));

## `webpackHotServerMiddleware`

Webpack Hot Server Middleware is designed to be used in conjunction with webpack-dev-middleware (and optionally webpack-hot-middleware) to hot update Webpack bundles on the server.

    // hot update Webpack bundles on the server
    app.use(webpackHotServerMiddleware(compiler));

## `rssr-env-loader`

load env files and define environment varibale [More info](https://www.npmjs.com/package/rssr-env-loader)

## `rssr-server-is-ready`

use to check node server is ready [More info](https://github.com/rssr-org/rssr-server-is-ready)

## `open`

Open stuff like URLs, files, executables. Cross-platform. [More info](https://www.npmjs.com/package/open)

    // load .env files and define environment varibale before all actions
    require('../setup/evnLoader');
    // define global.FILE_VERSION for dist file version. see render/Index.js template. ::5::
    require('../setup/fileVersion');

    const open = require('open')
    const cookieParser = require('cookie-parser')
    const express = require('express')
    const webpack = require('webpack')
    const config = require('../webpack/development')
    const webpackDevMiddleware = require('webpack-dev-middleware')
    const webpackHotMiddleware = require('webpack-hot-middleware')
    const webpackHotServerMiddleware = require('webpack-hot-server-middleware')
    const devServerIsReady = require('../setup/devServerIsReady')
    const {DIST_ROUTE, PUBLIC_PATH} = require('../setup/constant')

    // express app
    const app = express();

    // cookie
    app.use(cookieParser())

    // create webpack compiler
    const compiler = webpack(config);

    // make bundled project source files accessable from memory
    app.use(webpackDevMiddleware(compiler, {
        serverSideRender: true,
        publicPath: DIST_ROUTE
    }));

    // static files
    app.use(express.static(PUBLIC_PATH));

    // recompile webpack when file changes
    app.use(webpackHotMiddleware(compiler.compilers.find(compiler => compiler.name === 'client')));

    // hot update Webpack bundles on the server
    app.use(webpackHotServerMiddleware(compiler));

    // run server
    const PORT = process.env.PORT || 4000;

    app.listen(PORT, error => {
        if (error) {
            return console.error('Error in server.development.js: ', error);
        } else {
            // wait to project built and app ready
            devServerIsReady(PORT)
                .then(function () {
                    // open project in browser
                    open(`http://localhost:${PORT}`);

                    console.log(`development server running at http://localhost:${process.env.PORT}`);
                })
        }
    });
