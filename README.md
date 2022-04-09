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