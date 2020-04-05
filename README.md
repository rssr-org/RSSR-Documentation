<div align="left">
  <a href="https://github.com/rssr-org/RSSR">
    <img width="200" src="https://raw.githubusercontent.com/rssr-org/RSSR/master/public/asset/img/rssr-logo.png">
  </a>
</div>

## Features
RSSR is a SSR boilerplate for React js and contian:
- SSR (Server Side Rendering)
- User Authentication Structure
- SEO optimization utilities
- SCSS Style Namespace
- and more …

## Quick start
- Make sure that you have Node.js v10.13.0 and npm v6 or above installed.
- Clone repo using `git clone https://github.com/rssr-org/RSSR.git <YOUR_PROJECT_NAME>`
- Move to your local directory: `cd <YOUR_PROJECT_NAME>`
- Select one of the following instructions based on your environment

### Run as Development
1. Run `npm i` (install npm packages)
2. Run `npm run dev` in other next terminal (start running project for development)
3. stay for initial build to can see App over`localhost:8000` (App will be opened in browser automatically).

#### remove fake API
in real project you must remove fakeApi. 
1. go to `~/provider/server/development.js`, find `require('../setup/fakeApi')(app)` and remove it.
3. go to `~/provider/setup` and remove `fakeApi.js` file.
4. change `API_HOST_IN_CLIENT` and `API_HOST_IN_SERVER` in `.env` file. 

### Run as Production
1. pull changes from Git
2. Run `npm i` (install npm packages)
3. Run `npm run build` (building the project and inject it in to `/dist` directory at root of project)
4. Run one of below commands
#### initial start: 
- `npm run start` for start project with `node` runner (recommends for testing production).
- `npm run start-pm2-low` for start project with [pm2](https://pm2.keymetrics.io/docs/usage/quick-start/) tools and run production server over one core of CPU.
- `npm run start-pm2` is like `npm run start-pm2-low` but run over all CPU core. (learn more about it in [PM2 cluster](https://pm2.keymetrics.io/docs/usage/cluster-mode/)) (Recommend for Main production)

#### Updating: 
- `npm run up-low`, mix of delete available process and `npm run start-pm2-low` (once CPU core)
- `npm run up`,like `npm run up-low` but over all CPU core (Recommend for Main production)  

# Documentation
- [General](general)
  - [Installation](#)
  - [Folder Structure](general/folder_structure.md)
  - [CLI Commands](general/commands.md)
  - [Introduction ](general/introduction.md)
  - [Tool Configuration](general/files.md)
- [CSS](css/README.md)
- [JS](js/README.md)
  - [Trim-Redux](./trim-redux.md)
  - [Routing](./routing.md)
- [Styling (CSS)](css/README.md)
  - [Stylesheet](css/README.md#stylesheet)
  - [Sass](css/README.md#sass)
- [SEO](seo/README.md)
- [Testing](testing)
