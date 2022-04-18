# The basics of HTML5 and CSS3

# 5. Tables and Hyperlinks

Hyperlinks have different types of attributes.

If ```target``` is set to ```_blank```, then the link will be opened inside another tab.

If you want to navigate inside your own website ( not on an external one ) with links, you will have to use anchors. That means that you have to use the ```#{id}``` inside the ```href``` attribute of the link so you can navigate to a specific part of the website that has the given id. Example:

```HTML
<a href="#anchor_name_1">Anchor 1</a>
<a href="#anchor_name_2">Anchor 2</a>
<a href="#anchor_name_3">Anchor 3</a>
<a href="#anchor_name_4">Anchor 4</a>
<a href="#anchor_name_5">Anchor 5</a>
<div class="box">
    <h1 id="anchor_name_1">Anchor 1</h1>
</div>
<div class="box">
    <h1 id="anchor_name_2">Anchor 2</h1>
</div>
<div class="box">
    <h1 id="anchor_name_3">Anchor 3</h1>
</div>
<div class="box">
    <h1 id="anchor_name_4">Anchor 4</h1>
</div>
<div class="box">
    <h1 id="anchor_name_5">Anchor 5</h1>
</div>
```

You can also use this anchors to navigate to specific parts of an external website. Example:

```HTML
<a href="https://www.test_website.com/index.html#HEADLINE">Headline of another website</a>
```

# 6. Grafics and Multimedia

### ```<img>```

With ```src``` and ```alt``` you give the source of the file and a text that is read by screenreaders or that appears in case the image can't load.
With ```title``` you can give a title to the image that will show up when the user hovers the mouse over it.

***Images are not technically inserted on the website, they are linked on the HTML document. The ```<img>``` tag represents the space for the image.***

With ```width``` and ```height``` you can adjust the width and the height of the ```<img>``` tag where the image will be put. You should add those attributes since it takes a long time for images to load on websites and if you already have a designated place, with specific width and height attributes, then you will know how much space the ```<img>``` element will occupy. This helps you a lot because, in this way, you can make sure that the rest of the website and its design can be generated without any issues, since the website already knows how much space the ```<img>``` element will occupy.

You can use ```<figure>``` and ```<figcaption>``` in order to describe an image. Example:

```HTML
<figure>
    <img src="img/test.jpg" alt="Test Picture" width="400" height="256" title="Test Picture">
    <figcaption>This is the description of the picture.</figcaption>
</figure>
```

In order to work with html mappings you have to create a map with an id and at it to the usermap attribute inside the image that you want to create a mapping for.

Example:

```HTML
<img src="test.jpg" alt="Toy cars" title="Toy cars" usemap="#my_map">    
<map id="my_map" name="my_map">
    <area target="" alt="Alternative Title" title="Title 1" href="" coords="10,20,30,40,50,60,70,80,90,100" shape="poly">
    <area target="" alt="Alternative Title" title="Title 2" href="" coords="110,120,130,140,150,160,170,180,190,200" shape="poly">
</map>
```

You can see that we first just built a normal image and then added the attribute ```usemap``` to the image with the id of the mapping. Inside the ```map``` we add different areas with their descriptions.

You can use the ```<picture>``` tag in order to insert more images with different resolutions for certain media queries.

```HTML
<picture>
    <source media="(min-width:1024px)" srcset="images/test_1024.jpg">
    <source media="(min-width:640)" srcset="images/test_640.jpg">
    <source media="(min-width:480)" srcset="images/test_480.jpg">
</picture>
```

# 7. HTML Forms

You can add a ```fieldset``` in order to summarize/give a title to a form. You can use it to structure your website better. Example:

```HTML
<fieldset>
    <legend><h2>Input</h2></legend>
    <form>
        <label>Username</label>
        <input type="text" placeholder="Username" required>
        <label>Password</label>
        <input type="password" placeholder="Password" required>
    </form>
</fieldset>
```

A ```datalist``` allows you to give only a couple of options to an ```input```.

```HTML
<form>
    Title <input type="text" list="mylist" name="titel">
    <br>
    <datalist id="mylist">
        <option value="Mr"></option>
        <option value="Mrs"></option>
        <option value="Prof."></option>
    </datalist>
</form>
```

If you want to summarize a block of text and add a drop down menu to it whenever you click on the summarized message, you can use a ```details``` tag:

```HTML
<p>Lorem ipsum dolor sit amet.</p>
<details>
    <summary>Lorem, ipsum.</summary>
    <blockquote>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Provident autem labore reprehenderit et placeat, dicta laborum voluptas, nostrum quidem officia delectus. Voluptatem fuga in similique quaerat repellat cupiditate necessitatibus ut?</blockquote>
</details>
```

