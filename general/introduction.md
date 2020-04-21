# RSSR

## Rule

## Camel case

Camel case is the practice of writing phrases such that each word or abbreviation in the middle of the phrase begins with a capital letter, with no intervening spaces or punctuation. Common examples include "iPhone" and "eBay".

### `Note:` We use camcel case to name file and directory in RSSR

### `Note:` Component style file must be named as camel case in RSSR

## Pascal Case

PascalCase is a naming convention in which the first letter of each word in a compound word is capitalized

### `Note:` Component file must be named as pascal case in RSSR

## Tech Stack

Here's a curated list of packages that you should be at least familiar with before starting your awesome project. However, the best way to see a complete list of the dependencies is to check `package.json`

### Core

- [ ] [React](https://facebook.github.io/react/)
- [ ] [Trim-Redux](https://github.com/ebrahimiaval/trim-redux#readme)
- [ ] [Express](https://expressjs.com/)

### Linting

- [ ] [ESLint](http://eslint.org/)

## Project Structure

### `provider/`

This is our starting point, which includes basic settings.

- `provider/server`: As the name suggests, this folder contains development and production server configuration.
  - [`development.js`](./development.js.md): contains development configuration
  - [`production.js`](./production.js.md): contains production configuration

- `provider/webpack`: This folder contains webpack configuration
- `provider/setup`:Contains methods and additional operations of the provider section

### `public/`
Here is where all the static files are stored. All the files in this folder will be accessible directly.

### `src/`

This is the body of our application. 90% of the expected goals of the app will be defined in this folder.
`/src` folder has some sections, that explain below:
|**_Folder_**|**_Description_**|
|-------|-------|
|`src/App`|The main core of RSSR app. This folder contains all final view components _-we call them `Containers`-_ for getting on website/webapp's routes.|
|`src/Component`| The components by which we can create entities. They may be common in multiple containers.|
|`src/Partial`| React components and React echosystem Tools (e.g. HOCs, React Entities, ...) |
|`src/render`|The entry point of `/src` folder<ul><li>`/Server`: This directory contains `server.js` file. SSR concepts and renders is executing in this file</li><li>`/Template`:</li><li>`client.js`: This file will run in Browser environment. After loading the RSSR app, the code of this file will be executed. This file is similar to `index.js` in CRA projects.</li></ul>|
|`src/setup`|<ul><li>`/Style`: this directory contains public styles.</li><li>`/Utility`: this directory contains public javascript functions.</li><li>`Constant.js`: Here are constants.</li><li>`loacalStorage.js`: There are some datas that I went to set to browser's local storage at initial loading.</li><li>`Store.js`: There are the initial state and configs about [`Trim-Redux`](../js/trim-redux.md).</li></ul>|
 
## Relationships Between directories

<img src="relationships.png" title="Relationships Between directories" />

### `.babelrc, eslintrc, .env ...` :
There are Babel config, ESlint config, environmental variables for different modes and ... .

# RSSR Directory

There are two kind of directories in RSSR.

- [Entity Directory](#entity-directory)
- [Wrap Directory](#wrap-directory)

## Entity Directory

An entity directory is any singular, identifiable and separate directory which grow subcomponent in a tree structure. ex: home.js, about.js etc.

## Wrap Directory

It doesn't have Entity directory and isolated with their behavior, in fact to make project readable, they can hold different entities inside.

### `Note:` Wrap directory can be chaining like partial. It means component folders can be connected together in a graph structure.

## Special Directory

- [ `__style` Directory](#style-directory)
- [ `__action` Directory](#action-directory)
- [ `__component` Directory](#component-directory)

### `Note:` Two underline give an alert, shows that there is a special case.

## __style Directory:
`__style` directory is used when two components have common style. It solves these rare issues by creating `__style` in the first parent of that directory to handle duplicate style.

## `__action` Directory:
`__action` directory is used when two components have common action. Create `__action` in the first parent of that directory to handle duplicate action.

## `__component` Directory:
`__component` is used when a component is the same in multiple containers, we can solve the issue by creating `__Component` in the first parent of that directory to handle duplicate component.

## Expansion of Entity

| **_Dos_**         | **_Exceptions_**    | 
| -------------|-------------|
| 1-Every entity in the App,Component and Partial must have a directory | App.js file in the App folder |
| 2-Any entity with more than one file must be defined as a Entity Directory(Modular tree structure)  | Except for the js and css file until it doesn't reduce the readability of the project but also helps it |
| 3-The set of files and entities that have a specific definition must be defined as a Wrap Directory | Except for cases that include Entity Directory conditions                                               |

## Basic Building Blocks

### `TrimRedux`

trim-redux is a tool for simplifying working with the Redux in Reactjs. Trim-redux removed reducer, combineReducer and action in redux usage process
and lets you work with redux like react component state!
