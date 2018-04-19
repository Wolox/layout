# Wolox Layout

[![circle-ci](https://img.shields.io/circleci/project/github/Wolox/wolox-layout.svg)](https://circleci.com/gh/Wolox/wolox-layout)
[![npm](https://img.shields.io/npm/v/wolox-layout.svg)](https://www.npmjs.com/package/wolox-layout)

[![FEArmy](./assets/FEA_icon.png)](https://github.com/orgs/Wolox/teams/front-end-army/members)

## Features

* `margins.scss` & `paddings.scss` files contains all the margin and padding classes you need to start a basic project.
* `layout.scss` contains the basic flex box properties.

## Installation

1.  intall the package with `npm` or `yarn`

#### npm

```bash
npm i wolox-layout
```

#### yarn

```bash
yarn add wolox-layout
```

2- Include the wolox-bootstrap.scss before the index file of your CSS/SCSS.

If you want to import the 'wolox-bootstrap' in this way:

```js
@import 'wolox-bootstrap';
```

You have to add the following lines to the webpack configuration file:

```js
{
  loader: 'sass-loader',
  options: {
    includePaths: ['node_modules/wolox-layout']
  }
}
```

Otherwise you can import this file by doing:

```js
@import 'node_modules_path/wolox-layout/wolox-bootstrap';
```

Another way is to import the `margins.scss`, `paddings.scss` or `layout.scss` separately.

## Usage

* This will generate a margin top of 10px to your headline:


```html
 <h1 class="m-top-1">....</h1>
```

* This will generate a padding top of 10px to your headline:

```html
  <h1 class="p-top-1">....</h1>
```

* For responsive views just append an `-sm` to the class (e.g. `m-top-10-sm` or `p-top-10-sm`)
* To generate a flexbox layout you can do;


```html
<div class="column top">...</div>
```

this is the equivalent of:

```css
.my-custom-class {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
```

In summary, for vertical alignment we use `top`, `middle`, `bottom` and for horizontal alignment: `start`, `center`, `end`.

## About

This project is maintained by [Braian Dickson](https://github.com/braiandickson) & [Francisco Iglesias](https://github.com/frankiglesias) and it was written by [Wolox](http://www.wolox.com.ar).

![Wolox](https://raw.githubusercontent.com/Wolox/press-kit/master/logos/logo_banner.png)