## Chapter 8 ( Introduction to CSS )

You can import css files inside your css file using the ```@import``` query.

Example:

```CSS
@import url("header.css");
@import url("paragraph.css");

div{
    background-color: blue;
}
```

# 12. CSS Positioning

## CSS Position 

The ```position``` property sets how an element is positioned inside the document. The properties ```top```, ```right```, ```bottom``` and ```left``` determine the final location of the element.

These are the following value that the ```position```  property can take:

```CSS
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;

/* Global values */
position: inherit;
position: initial;
position: revert;
position: revert-layer;
position: unset;
```

### Values explained:

This is what our html document looks like before changing the position of elements:

![Positioning in markdown](ScreenshotsForNotes/NoPositioningHTML.PNG)

#### ```Static```

***The static value is the default value.*** It means that the element is positioned according to the flow of the document. When an element has the ```static``` position, the properties ```top```, ```right```, ```bottom```, ```left``` and ```z-index``` have *no effect*.

#### ```Relative```

When you first set an element to be positioned ```relative``` you will see that nothing has changes. When an element is positioned ```relative```, then the element isn't taken out of the flow of the document. The element can however change its position using the ```top```, ```right```, ```bottom``` and ```left``` properties. Example:

```CSS
#box5{
    position: relative;
    left: 600px;
}
```

![Relative position changed](ScreenshotsForNotes/RelativeChanged.PNG)

The other elements will behave as if ```#box5``` is still there, even though it has moved. 

***The properties ```top```, ```right```, ```bottom``` and ```left``` only change its position relative to its original position.***

MDN:

> The element is positioned according to the normal flow of the document, and then offset relative to itself based on the values of top, right, bottom, and left. The offset does not affect the position of any other elements; thus, the space given for the element in the page layout is the same as if position were static.

#### ```Absolute```

When an element is positioned ```absolute```, then that element is completely taken out of the flow of the document. All the other elements will behave as if it's simply not there. Just like with ```relative``` positioning, you can change the location using ```top```, ```right```, ```bottom``` and ```left```. 

This is what the element looks like after I've positioned it ```absolute``` with nothing else to it:

```CSS
#box5{
    position: absolute;
}
```

![Relative position changed](ScreenshotsForNotes/SimpleAbsolute.PNG)

You can see that the element has been taken out of the flow of the document and the other elements behave as if it's not there. The ```box6``` is under ```box5``` now but ```box5``` is shown since it has a higher ```z-index```.

Now, as previously mentioned, we can change its position using the properties ```top```, ```right```, ```bottom``` and ```left```:

```CSS
#box5{
    position: absolute;

    top: 250px;
    right: 30px;
}
```

![Absolute simple location](ScreenshotsForNotes/AbsoluteSimpleLocationChange.PNG)

The element has been positioned to be 30px far from the right side of the document and 250px far from the top side of the document.

The way ```top```, ```right```, ```bottom``` and ```left``` behave is also determined by the closest positioned element of the element that is set to be ```absolute``` ( note that a positioned element is considered an element that has the ```position``` property anything but ```static```, which is the default ```position``` property ).

That means that if the parent element of ```box5``` is set to be for example ```relative```, then that will change the behavior of the ```top```, ```right```, ```bottom``` and ```left``` properties.

Here is an example of how we changed the document before any positioning happened:

![Margin Main](ScreenshotsForNotes/MarginMain.PNG)

We have a ```<main></main>``` tag with some margin and padding and inside we have the boxes.

Let's change ```box5``` and give it a position of ```absolute``` and change its location:

```CSS
#box5{
    position: absolute;
    bottom: 0px;
    right: 0px;
}
```

![Absolute Position](ScreenshotsForNotes/AbsoluteChangeNoRelativeYetMainPadding.PNG)

Now, let's see how this element looks like when we change its parent element to also be positioned ( we will position it ```relative``` ):

```CSS
main {
    margin: auto;
    width: 700px;
    height: 700px;
    padding: 20px;
    border: 3px solid black;

    position: relative;
}

#box5{
    position: absolute;
    bottom: 0px;
    right: 0px;
}
```

![Absolute Position](ScreenshotsForNotes/AbsoluteChangeRelativeParent.PNG)

Now you can see that the position has changed but it's relative to its parent element ( in this case the ```<main></main>``` element )

MDN:

> The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to its closest positioned ancestor, if any; otherwise, it is placed relative to the initial containing block. Its final position is determined by the values of top, right, bottom, and left.
> This value creates a new stacking context when the value of z-index is not auto. The margins of absolutely positioned boxes do not collapse with other margins.

