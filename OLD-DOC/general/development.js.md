# Development Configuration

## `Express`

Express.js, or simply Express, is a web application framework for Node.js, released as free and open-source software under the MIT License. It is designed for building web applications and APIs. It has been called the de facto standard server framework for Node.js. [`More Info`](https://expressjs.com/)

## `Express Middleware`
Express middleware are functions that are executed during the lifecycle of a request to the Express server. Each middleware has access to the HTTP request and response for each route (or path) it's attached to. In fact, Express itself is compromised wholly of middleware functions. [`More Info`](https://expressjs.com/en/guide/writing-middleware.html)


    // make express server
    const app = express();

    // static files
    app.use(express.static(PUBLIC_PATH));

## `CookieParser`

Parse Cookie header and populate req.cookies with an object keyed by the cookie names. Optionally you may enable signed cookie support by passing a secret string, which assigns req.secret so it may be used by other middleware. [`More info`](https://www.npmjs.com/package/cookie-parser)

    // cookie
    app.use(cookieParser())

## `webpack`
webpack is an open-source JavaScript module bundler. It is a module bundler primarily for JavaScript, but it can transform front-end assets like HTML, CSS, and images if the corresponding loaders are included. Webpack takes modules with dependencies and generates static assets representing those modules. [`More info`](https://webpack.js.org/)

    // create webpack compiler
    const compiler = webpack(config);

## `webpackDevMiddleware`
An express-style development middleware for using with webpack bundles and allows serving of the files emitted from webpack. This should be used for development only.

    // make bundled project source files accessable from memory
    app.use(webpackDevMiddleware(compiler, {
        serverSideRender: true,
        publicPath: DIST_ROUTE
    }));


Some of the benefits of using this middleware are as follow:
- No files are written to disk, rather it handles files in memory.
- If files changed in watch mode, the middleware delays requests until compiling has completed.
- Supports hot module reload (HMR).

## `webpackHotMiddleware`

Webpack hot reloading using only webpack-dev-middleware. This allows you to add hot reloading into an existing server without webpack-dev-server.
This module is only concerned with the mechanisms to connect a browser client to a webpack server & receive updates. It will subscribe to changes from the server and execute those changes using webpack's HMR API. Actually making your application capable of using hot reloading to make seamless changes is out of scope, and usually handled by another library.

    // recompile webpack when file changes
    app.use(webpackHotMiddleware(compiler.compilers.find(compiler => compiler.name === 'client')));

## `webpackHotServerMiddleware`

Webpack Hot Server Middleware is designed to be used in conjunction with webpack-dev-middleware (and optionally webpack-hot-middleware) to hot update Webpack bundles on the server.

Webpack Hot Server Middleware is very similar to the nodemon package in the nodejs.

The difference is that the nodemon ,run nodejs's web server from the beginning but Webpack Hot Server Middleware starts from the root file defined in the compiler and only refreshes the part that has changed.

    // hot update Webpack bundles on the server
    app.use(webpackHotServerMiddleware(compiler));