# SASS

## Lesson Objectives

1. Describe what SASS is
1. Install SASS
1. Save values in variables
1. Nest rules inside each other
1. Separate code out into partials
1. Import partials
1. Create a mixin
1. Have rules inherit values
1. Use Operators

## Describe what SASS is

SASS stands for Syntactically Awesome Style Sheets.  It's a transpiler, much like Babel is for ES6.  It takes SASS syntax and turns it into CSS.  It basically adds additional functionality to CSS that isn't available by default.

## Install SASS

You can install as a node package or a ruby gem.  Let's use node:

```
sudo npm install -g sass
```

Now you can use the following to compile the sass file called `index.scss` to `index.css`

```
sass index.scss index.css
```

## Save values in variables

```css
$primary-color: #333;
body {
    color: $primary-color;
}
```

after compiling, you should get:

```css
body {
    color: #333;
}
```

## Nest rules inside each other

You can have nest rules within each other, just like in HTML

```css
nav {
    ul {
        margin:0;
    }
    a {
        display: block;
    }
}
```

This will output:

```css
nav ul {
    margin:0
}
nav a {
    display: block;
}
```

## Separate code out into partials

Partials are just `.scss` files with a leading underscore (`_`).  The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file.

Try it in `_nav.scss`

```css
nav {
    padding: 10px;
}
```

## Import partials

To import a partial:

```css
body {
	font: Arial;
}

@import 'nav';
```

This produces:

```css
body {
  font: Arial;
}

nav {
  padding: 10px;
}
```

## Create a mixin

Mixins are like functions.  They produce rules based on some (or no) parameters:

```css
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

## Have rules inherit values

You can have a set of rules be inherited by a rule:

```css
%box {
    border:1px solid black;
    padding: 10px;
}

.plain-box {
    @extend %box;
    background: grey;
}

.awesome-box{
    @extend %box;
    background: red;
}
```

This produces:

```css
.awesome-box, .plain-box {
  border: 1px solid black;
  padding: 10px;
}

.plain-box {
  background: grey;
}

.awesome-box {
  background: red;
}
```

## Use Operators

You can use all your usual math operators (`+-*/%`) in sass:

```css
article{
  width: 600px / 960px * 100%;
}

aside{
  width: 300px / 960px * 100%;
}
```

This will produce:

```css
article {
  width: 62.5%;
}

aside {
  width: 31.25%;
}
```