#### ```Fixed```

An element that is positioned to be 'fixed' is taken out of the document flow and is being scrolled with the page.

MDN:

> The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to the initial containing block established by the viewport, except when one of its ancestors has a transform, perspective, or filter property set to something other than none (see the CSS Transforms Spec), in which case that ancestor behaves as the containing block. (Note that there are browser inconsistencies with perspective and filter contributing to containing block formation.) Its final position is determined by the values of top, right, bottom, and left.

#### ```Sticky```

An element that is position to be 'sticky' isn't taken out of the document flow

MDN:

> The element is positioned according to the normal flow of the document, and then offset relative to its nearest scrolling ancestor and containing block (nearest block-level ancestor), including table-related elements, based on the values of top, right, bottom, and left. The offset does not affect the position of any other elements.

This value always creates a new stacking context. Note that a sticky element "sticks" to its nearest ancestor that has a "scrolling mechanism" (created when overflow is hidden, scroll, auto, or overlay), even if that ancestor isn't the nearest actually scrolling ancestor. This effectively inhibits any "sticky" behavior (see the GitHub issue on W3C CSSWG).

## CSS global properties

The global properties of most css properties are:

* inherit;
* initial;
* revert;
* revert-layer;
* unset;

### Inherit

The property should received its inherited values.

MDN:

> In CSS, inheritance controls what happens when no value is specified for a property on an element.
> CSS properties can be categorized in two types:
> * inherited properties, which by default are set to the computed value of the parent element
> * non-inherited properties, which by default are set to initial value of the property

### Initial

This means that the property has to revert back to its initial values. The initial settings of a property are its default values.

### Revert

> Specifies behavior that depends on the stylesheet origin to which the declaration belongs:
> * If the rule belongs to the author origin, the revert value rolls back the cascade to the user level, so that the specified values are calculated as if no author-level rules were specified for the element. For purposes of revert, the author origin includes the Override and Animation origins.
> * If the rule belongs to the user origin, the revert value rolls back the cascade to the user-agent level, so that the specified values are calculated as if no author-level or user-level rules were specified for the element.
> * If the rule belongs to the user-agent origin, the revert value acts like unset.

### Revert-layer

> Specifies that all the element's properties should roll back the cascade to a previous cascade layer, if one exists. If no other cascade layer exists, the element's properties will roll back to the matching rule, if one exists, in the current layer or to a previous style origin.

### Unset

Specifies that all the element's properties should be changed to their inherited values if they inherit by default, or to their initial values if not.


## CSS Float and Clear

In order to make elements float left or right use the ```float``` property. In order to clear the floating you must use the ```clear``` property ( clear ```right```, ```left``` or ```both``` ).

## CSS Flexbox

```>```

### Basics and terminology



Since flexbox is a whole module and not a single property, it involves a lot of things including its whole set of properties. Some of them are meant to be set on the container (parent element, known as “flex container”) whereas the others are meant to be set on the children (said “flex items”).

If “regular” layout is based on both block and inline flow directions, the flex layout is based on “flex-flow directions”. Please have a look at this figure from the specification, explaining the main idea behind the flex layout.

![Container Terminology](ScreenshotsForNotes/Flexbox/terminology.svg)


Items will be laid out following either the main axis (from main-start to main-end) or the cross axis (from cross-start to cross-end).

* main axis – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
* main-start | main-end – The flex items are placed within the container starting from main-start and going to main-end.
* main size – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
* cross axis – The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
* cross-start | cross-end – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
* cross size – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.

### Properties for the flex container

#### ```display```

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```CSS
.container {
  display: flex; /* or inline-flex */
}
```

Note that CSS columns have no effect on a flex container.

#### ```flex-direction```

![Flex direction](ScreenshotsForNotes/Flexbox/flex-direction.svg)

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```CSS
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

* row (default): left to right in ltr; right to left in rtl
* row-reverse: right to left in ltr; left to right in rtl
* column: same as row but top to bottom
* column-reverse: same as row-reverse but bottom to top

#### ```flex-wrap```

![Flex wrap](ScreenshotsForNotes/Flexbox/flex-wrap.svg)

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

```CSS
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

* nowrap (default): all flex items will be on one line
* wrap: flex items will wrap onto multiple lines, from top to bottom.
* wrap-reverse: flex items will wrap onto multiple lines from bottom to top.

#### ```flex-flow```

This is a shorthand for the flex-direction and flex-wrap properties, which together define the flex container’s main and cross axes. The default value is row nowrap.

