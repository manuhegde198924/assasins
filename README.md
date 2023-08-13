# assasins
hosted link:https://manuhegde198924.github.io/assasins/


The flex container properties are:

    flex-direction
    flex-wrap
    flex-flow
    justify-content
    align-items
    align-content

	
Shark Coder
Shark Coder
Tools
HTML
Layout
Typography
Images
Visual
Blocks

Tools

HTML

Layout

    CSS Flexbox: A Complete Guide
    CSS Grid Tutorial
    Bootstrap Grid Tutorial

Typography

Images

Visual

Blocks

Data Visualization
Popular Tags
visualization pandas matplotlib jupyter seaborn JS blocks buttons
CSS Flexbox: A Complete Guide

This guide explains everything about flexbox, focusing on different properties for the flex container (the parent element) and the flex items (the child elements). It includes various examples and lifehacks.
CSS Flexbox: A Complete Guide
Contents

CSS flexbox (Flexible Box Layout Module) is a layout module that consists of the flex container (the parent element) and the flex items (the children elements). The flex items can be organized as a row or as a column, and the available free space can be distributed between them in various ways.
Flex container and flex items

            
<div class="container">
    <div class="item">
        <p>Item1</p>
    </div>
    <div class="item">
        <p>Item2</p>
    </div>
    <div class="item">
        <p>Item3</p>
    </div>
    <div class="item">
        <p>Item4</p>
    </div>
</div>

    

With the help of flexbox you can:

    Automatically scale elements (alter height or width) so that they fill the available space
    Automatically shrink or grow elements to make them fit into the container and prevent overflow
    Change the order of the items
    Solve the problem of horizontal and vertical centering
    Create columns of the same height
    Create a footer sticking to the bottom of the page
    Design navigation panels
    And more

Flexbox layout is intended for small-scale layouts, while the Grid layout is most appropriate to larger scale layouts.

Flexbox elements can have many properties some of which are set on the flex container and the others are set on the flex items.

Properties that apply to the flex container:

    align-content
    align-items
    display
    flex-direction
    flex-flow
    flex-wrap
    justify-content

Properties that apply to the flex items:

    align-self
    flex
    flex-basis
    flex-grow
    flex-shrink
    order

How to Create the Flex Container

The display: flex; property applies to the container, makes the container a block element, and enables the flex layout for all its direct children.

            
.container {
  display: flex; 
}
    

The display: inline-flex; works in the same way. Only it creates a container as an inline element.

            
.container {
  display: inline-flex; 
}
    

Note that some properties do not work when applied to the flex items, namely clear, float, and vertical-align. And pseudoelements such as ::first-letter and ::first-line has no effect on a flex container. Also, an absolutely-positioned flex item does not participate in flex layout.

Don’t use percentage paddings or margins in a flex container as older browser behavior will vary.
How to Create a Row or Column

If you want to arrange the flex items to look like a row or a column, apply the flex-direction property to the container.

The flex-direction: row; property will make a horizontal row. The row is the default value.

            
.container {
  flex-direction: row; 
}
    

flex-direction: row

If you have more items that can fit in one row and you still want a horizontal layout, the flex-wrap: wrap; property will come in handy. This way, the flex items will wrap onto multiple lines inside the flex container. The default value is flex-wrap: nowrap;.

            
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
    

flex-wrap: wrap

To make a vertical column, apply the flex-direction: column; to the container.

            
.container {
  flex-direction: column; 
}
    

flex-direction: column

There’s a shorthand for the flex-direction and flex-wrap properties — flex-flow. The default value is row nowrap.

            
.container {
  flex-flow: row wrap; // flex-direction + flex-wrap
}
    

How to Align Elements Horizontally

To define the horizontal alignment of items, use the justify-content property. It may have one of the following values:

    flex-start: items are packed toward the container’s left side (it’s the default value)
    flex-end: items are packed toward the container’s right side
    center: items are placed in the center
    space-between: items are evenly distributed in the line (the first item is on the left, the last item on the right)
    space-around: items are evenly distributed in the line with equal space on both sides of the items. Note that visually the spaces aren’t equal since all the items have equal space on both sides. The margins of adjacent flex items do not collapse. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies
    space-evenly: items are distributed so that the spacing between any two items (and the space to the edges) is equal

            
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
    

justify-content&nbsp;

You can use auto-margins to divide flex items in the same container. Auto-margins eat up all the extra space in a flex container. For example, to move an item to the right side of the container, apply to it the margin-left: auto; property. However, if free space is distributed to auto-margins, the alignment properties will have no effect.
How to Align Elements Vertically

