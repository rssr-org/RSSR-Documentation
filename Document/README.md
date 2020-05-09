# Overview
In first look at _**RSSR**_ project, you'll see some directories and files. We describe them here:

### Directories
  - [_/provider:_](Provider) This is our starting point, which includes basic settings.<br/><br/>
  - [_/public:_](Public) Here is where all the static files are stored. All the files in this folder will be accessible directly.<br/><br/>
  - [_/src:_](Src) This is the body of our application. 90% of the expected goals of the app will be defined in this folder.<br/><br/>

### Files
#### Environment Variables:
  - _**.env:**_ Enviroment variables for Development and Production mode
  - _**.env.development:**_ Enviroment variables for Development
  - _**.env.production:**_ Enviroment variables for Production

#### Configures:
  - _**.babelrc:**_ We used [Babeljs](https://babeljs.io/) for compiling Javascript and transpile its new features to older vesrions, that compatible with older browsers, that not supported new generations of Javascript language.
  - _**.eslintrc:**_ We also used [ESLint](https://eslint.org/) for automically finding, linting and fixing problems in **_RSSR_** apps.

___
# Rules
#### Naming Convention:
We considered using [camleCase](https://en.wikipedia.org/wiki/Camel_case) for default naming files and directories. but in some cases like HOCs and React Components, we prefferd using [PascalCase](https://techterms.com/definition/pascalcase).

#### Directories Types:
In _**RSSR**_ project, we've multiple types for each directories based on what they have or do.
  - **Entity Directories:** An entity directory is any singular, identifiable and separate directory which grow subcomponent in a tree structure. ex: home.js, about.js etc. <br/><br/>
  - **Wrap Directories:** It doesn't have Entity directory and isolated with their behavior, in fact to make project readable, they can hold different entities inside.<br/>
  _NOTE: Wrap directory can be chaining like [partial](Src/Partial). It means component folders can be connected together in a graph structure._<br/><br/>

  - **Special Directories:** // TODO: continue from here
___
# Relationships Between Directories
___
# Content List