```CSS
.container {
  flex-flow: column wrap;
}
```

#### ```justify-content```

![justify-content](ScreenshotsForNotes/Flexbox/justify-content.svg)

This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```CSS
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
}
```

* flex-start (default): items are packed toward the start of the flex-direction.
* flex-end: items are packed toward the end of the flex-direction.
* start: items are packed toward the start of the writing-mode direction.
* end: items are packed toward the end of the writing-mode direction.
* left: items are packed toward left edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
* right: items are packed toward right edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like end.
* center: items are centered along the line
* space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line
* space-around: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
* space-evenly: items are distributed so that the spacing between any two items (and the space to the edges) is equal.

#### ```align-items```

![align-items](ScreenshotsForNotes/Flexbox/align-items.svg)

This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis (perpendicular to the main-axis).

```CSS
.container {
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
}
```

* stretch (default): stretch to fill the container (still respect min-width/max-width)
* flex-start / start / self-start: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
* flex-end / end / self-end: items are placed at the end of the cross axis. The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
* center: items are centered in the cross-axis
* baseline: items are aligned such as their baselines align

#### ```align-content```

![align-content](ScreenshotsForNotes/Flexbox/align-content.svg)

This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

* Note: This property only takes effect on multi-line flexible containers, where flex-wrap is set to either wrap or wrap-reverse). A single-line flexible container (i.e. where flex-wrap is set to its default value, no-wrap) will not reflect align-content.*

```CSS
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
}
```

* normal (default): items are packed in their default position as if no value was set.
* flex-start / start: items packed to the start of the container. The (more supported) flex-start honors the flex-direction while start honors the writing-mode direction.
* flex-end / end: items packed to the end of the container. The (more support) flex-end honors the flex-direction while end honors the writing-mode direction.
* center: items centered in the container
* space-between: items evenly distributed; the first line is at the start of the container while the last one is at the end
* space-around: items evenly distributed with equal space around each line
* space-evenly: items are evenly distributed with equal space around them
* stretch: lines stretch to take up the remaining space

#### ```gap, row-gap, column-gap```

![Gap](ScreenshotsForNotes/Flexbox/gap.svg)

The gap property explicitly controls the space between flex items. It applies that spacing only between items not on the outer edges.

```CSS
.container {
    display: flex;
    ...
    gap: 10px;
    gap: 10px 20px; /* row-gap column gap */
    row-gap: 10px;
    column-gap: 20px;
}
```

The behavior could be thought of as a minimum gutter, as if the gutter is bigger somehow (because of something like justify-content: space-between;) then the gap will only take effect if that space would end up smaller.

It is not exclusively for flexbox, gap works in grid and multi-column layout as well.

### Properties for the flex items

#### ```order```

![order](ScreenshotsForNotes/Flexbox/order.svg)

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

```CSS
.item {
  order: 5; /* default is 0 */
}
```

Items with the same order revert to source order.

#### ```flex-grow```

![flex-grow](ScreenshotsForNotes/Flexbox/flex-grow.svg)

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, that child would take up twice as much of the space either one of the others (or it will try, at least).

```CSS
.item {
  flex-grow: 4; /* default 0 */
}
```

Negative numbers are invalid.

#### ```flex-shrink```

This defines the ability for a flex item to shrink if necessary.

```CSS
.item {
  flex-shrink: 3; /* default 1 */
}
```

Negative numbers are invalid.

#### ```flex-basis```

This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The auto keyword means “look at my width or height property” (which was temporarily done by the main-size keyword until deprecated). The content keyword means “size it based on the item’s content” – this keyword isn’t well supported yet, so it’s hard to test and harder to know what its brethren max-content, min-content, and fit-content do.

```CSS
.item {
  flex-basis:  | auto; /* default auto */
}
```

If set to 0, the extra space around content isn’t factored in. If set to auto, the extra space is distributed based on its flex-grow value. See this graphic.

#### ```flex```

This is the shorthand for flex-grow, flex-shrink and flex-basis combined. The second and third parameters (flex-shrink and flex-basis) are optional. The default is 0 1 auto, but if you set it with a single number value, like flex: 5;, that changes the flex-basis to 0%, so it’s like setting flex-grow: 5; flex-shrink: 1; flex-basis: 0%;.

```CSS
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

It is recommended that you use this shorthand property rather than set the individual properties. The shorthand sets the other values intelligently.

#### ```align-self```

![align-self](ScreenshotsForNotes/Flexbox/align-self.svg)

This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

Please see the align-items explanation to understand the available values.

```CSS
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

Note that float, clear and vertical-align have no effect on a flex item.