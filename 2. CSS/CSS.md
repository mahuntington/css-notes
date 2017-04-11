# CSS - An Introduction

## Lesson Objectives

1. Define CSS and describe its use
1. Diagram the structure of CSS
1. Demonstrate how to apply rules to a specific tag
1. List some common element properties that can be styled
1. Describe ids and classes. Explain when should we use which.
1. Describe "The Cascade"
1. Describe how to combine various selectors
1. Describe Specificity

## Define CSS and describe its use

HTML gives our site function, but it doesn't do much in terms of how the site looks.  This is where CSS comes in

1. Cascading - We'll Define shortly
1. Style - making things pretty!
1. Sheets - it's just a sheet of text, not a program we write

## Diagram the structure of CSS

A CSS file is composed of many rules.  Each rule governs the appearance of certain elements.  A generalized form looks like:

```CSS
selector {
	property:value;
	property:value;
	property:value;
}
```

 Everything inside the curly braces is called the "declaration block"

## Demonstrate how to apply rules to a specific tag

If you wanted to style all the `<p>` tags of a page, you could style it by writing:

```CSS
p {
	property:value;
	property:value;
	property:value;
}
```

## List some common element properties that can be styled

Here are some properties that you can set for an element

1. color
	- names
		- blue, red, yellow, white, grey, black, green, orange, purple
		- http://www.crockford.com/wrrrld/color.html
	- value
		- hexidecimal number (0-F), six places
			- #0088FF
		- https://color.adobe.com
1. background
	- color
	- url()
1. font-size
	- measured in px (for now)
1. font-family
	- System fonts
		- Single word fonts
			- Arial, Courier, Times, etc
		- Multi word fonts must be placed in quotes
			- "Times New Roman", "Arial Black", "Lucinda Console"
		- Use http://www.cssfontstack.com/ to see what fonts are available on what operating systems
	- Generic fonts
		- serif, sans-serif, cursive, fantasy, monospace.
	- can have several font families as a value
		- starts with first and goes down the line until it finds one it has
1. font-weight
	- normal, bold
1. text-align
	- left, right, center

## Describe ids and classes. Explain when should we use which.

Sometimes just targeting an element is not enough.  We can target other attributes of elements in our selectors.

1. ids
	- `<div id="left-column"></div>`
	- `#left-column {}`
	- each id on a page must be unique
	- great for locations on a page that occur only once
		- e.g. left column, contact form, etc
1. classes
	- `<div class="large-module"></div>`
	- `.large-module {}`
	- each class on a page do not have to be unique
	- great for repeatable ideas
		- module
			- e.g. ad unit, comment block, etc
		- function
			- e.g. active, important,etc

## Describe "The Cascade"

Some properties of elements are passed down to their children. In general:

1. Properties dealing with text are inherited by their children
1. Properties dealing with spacing are not inherited by their children
1. https://www.w3.org/TR/CSS2/propidx.html

## Describe how to combine various selectors

Selectors can be more complex than just an element, id, or class.

1. You can have a set of rules affect multiple sections by listing them
	- `p, #left-column {}`
		- will style all `<p>` tags and whichever tag has and id of "left-column"
1. You can combine attributes (i.e. tag, class, id) to narrow down how many elements are effected
	- `a.important {}`
		- styles all anchor tags that also have an "important" class
			- `<a class="important"></a>`
	- `#left-column.visible {}`
		- styles whichever tag that has the id of "left-column", but only when it also has a class of "visble"
			- styled: `<div id="left-column" class="visible"></div>`
			- not-styled: `<div id="left-column"></div>`
	- `.profile.minimized {}`
		- styles all tags that have two classes (separated by a space): "profile" and "minimized"
		- `<div class="profile minimized"></div>`
	- `div#left-column {}`
		- you could combine tags and ids, but there's only ever going to be one tag with an id of "left-column"
		- it's not like you would have a group of tags with the same id, from which you want to select only those that are `div` tags
		- might as well just write `#left-column {}` and leave out the div
1. You can filter out tags based on their ancestors
	- `main p {}`
		- will style all `<p>` tags that are descendants of `<main>` tags
		```html
		<main>
			<p></p>
		</main>
		```
		```html
		<main>
			<section>
				<p></p>
			</section>
		</main>
		```

## Describe Specificity

When an element is being styled by two rules at the same time, the browser calculates which rule is more specific and applies that rule.  To do this it looks at the selector.  If both rules have the same specificity, the last rule is applied.

1. Count the number of ids in each rule's selector.
	- Apply whichever rule has more ids in its selector
	- In theory there should only be one or zero ids in each selector
		- `#left-column #comments`
			- do not need to filter by ancestor
			- can just write `#comments`
1. If the number of ids in each rule's selector is the same, count the number of classes
	- Apply whichever rule has more classes in its selector
1. If the number of ids and classes in each rule's selector is the same, count the number of tags
	- Apply whichever rule has more tags in its selector
