
# Documentation
Document of RSSR (React Server Side Rendering) boilerplate. 

## Table of Contents
- [General](general)
  - [**CLI Commands**](general/commands.md)
  - [Introduction ](general/introduction.md)
  - [Tool Configuration](general/files.md)
- [JS](js)
  - [Trim-Redux](js/trim-redux.md)
- [Styling (CSS)](css/README.md)
  - [Stylesheet](css/README.md#stylesheet)
  - [Sass](css/README.md#sass)
- [Testing](testing)

## Overview
RSSR is a SSR boilerplate for React js which contains:
- SSR (Server Side Rendering)
- User Authentication Structure
- SEO optimization utilities
- SCSS Style Namespace
- and more …

## Usage Tips
- Run commands at root of project.

### Run in Development mode
1. Run `npm i` (install npm packages).
2. Run `npm run dev` in other next terminal (start running project in development mode).
3. Stay for initial build to be able to see App over`localhost:8000` (App will be opened in browser automatically).

#### remove fake API
In the real project you must remove fakeApi. 
1. Go to `~/provider/server/development.js`, find `require('../setup/fakeApi')(app)` and remove it.
3. Go to `~/provider/setup` and remove `fakeApi.js` file.
4. Change `API_HOST_IN_CLIENT` and `API_HOST_IN_SERVER` in `.env` file. 

### Run in Production mode
1. Pull changes from Git.
2. Run `npm i` (install npm packages).
3. Run `npm run build` (building the project and inject it in to `/dist` directory at root of project).
4. Run one of the following commands.
#### initial start: 
- `npm run start` for starting the project by `nodejs` runner (recommended for testing production).
- `npm run start-pm2-low` for starting the project by [pm2](https://pm2.keymetrics.io/docs/usage/quick-start/) tools and run production server over one core of CPU.
- `npm run start-pm2` is like `npm run start-pm2-low` but it runs over all CPU core. (learn more about it in [PM2 cluster](https://pm2.keymetrics.io/docs/usage/cluster-mode/)) (recommended for main production)

#### Updating: 
- `npm run up-low`, mix of delete available process and `npm run start-pm2-low` (once CPU core)
- `npm run up`,like `npm run up-low` but over all CPU core (recommended for main production)  


## Structure
### CSS
See the [CSS documentation](css/README.md) for more information.

### JS
See the [JS documentation](js/README.md) for more information about the
JavaScript side of things.

### SEO
We use [react-helmet](https://github.com/nfl/react-helmet) for managing document head tags. Examples on how to
write head tags can be found [here](https://github.com/nfl/react-helmet#examples).
Also we use [rssr-seo-optimization](https://github.com/rssr-org/rssr-seo-optimization) which redirects domains starting with www to non-www and removes slash at the end of URL for improving SEO.

### Testing
