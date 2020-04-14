# RSSA

# Rule

## Camel case
Camel case is the practice of writing phrases such that each word or abbreviation in the middle of the phrase begins with a capital letter, with no intervening spaces or punctuation. Common examples include "iPhone" and "eBay".

### `Note:` We use camcel case to name file and directory in RSSR
### `Note:` Component style file must be named as camel case in RSSR

## Pascal Case
PascalCase is a naming convention in which the first letter of each word in a compound word is capitalized

### `Note:` Component file must be named as pascal case in RSSR

# Tech Stack

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

- `provider/setup`: 


### `public/`
Here is where all the static files are stored. All the files in this folder will be accessible directly.



### `src/`
This is the body of our application. 90% of the expected goals of the app will be defined in this folder.
- `src/App`:
- `src/Component`:
- `src/Partioal`:
- `src/render`:
   - `Server` 
   - `Template` 
   - `client.js` 
- `src/setup`:
     - `Style`: this directory contains public styles.
     - `Utility`: this directory contains public javascript functions.
     - `Constant.js`: Here are constants.
     - `loacalStorage.js`: There are some datas that I went to set to browser's local storage at initial loading. 
     - `Store.js`: There are the initial state and configs about [`Trim-Redux`](../js/trim-redux.md) .

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

##  __style Directory: 
`__style` directory is used when two components have common style. It solves these rare issues by creating `__style` in the first parent of that directory to handle duplicate style.

## `__action` Directory:
`__action` directory is used when two components have common action. Create `__action` in the first parent of that directory to handle duplicate action.

## `__component` Directory:
`__component` is used when a component is the same in multiple containers, we can solve the issue by creating `__Component` in the first parent of that directory to handle duplicate component.

## Basic Building Blocks


### `TrimRedux`

trim-redux is a tool for simplifying working with the Redux in Reactjs. Trim-redux removed reducer, combineReducer and action in redux usage process
and lets you work with redux like react component state!
