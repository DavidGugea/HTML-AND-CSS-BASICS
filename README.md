# The basics of HTML5 and CSS3

## Chapter 5 ( Tables and Hyperlinks )

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

## Chapter 6 ( Grafics and Multimedia )

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

## Chapter 7 ( HTML Forms )

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