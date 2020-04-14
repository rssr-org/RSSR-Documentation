# Configuration
## The root folder 
 - [`.eslintrc`](#)
 - [`.babelrc`](#babelrc)
 - [`.gitignore`](#gitignore)
 - [`package.json`](#)


## The root folder

- `.eslintrc`: Eslint settings which help us code easier and cleaner
  
  
## `.babelrc`: 
 All Babel API [options](https://babeljs.io/docs/en/6.26.3/babel-core#options) except the callbacks are allowed (because .babelrc files are serialized as JSON5). 
  - List of presets (a set of plugins) to load and use, consist of 
    - [`@babel/preset-react`](https://babeljs.io/docs/en/next/babel-preset-react.html)
    - [`@babel/preset-env`](https://babeljs.io/docs/en/babel-preset-env): is a smart preset that allows you to use the latest JavaScript without needing to micromanage which syntax transforms (and optionally, browser polyfills) are needed by your target environment(s)

  - List of plugins to load and use, consist of: 
    - [`@babel/plugin-transform-runtime`](https://babeljs.io/docs/en/babel-plugin-transform-runtime): A plugin that enables the re-use of Babel's injected helper code to save on codesize.
    - [`@babel/plugin-proposal-object-rest-spread`](https://babeljs.io/docs/en/babel-plugin-proposal-object-rest-spread)
    - [`@babel/plugin-proposal-decorators`](https://babeljs.io/docs/en/babel-plugin-proposal-decorators)
    - [`@babel/plugin-proposal-class-properties`](https://babeljs.io/docs/en/babel-plugin-proposal-class-properties)


 ## `.gitignore`: 
   Tells `git` to ignore certain files and folders which don't need to be version controlled, like the build folder.

