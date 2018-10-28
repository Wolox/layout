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

2. Import the `wolox-bootstrap.scss` to have margins, and layout all toghether. Or you can import them separately if needed.

```scss
@import '~wolox-bootstrap/wolox-bootstrap';
 // or
@import '~wolox-bootstrap/layout';
@import '~wolox-bootstrap/separations';
```

## Usage

### General import of Wolox-boostrap

This will generate a series of classes like:
```scss
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
### Layout API interface
To generate a flexbox layout you can do:
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

| Column  | Class name  |
| :------------ |:---------------:|
| `align-items: center`      | `column center` |
| `align-items: flex-end`      | `column end` |
| `align-items: flex-start`      | `column start` |
| `justify-content: center`      | `column middle` |
| `justify-content: flex-end`      | `column bottom` |
| `justify-content: flex-start`      | `column top` |
| `justify-content: space-between`      | `column space-between` |
| `justify-content: space-around`      | `column space-around` |


| Row  | Class name  |
| :------------ |:---------------:|
| `align-items: center`      | `row middle` |
| `align-items: flex-end`      | `row bottom` |
| `align-items: flex-start`      | `row top` |
| `justify-content: center`      | `row center` |
| `justify-content: flex-end`      | `row end` |
| `justify-content: flex-start`      | `row start` |
| `justify-content: space-between`      | `row space-between` |
| `justify-content: space-around`      | `row space-around` |

For responsive classes (with 960px as breakpoint) append `-sm` suffix to the class.


```html
<div class="row space-between space-around-sm">
  ...
</div>
```
### Margins and Paddings generator
In case of including only the separation file the way to create this custom classes is
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
