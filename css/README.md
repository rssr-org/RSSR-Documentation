# Styling (CSS)

  - [Stylesheet](#stylesheet)
  - [Sass](#sass)
    - [Setup](#setup)
    - [Usage](#usage)



## Stylesheet

[Webpack](https://webpack.js.org/) allows you to import more than JavaScript.
Using the [`css-loader`](https://webpack.js.org/loaders/css-loader/) you can import CSS
into a JavaScript:

**`Button.css`**

```css
.danger {
  background-color: red;
}
```

**`Button.js`**

```js
import React from 'react';
import './Button.css'; // Tell Webpack that Button.js uses these styles

function Button() {
  // You can use them as regular CSS styles
  return <button className="danger">Click me</button>;
}
```

> For more information about Stylesheets and the `css-loader` see https://github.com/webpack-contrib/css-loader


## Sass

### Setup

### Usage

**`Button.scss`**

```scss
$error-color: red;

.danger {
  background-color: $error-color;
}
```

**`Button.js`**

```js
import React from 'react';
import './Button.scss';

function Button() {
  return <button className="danger">Click me</button>;
}
```

> For more information about Sass and the `sass-loader` see https://github.com/webpack-contrib/sass-loader