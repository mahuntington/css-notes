# jQuery UI

## Lesson Objectives

1. Describe what jQuery UI is and what makes it unique
1. Install jQuery UI
1. Use some common interactions
1. Use some common widgets
1. Use some common effects

## Describe what jQuery UI is

jQuery UI is an extension if jQuery.  Here's how they differ:

1. jQuery is primarily meant for low level DOM manipulation
1. jQuery UI is a set of components, very much like Foundation

Here's how jQuery differs from Foundation:

1. jQuery UI focuses more on functionality, whereas Foundation is mostly visual
1. jQuery UI's components are easily customizable, so that you can perform unique tasks with them
1. Foundation's components are mostly copy/paste

## Install jQuery UI

Using it is as easy as adding script tags referencing the proper CDNs

```html
<head>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
</head>
```

Note that jQuery requires jQuery as a dependency.

[The docs](http://jqueryui.com/demos/) for jQuery UI have great sample code.  Check out all the possibilities!

## Use some common interactions

An interaction, is just an ability the user has with a certain DOM element.  jQuery UI just adds some extra functions onto the standard jQuery object, so creating these interactions is easy:

Draggable:

```html
<!doctype html>
<html lang="en">
<head>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <style>
        #draggable { width: 150px; height: 150px; padding: 0.5em; border:1px solid black; }
    </style>
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
        $( function() {
            $( "#draggable" ).draggable();
        } );
    </script>
</head>
<body>
    <div id="draggable">
        Drag me around
    </div>
</body>
</html>
```

Droppable:

```html
<!doctype html>
<html lang="en">
<head>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <style>
        #draggable { border: 1px solid black; width: 100px; height: 100px; padding: 0.5em; float: left; margin: 10px 10px 10px 0; }
        #droppable { border: 1px solid black; width: 150px; height: 150px; padding: 0.5em; float: left; margin: 10px; }
        .highlight { background: yellow; }
    </style>
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
        $( function() {
            $( "#draggable" ).draggable();
            $( "#droppable" ).droppable({
                drop: function( event, ui ) {
                    $( this )
                    .addClass( "highlight" )
                    .html( "Dropped!" );
                }
            });
        } );
    </script>
</head>
<body>

    <div id="draggable">
        Drag me to my target
    </div>

    <div id="droppable">
        Drop here
    </div>


</body>
</html>
```

## Use some common widgets

Widgets are more fleshed out components, containing multiple elements, that have more complex interactions with each other:

Accordion:

```html
<!doctype html>
<html lang="en">
<head>
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <style>
        #accordion h3, #accordion div {
            border:1px solid black;
            margin:0;
        }
    </style>
    <script>
    $( function() {
        $( "#accordion" ).accordion();
    } );
    </script>
</head>
<body>

    <div id="accordion">
        <h3>Section 1</h3>
        <div>
            <p>
                Mauris mauris ante, blandit et, ultrices a, suscipit eget, quam. Integer
                ut neque. Vivamus nisi metus, molestie vel, gravida in, condimentum sit
                amet, nunc. Nam a nibh. Donec suscipit eros. Nam mi. Proin viverra leo ut
                odio. Curabitur malesuada. Vestibulum a velit eu ante scelerisque vulputate.
            </p>
        </div>
        <h3>Section 2</h3>
        <div>
            <p>
                Sed non urna. Donec et ante. Phasellus eu ligula. Vestibulum sit amet
                purus. Vivamus hendrerit, dolor at aliquet laoreet, mauris turpis porttitor
                velit, faucibus interdum tellus libero ac justo. Vivamus non quam. In
                suscipit faucibus urna.
            </p>
        </div>
        <h3>Section 3</h3>
        <div>
            <p>
                Nam enim risus, molestie et, porta ac, aliquam ac, risus. Quisque lobortis.
                Phasellus pellentesque purus in massa. Aenean in pede. Phasellus ac libero
                ac tellus pellentesque semper. Sed ac felis. Sed commodo, magna quis
                lacinia ornare, quam ante aliquam nisi, eu iaculis leo purus venenatis dui.
            </p>
            <ul>
                <li>List item one</li>
                <li>List item two</li>
                <li>List item three</li>
            </ul>
        </div>
        <h3>Section 4</h3>
        <div>
            <p>
                Cras dictum. Pellentesque habitant morbi tristique senectus et netus
                et malesuada fames ac turpis egestas. Vestibulum ante ipsum primis in
                faucibus orci luctus et ultrices posuere cubilia Curae; Aenean lacinia
                mauris vel est.
            </p>
            <p>
                Suspendisse eu nisl. Nullam ut libero. Integer dignissim consequat lectus.
                Class aptent taciti sociosqu ad litora torquent per conubia nostra, per
                inceptos himenaeos.
            </p>
        </div>
    </div>


</body>
</html>
```

## Use some common effects

jQuery UI has some fun visual effects you can run on DOM elements:

Bounce

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title></title>
        <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
        <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
        <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
        <script type="text/javascript">
            $(function(){
                $('h1').click(function(){
                    $(this).effect('bounce')
                });
            })
        </script>
    </head>
    <body>
        <h1>Click me</h1>
    </body>
</html>
```