To align flex items vertically, use the align-items, align-content or align-self properties.
Align-items

To define the vertical alignment of several items, apply the align-items property to the container. This property may have one of the following values:

    stretch: items are stretched to fill the container, still respecting min-width and max-width properties (it’s the default value)
    flex-start: items are placed in the top part of the container
    flex-end: items are placed in the bottom part of the container
    center: items are centered in the middle of the container
    baseline: items are aligned such as their baselines align

            
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
    

align-items&nbsp;
Align-content

To define the vertical alignment of several lines of items, use the align-content property. This property has no effect when there is only one line of flex items.

This property only works if two conditions are met:

    The wrap value should be applied to the flex container
    The flex container should be higher than the lines of the flex items

In other words, there must be additional vertical space inside the container, which should be larger than the sum of all the heights of the rows of elements.

This property may have one of the following values:

    stretch: lines stretch to take up all the available space in the container (it’s the default value)
    flex-start: lines are placed in the top part of the container
    flex-end: lines are placed in the bottom part of the container
    center: lines are centered in the middle of the container
    space-between: lines are evenly distributed in the container
    space-around: lines are evenly distributed with equal space around each line

            
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
    

align-content&nbsp;
Align-self

To vertically align individual items, use the align-self property.  It applies to the flex items, not to the flex container. It is useful to override the alignment specified for the flex container with the help of the align-items property.

The align-self property may have one of the following values (the same ones as in the case of the align-items property plus auto):

    auto: equals to the value specified in the align-items property for the flex container (it’s the default value)
    stretch: items are stretched to fill the container, still respecting min-width and max-width properties
    flex-start: items are placed in the top part of the container
    flex-end: items are placed in the bottom part of the container
    center: items are centered in the middle of the container
    baseline: items are aligned such as their baselines align

            
.item {
  align-self: auto | stretch | flex-start | flex-end | center | baseline;
}
    

align-self
How to Change the Order of the Elements

Several properties allow determining the order of the flex items: order, row-reverse, column-reverse, wrap-reverse.
Order

To customize the order of individual flex items, use the order property. It applies to the flex items.

By default, all flex items have the order: 0; value. If you specify the value -1 for an element, it moves toward the start of the line, and the value 1 places it in the end. If multiple flex items have the same order value, they will be displayed according to the original order.

            
.item {
  order: <integer>; 
}
    

The default order:
Flex order

To make the last item first:

            
.item5 {
  order: -1;
}
    

Flex order

To change the order of individual items:

            
.item1 { order: 4; }
.item2 { order: 3; }
.item3 { order: 1; }
.item4 { order: 5; }
.item5 { order: 2; }
    

Flex order
Row-reverse, column-reverse

You can reverse the item order. To arrange flex items in a row right to left, apply the flex-direction: row-reverse; property to the flex container.

            
.container {
  flex-direction: row-reverse;
}
    

<span id="docs-internal-guid-dcc6e8d3-7fff-0a63-9894-7f67e298b4c3"><span style="font-size: 11pt; font-family: &quot;Courier New&quot;; color: rgb(0, 0, 0); background-color: transparent; font-variant-numeric: normal; font-variant-east-asian: normal; vertical-align: baseline; white-space: pre-wrap;">flex-direction: row-reverse</span></span>

To arrange flex items in a column bottom to top, use the flex-direction: column-reverse; property.

            
.container {
  flex-direction: column-reverse;
}
    

flex-direction: column-reverse

Instead of flex-direction, you can choose the shorter flex-flow property to apply those values:

            
.container {
  flex-flow: row-reverse wrap;
}

.container {
  flex-flow: column-reverse nowrap;
}
    

Wrap-reverse

There is also the flex-wrap: wrap-reverse; property that allows wrapping flex items onto multiple lines from bottom to top.

            
.container {
  flex-wrap: wrap-reverse;
}
    

flex-wrap: wrap-reverse
How to Make the Elements Grow or Shrink

The flexibility of flex items is determined by the flex-basis, flex-grow, and flex-shrink properties.
Flex-basis

The flex-basis property defines the default size of the flex item before the available space is distributed. You can set an absolute value (e. g. 200px or 10em), a percentage value (e. g. 50%) or a keyword (auto, content).

            
.item {
  flex-basis: <length> | auto | content; 
}
    

