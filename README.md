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