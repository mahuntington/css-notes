# HTML - Tags, Content, Attributes, & Semantic HTML

## Lesson Objectives

1. Describe what HTML is
1. Describe what a tag is
1. Describe what the content of a tag is
1. List some common tags
1. Describe what the attributes of a tag do
1. List some common tags that have attributes
1. Describe what Semantic HTML means

## Describe what HTML is

HTML stands for Hyper Text Markup Language.  It's a way to give structural meaning to text.  It allows computers and programmers to easily determine what the purpose of a chunk of text does.

## Describe what a tag is

HTML creates this meaning by surrounding text with tags.  Tags look like this: `<example-tag></example-tag>`.  Note that there is an opening and a closing part of the tag.  We call these "opening" and "closing" tags.

## Describe what the content of a tag is

Between the opening and closing tags, we insert the text or "content" of the tag.  The final result would look like this: `<example-tag>Content Goes in here</example-tag>`.  Tags can also be placed within other tags:

```html
<outer-tag>
  <inner-tag></inner-tag>
</outer-tag>
```

Note that when placing a tag inside another tag, you should indent the new tag to show it is a child of its parent tag.

## List some common tags

In general, we don't create our own tags.  Instead there are a set of predefined tags with functionality already associated with them.

### Initializing a page

Every site should start with:

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

1. The DOCTYPE tag is special and doesn't get closed.  It also is the only tag that can have non-alpha-numeric (letters/numbers) values in it.
1. html: shows where the html begins
1. head: contains content specifically for the browser, not the user, to see.
1. body: contains all the content that the user will see when viewing the html in a web browser like Chrome, Firefox, etc.

### basic tags

1. h1, h2, h3, h4, h5, h6

  - These are headers.  Imagine you're giving a lecture and you want to have an outline.  These will help a computer/programmer figure out what are the title, sub sections, sub-sub sections, etc. of your outline.
  - The lower the number, the more important the header is.  h1 tags are generally the title of the page.  h2 denote a section, and so on.

1. p

  - These are paragraphs

### specific structure

Of course a website is more than just headers and paragraphs, though.  It has many sections to it that a normal outline doesn't.  Here are some of the more common tags we use to give structure to the page

1. header

  - could contain elements like a log and a nav bar.  Perhaps the title of the page too?

1. footer

  - could contain disclaimers, copyrights, and less important links (privacy, terms and conditions, legal, etc).

1. main

  - the bulk of your site goes in here

1. section

  - within some of the tags listed above, there can be different sections.  Use this tag to block each section off

1. nav

  - this will hold navigation links

1. article

  - if you're writing a blog, or have a page with many self contained sections, this might work well

1. aside

  - this is for tangential material.  Sidebars, inserts, etc.

### generic structure

Sometimes we need a tag that doesn't fit into any of the previously defined categories.  If this is the case, we can use one of two generic tags

1. div

  - used to block out chunks of content

1. span

  - use to block out small bits of content (e.g. words, sentences, etc)

### elements

Some elements are not structural, but actually make the content display differently

1. ul/ol/li

  - creates a list, either unordered (ul) or ordered (ol)
  - inside each `ul` or `ol` is a set of `li` list item elements.

1. em

  - this will emphasize a chunk of text, usually making it italics

1. strong

  - this will emphasize a chunk of text, usually making it bold.

### decorative elements

Some elements do not contain content and instead are purely for decoration.  Elements that do not contain content are written like so `<no-content-tag/>`.  Note there is no closing tag and the slash comes before the final `>`

1. hr

  - horizontal rule, `<hr/>` creates a divider

1. br

  - break, `<br/>`, starts a new line in a chunk of text.

## Describe what the attributes of a tag do

We can add more meaning to a tag by adding "attributes" to it.  The looks like `<some-tag my-attribute="attribute-value"><some-tag>` or `<self-closing-tag attribute="value"/>`.  Again, in general, we don't create our own attributes, but instead choose from predefined ones which have specific functionality depending on what tag they're attached to.

## List some common tags that have attributes

1. a

  - Anchor tag.  Creates a clickable link to another page.  Uses the `href` attribute to do so
  - example: `<a href="http://www.google.com">This link will go to Google</a>`
  - note that the actual URL (location) of the page is hidden, and that only the content is shown.

1. img

  - self closing, but contains a `src` attribute with is the URL to an image
  - examle: `<img src="https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png"/>`

1. video

  - like `img` but goes to a video
  - example: `<video src="http://www.w3schools.com/html/mov_bbb.mp4"/>`
  - also has attributes like `autoplay`, `controls`, `loop`

1. audio

  - like `img` and `video`
  - example: `<audio controls="true" src="http://www.w3schools.com/tags/horse.mp3"/>`

## Describe what Semantic HTML means

The most important thing to remember is that these tags and attributes are supposed to give structure and meaning your content, not appearance.  Sometimes you might want the title of the page to be smaller than the titles of the sub sections.  You should still use the tag that conveys the proper meaning, even if it doesn't look right.