The flex-basis property can be interpreted as the minimum width of the flex item. If you specify a flex-basis value, it will set the width for the specific item, but depending on other flex parameters the flex item may become wider (or narrower) than the flex-basis value.

The default value is auto. It retrieves the value of the width property. And the content value is based on the flex item’s content.

If you do not set a ﬂex-basis value and set the flex-grow value to 0, the element will be compressed to its minimum size.
Flex-grow

The flex-grow property applies to individual flex items and defines the ability of a flex item to grow. It dictates what amount of the available space inside the flex container the item should take up. It accepts a unitless value that serves as a proportion. The default value is 0. Negative numbers are invalid.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If the flex-grow value of an item is set to 2, it will get 2 times more pixels to the original width than other items with the flex-grow value 1.

            
.item1 { flex-grow: 1; }
.item2 { flex-grow: 1; }
.item3 { flex-grow: 2; }
    

flex-grow
Flex-shrink

The flex-shrink property applies to the flex items and indicates how much each element will be reduced if there is not enough available space. It accepts a unitless value that serves as a proportion. The default value is 1. The value 0 allows keeping the item’s original size. Negative numbers are invalid.

            
.container { width: 700px; padding: 20px; }

.item1 { flex-basis: 150px; flex-shrink: 1; } // actual width: 133.5px
.item2 { flex-basis: 250px; flex-shrink: 2; } // actual width: 204px
.item3 { flex-basis: 350px; flex-shrink: 3; } // actual width: 316.5px
    

flex-shrink

The flex-shrink property won’t work if the flex container has the flex-wrap: wrap; property.
Flex

The flex property is the shorthand for flex-grow, flex-shrink, and flex-basis combined. The second and third parameters (flex-shrink and flex-basis) are optional.

It may have several values:

    flex-grow flex-shrink flex-basis: values of the three properties combined
    none: same as 0 0 auto (makes the flex items fully inflexible)
    initial: same as 0 1 auto (the default value; it is based on the width and height properties)
    auto: same as 1 1 auto (it is based on the width and height properties, but makes the flex items fully flexible)
    <positive number>: same as <positive number> 1 0 (makes the flex item flexible and sets the flex basis to zero)

You can make one item flexible by applying the flex: 1; property and make other ones static by applying flex: initial; width: 300px; (or another value for the fixed width).

For example, flex: 1 1 300px; is identical to the code below:

            
flex-grow: 1;
flex-shrink: 1;
flex-basis: 300px;
    

And flex: 1; is identical to the code below:

            
flex-grow: 1;
flex-shrink: 1;
flex-basis: 0%;
    

In the example above, the width of a flex item will not be defined by its content but by the flex-grow property.

You can use the flexbox layout to make the footer stick to the bottom of the page. See the code below.

            
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
}
    

Checklist

    Create a flex container (e. g. div .container) and put flex items inside (e. g. div .item).
    Apply display: flex; to the container.
    Set flex-flow: row wrap; or flex-flow: column nowrap; for the .container.
    To determine the horizontal alignment, use the justify-content property (flex-start, center, flex-end, space-around, space-between).
    To determine the vertical alignment, use the align-items property (flex-start, center, flex-end, stretch, baseline). To align individual items vertically, use align-self (flex-start, center, flex-end, stretch, baseline).
    To change the order of the flex items, apply the order property or flex-direction: row-reverse; or flex-direction: column-reverse;.
    To make one element wider than the other one inside the container (for example, to make it twice as wide), apply flex: 2; to one element and flex: 1; to the others.

flex footer navigation columns layout
Please share this article:
About Me Contact Me Support the Project

html parrt<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assasins</title>
    <link rel="stylesheet" href="styles.css"/>
