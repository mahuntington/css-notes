# Foundation

## Lesson Objectives

1. Describe what Foundation is
1. Download Foundation
1. Use some common Foundation elements
1. Build Foundation using the CLI

## Describe what Foundation is

Foundation is a front-end framework, much like Bootstrap, that aims to give you some bass styling and functionality for common elements you'll use

## Download Foundation

To download it:

1. Go to https://foundation.zurb.com/ and click the "Download Foundation" button
1. You'll be taken to another page where you can select different versions of the framework
1. Choose "Download Everything"
1. Unzip the file downloaded
1. Open the `foundation-X.X.X-complete` dir in your code editor

## Use some common Foundation elements

Inside your downloaded directory, you'll see an index.html file which provides you lots of good examples for components you might want to use.  Most notably:

### Buttons

```html
<a href="#" class="button">Simple Button</a>
<a href="#" class="success button">Success Btn</a>
<a href="#" class="alert button">Alert Btn</a>
<a href="#" class="secondary button">Secondary Btn</a>
```

### A Grid System

Grid systems are great for laying out a site.  Most sites adhere to a 12 vertical grid system, where the page is visually divided into 12 vertical columns (each with a gutter, or margin, between them):

![](https://monikagarciaprado.files.wordpress.com/2015/01/columns-grid-web-design.png)

Each visual element can take up somewhere between 1 and 12 of these columns.  This make spacing uniform across the page, and brings a sense of cohesion to the visual design.

```html
<div class="grid-x grid-padding-x">
    <div class="large-12 cell">
        <div class="primary callout">
            <p><strong>This is a twelve cell section in a grid-x.</strong> Each of these includes a div.callout element so you can see where the cell are - it's not required at all for the grid.</p>
        </div>
    </div>
</div>
<div class="grid-x grid-padding-x">
    <div class="large-6 medium-6 cell">
        <div class="primary callout">
            <p>Six cell</p>
        </div>
    </div>
    <div class="large-6 medium-6 cell">
        <div class="primary callout">
            <p>Six cell</p>
        </div>
    </div>
</div>
<div class="grid-x grid-padding-x">
    <div class="large-4 medium-4 small-4 cell">
        <div class="primary callout">
            <p>Four cell</p>
        </div>
    </div>
    <div class="large-4 medium-4 small-4 cell">
        <div class="primary callout">
            <p>Four cell</p>
        </div>
    </div>
    <div class="large-4 medium-4 small-4 cell">
        <div class="primary callout">
            <p>Four cell</p>
        </div>
    </div>
</div>
```

**Note** that when declaring a cell, you can specify how many columns an element will take up at smaller sized screens:

```html
<div class="large-4 medium-4 small-4 cell">
    <div class="primary callout">
        <p>Four cell</p>
    </div>
</div>
```

The above example takes up 4 columns in large screens, 4 columns in medium screens, and 4 columns in small screens.

If you omit these classes, on the screen sizes, omitted, the cell will default to 12 columns.

### Callouts

Box off a section:

```html
<div class="callout">
    <h5>So many components, girl!</h5>
    <p>A whole kitchen sink of goodies comes with Foundation. Check out the docs to see them all, along with details on making them your own.</p>
    <a href="http://foundation.zurb.com/sites/docs/" class="small button">Go to Foundation Docs</a>
</div>
```

### Form elements:

Most inputs don't need classes

```html
<input type="text" placeholder="just like normal" />
<select>
    <option value="husker">Husker</option>
    <option value="starbuck">Starbuck</option>
    <option value="hotdog">Hot Dog</option>
    <option value="apollo">Apollo</option>
</select>
<input type="radio"/>
<input type="checkbox"/>
<textarea placeholder="Basic text area"></textarea>
```

You can put inputs together with other elements:

```html
<div class="input-group">
    <input type="text" placeholder="input with element" class="input-group-field" />
    <span class="input-group-label">.com</span>
</div>
```

### BUT WAIT THERE'S MORE!!

Visit [the docs](https://foundation.zurb.com/sites/docs/) for more information.  Zurb has put a lot of effort into making the documentation easy to use, including videos!  Just copy, paste, and modify all you want!

## Build Foundation using the CLI

You also have the option to create a foundation site using source code.  To do this, we'll use an npm packaged called `foundation-sites`

```
sudo npm install --global foundation-cli
```

Now that you have that, you can do to following to create a new site:

```
foundation new
```

After following the prompts, you have a new site generate

1. Open up the directory in your IDE.
1. Open the index.html in your browser
1. In your terminal, run: `npm run start`

This will recompile your css files whenever you make a change.

You can make edits in `scss/_settings.scss`.
