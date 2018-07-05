# Wolox Layout

[![circle-ci](https://img.shields.io/circleci/project/github/Wolox/wolox-layout.svg)](https://circleci.com/gh/Wolox/wolox-layout)
[![npm](https://img.shields.io/npm/v/wolox-layout.svg)](https://www.npmjs.com/package/wolox-layout)

[![FEArmy](./assets/FEA_icon.png)](https://github.com/orgs/Wolox/teams/front-end-army/members)

## Features

* `separations.scss` file contains all the margin and padding class generators for your own stylesheet.
* `layout.scss` contains a series of classes that can be used to define a page's layout using flexbox.

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

2- Include the wolox-bootstrap.scss before the index file of your CSS/SCSS to have paddings, margins, and layout already generated all toghether. Or you can import them separately.

If you want to import the 'wolox-bootstrap' in this way:

```scss
@import '~wolox-bootstrap/wolox-bootstrap';
 // or
@import '~wolox-bootstrap/layout';
@import '~wolox-bootstrap/separations';
```

## Usage

If you import the `wolox-boostrap` file:

* Will generate a series of classes like:
```sass
.m-0 { margin: 0; }
.m-1 { margin: 10px; }
...
.m-20 { margin: 200px; }

.m-top-0 { margin: 0; }
.m-top-1 { margin: 10px; }
...
.m-top-20 { margin: 200px; }

@media (max-width: 960px) {
.p-top-0-sm { padding: 0; }
.p-top-1-sm { padding: 10px; }
...
.p-top-20-sm { padding: 200px; }
}

// And so on for every type of margin and padding from 0 to 200px.

```

* To generate a flexbox layout you can do;
```html
<div class="column middle">...</div>

<!-- this is the equivalent to: -->
```
```scss
.my-custom-class {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
```

In summary, for vertical alignment we use `top`, `middle`, `bottom` and for horizontal alignment: `start`, `center`, `end`.

In case of including only the separation file the way to create this custom classes is:

```scss
@include generate-layout(property, orientation, max-value, min-value, scale, suffix, breakpoint);
```

For example:
```scss
@include generate-layout('margin','top', 1000, 0, 10, 'sm', 960);

// Will generate

@media (max-width: 960px) {
.m-top-0-sm { margin: 0; }
.m-top-1-sm { margin: 10px; }
...
.m-top-100-sm { margin: 1000px; }
}
```

If you don't give a suffix and breakpoint will generate classes without media query

```scss
@include generate-layout('margin','top', 1000, 0, 10);

// Will generate
.m-top-0 { margin: 0; }
.m-top-1 { margin: 10px; }
...
.m-top-100 { margin: 1000px; }
```
## About

This project is maintained by [Braian Dickson](https://github.com/braiandickson) & [Francisco Iglesias](https://github.com/frankiglesias) and it was written by [Wolox](http://www.wolox.com.ar).

![Wolox](https://raw.githubusercontent.com/Wolox/press-kit/master/logos/logo_banner.png)
