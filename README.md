
# Documentation
document of RSSR (React Server Side Rendering) Boilerplate. 

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
RSSR is a SSR boilerplate for React js and contian:
- SSR (Server Side Rendering)
- User Authentication Structure
- SEO optimization utilities
- SCSS Style Namespace
- and more …

## Usage Tips
- run commands at root of project.

### Run as Development
1. Run `npm i` (install npm packages)
2. Run `npm run api` for fake api (NOTICE: in real projects you must remove fake api structure and there is no need to execute this)
2. Run `npm run dev` in other next terminal (start running project for development)
3. stay for initial build to can see App over`localhost:8000` (App will be opened in browser automatically).

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


## Structure
### CSS
See the [CSS documentation](css/README.md) for more information.

### JS
See the [JS documentation](js/README.md) for more information about the
JavaScript side of things.

### SEO
We use [react-helmet](https://github.com/nfl/react-helmet) for managing document head tags. Examples on how to
write head tags can be found [here](https://github.com/nfl/react-helmet#examples).
Also we use [rssr-seo-optimization](https://github.com/rssr-org/rssr-seo-optimization) that redirect domains starting with www to non-www and remove slash at the end of URL for improve SEO

### Testing
