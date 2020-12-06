<div>
  <a href="https://github.com/rssr-org/RSSR">
    <img width="200" src="https://raw.githubusercontent.com/rssr-org/RSSR/master/public/asset/img/rssr-logo.png">
  </a>
</div><br/>

**RSSR** is a _React Server Side Rendering_ biolerplate that helps you creat SSR React apps easier than any time.

## Features
- SSR (Server Side Rendering)
- User authentication structure
- SEO optimization utilities
- SCSS Style Namespace
- and more…
___
## Installation
_NOTE: Make sure that you have **Node.js ^10.13.0** and **npm ^6** installed._
```shell
// Clone the RSSR repository 
git clone https://github.com/rssr-org/RSSR.git <YOUR_PROJECT_NAME>

// Move to cloned RSSR app directory
cd <YOUR_PROJECT_NAME>

// Install the require npm packages
npm install
```
___
## Usage tips
### Remove Fake API
We connected the Fake-API to the RSSR so you can see how it actually works.

after clone see `help.txt` file in `~/FakeApi` directory.

### Run in development mode
```shell
npm run dev
```
### Run in production mode
1. Create `/dist` directory, that contains the builded of your RSSR app
```shell
npm run build
```
2. Run the builded RSSR app<br/>
_NOTE: For running your RSSR app, you have two Predetermined ways.You can modify these latter by yourself._
```shell
npm run start
```
or,
```shell
npm run start-pm2
```
If you run your RSSR app with [PM2](https://www.npmjs.com/package/pm2), you can update your project after changes, with:
```shell
npm run up
```
**Read more: [Getting Started](Getting-Started)**<br/>
**Read everything about RSSR: [Documentation](Document)**