</head>
<body>
    <main>
        <section class="glass">
            <div class="dashboard">
                <div class="user">
                    <img src="https://media.licdn.com/dms/image/C4E03AQFR4LKNI52x3w/profile-displayphoto-shrink_400_400/0/1516820009180?e=1697673600&v=beta&t=vYM4iFAS4c39yYShD48GlnK40x2u2SVo2Nu91MY7vis" width="45"height="45">
                    <h4>MaNU-HEgdE</h4>
                    <p>Pro Member</p>
                </div>
                <div class="links">
                    <div class="link">
                        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTymkQD44guoVKXYpydfNWIFfoUk0nXes__kNl22CAF5w&s" width="40" height="40"/>
                        <h4>Streams</h4>
                    </div>
                    <div class="links">
                        <div class="link">
                            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRCFtcb7JgdXT7BJgfDMzx3vHHopz3kYob2zeZIatut2Q&s"width="40" height="40"/>
                            <h4>Games</h4>
                        </div>
                        <div class="links">
                            <div class="link">
                                <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKUAAAClCAMAAAAK9c3oAAAAYFBMVEX///8AAAD8/PyUlJRqamrs7OyAgID09PSXl5e4uLiRkZH4+PhiYmLY2NiioqImJiYaGhosLCzm5uZKSkpycnLf39/CwsJDQ0OwsLBbW1vNzc0fHx9UVFQSEhKqqqpPT0/O0XrrAAAClUlEQVR4nO2cbXeCIBiGRTPN1+zF3Nbq///LLXeWUCasbiTXfX3Gh8sHEOFw8DxCCCGEENKL7xJDxXwRB+6IF7mBaFSUwi1lEWkzWTh2PFHospm7zuSJMtdYLlwbtiw0DR67FmyJh5vcD1wLtgS0hPHfLKtsNi5ZdYdllofjkmd3WM7CwZJ4whktUdASBy1x0BIHLXHQEgctcdASBy1x0BIHLXHQEgctcdASBy1x0BIHLXHQEgctcdiyjMIwNRL4Lqg9P2DJMmzeluWm1p+y8OtZ+fnW6DytWEabn3KJ1jL5KbjRaFqxTH4LxhrJc0jN+9iw9EUXc7Bg0hUc3/K9q1wkt4OmkqQYPjRiw7KWar8d1ZclxfvolqFc/c0up0iK4eFjZfQcFYH+vqmeXNgPB7Riuf3QZVNtblFu7Vv60QVpXSkSyeU0lKqSVZ1ehlBdHrdcNcH8irVicZVNVVKsrwMEzQppme+FAapmon/gu6tKH6dHLcOdSY1CHKRIhmcPd1ItD1rOzWoU664Bt4YvJuYoyzTrC9/Dsjvr1ywNn8nOg+5By5VRrzzRNfnB9JH9Of8vkctp9Mu7xrhhk++6uX2k76U6l4/+vZzI3OMZzOOB+3m8B/0/0UU2P0b4J7pCbe/+JZr6f3kc33Ia/+qG6x4lm+OvewzXkL7bNaQnZXKwnJTN4YBu9zZiw4IvvE/U7rlVZntum3LpaM/N+8P+Zepu/xINLXHQEgctcdASBy1x0BIHLXHQEgctcdASBy1x0BIHLXHQEgctcdASBy1x0BIHLXHcZTmN+4mmcdeTS2iJ439YTuKewWnc2fgc919Wuvsvn+Iu0YP2/EJUVPowVqkO+nMJ07jjthV9/vuCCSGEEEJejy9MT0GarN8/6QAAAABJRU5ErkJggg=="width="40" height="40"/>
                                <h4>New</h4>
                            </div>
                            <div class="links">
                                <div class="link">
                                    <img src="data:image/jpeg;base64,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"width="40" height="40"/>
                                    <h4>Library</h4>
                                </div>
                </div>
                <div class="pro">
                    <h3>Join pro for free games</h3>
                    <img src="data:image/jpeg;base64,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" width="55"height="55"/>
                </div>
            </div>
            <div class="games">
                <div class="status">
                    <h1>Active Games</h1>
                    <input type="text"/>
                    <div class="cards">
                        <div class="card1">
                            <img src="data:image/jpeg;base64,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"width="40"height="40/>
                            <div class="card-inf">
                                <h2>Assains creed wallaha</h2>
                                <p>ps5 version</p>
                                <div class="progress"></div>
                            </div>
                            <h2 class="percentage">60%</h2>
                        </div>
                        <div class="card2">
                            <img src="data:image/jpeg;base64,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"width="40"height="40/>
                            <div class="card-inf">
                                <h2>Assains creed wallaha</h2>
                                <p>ps5 version</p>
                                <div class="progress"></div>
                            </div>
                            <h2 class="percentage">66%</h2>
                        </div>
                        <div class="card3">
                            <img src="data:image/jpeg;base64,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"width="40"height="40"/>
                            <div class="card-inf">
                                <h2>Assains creed wallaha</h2>
                                <p>ps5 version</p>
                                <div class="progress"></div>
                            </div>
                            <h2 class="percentage">70%</h2>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>
    <div class="circle1"></div>
    <div class="circle2"></div>
</body>
</html>

