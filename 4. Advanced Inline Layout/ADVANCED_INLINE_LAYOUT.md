# CSS - Advanced Inline Layout

## Lesson Objectives

1. Explain the float property
1. Describe how to use calc

## Explain the float property

Imagine we had an image, and we wanted to have text wrap around it, like in a newspaper.  The float property was originally created to handle exactly this.

### Original use

The `float` property has two values

1. left
1. right

If you want to force text to begin on the line below the floated element (i.e. stop floating), you can use the `clear:left`, `clear:right`, `clear:both`

### Alternative use for layout

You can use `float` to line up `block` elements, one next to another.

#### Issues with this technique

1. All elements in the line must have widths that do not add up to more than their container, or they will wrap.
1. If you have a container with nothing but floated elements for content, the height of the container will be 0, even though the floated elements take up space
	- This is problematic if the container has a background color/image
	- To fix this, you have many options:
		- put an empty div with `clear:both` after all the floated elements
		- add `overflow:auto` to the container
		- many others...

#### Compare this technique with inline-block

Inline-block elements are often preferable to a line of floated block elements, but inline-block elements have a problem too:

If you have inline-block elements next to each other, there is often space between each element.  This is caused by the browser rendering the line breaks between each tag as a single space.

To fix this:
- reformat code so that there is no space between each tag
- Set the `font-size` of the container to be 0 and then reset it for each element
- https://css-tricks.com/fighting-the-space-between-inline-block-elements/

## Describe how to use calc

The `calc` property is used when you want to combine two units of measure together.  This is especially useful when the units of measure are different.

Example:
If you have a fixed width element (e.g. a logo) in line with an element that has a % width
