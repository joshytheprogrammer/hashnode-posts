## HTML for beginners

HTML is a markup language for defining websites. It stands for HYPER TEXT MARKUP LANGUAGE and is what defines the structure of every website. For example, html can define links, paragraphs, divisions, articles, sections etc. 

A HTML element is defined by a start tag, some content, and an end tag:

```html
<tagname> Content goes here... </tagname>
```
The HTML element is everything from the start tag to the end tag:

```html
<h1>My First Heading</h1>
```
```html
<p>My first paragraph.</p>
```

~ exert from w3schools

## HTML Editing Software

Visit [https://code.visualstudio.com/](https://code.visualstudio.com/) and follow the appropriate steps to download and install vscode. 

Now proceed to installing the extension known as live server. If you don't see it in the extensions tab, you can click [here](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) to install it. 

Launch a local development server with live reload feature for static & dynamic pages.

![vscode-live-server-animated-demo.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1660072499457/qhWT2wL8b.gif align="left")

## Structure of a HTML document

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

### Breakdown

The `<!DOCTYPE html>` declaration tells the browser your document is going to be a html5 document. It must at the top of the page before any HTML tags.

The `<title>Document</title>` tag, defines the text that is shown on the browser tab. 

### Empty tags

Some HTML element have no content. These are called empty tags. An example of this is `<br>`. Empty elements do not have end tags.

### Self closing tags

Not all elements require end tags. Elements like the image tag, do not require closing tag. These are called self closing tags. Other self closing tags are ->

```html
<area />
<base />
<br />
<col />
<embed />
<hr />
<img />
<input />
<link />
<meta />
<param />
<source />
<track />
<wbr />
```

### Nested HTML

HTML elements can be nested, this means that they can be placed inside other html elements. In fact, most html elements are nested. The head, body, p, footer, article are all elements that are usually nested.

### Never skip the end tag

Never skip the end tag, it is common for beginners to not close their html elements. 
```html
<h1> What is my gender? 
<p> I am a boy. </p>
```
This will cause multiple errors. Remember the syntax -> 
```html 
<tagname> content... </tagname>
```

### Html tags are case insensitive 

HTML tags are not case sensitive. This means that `<P>` and `<p>` are the same in HTML. However, it is **recommended** you use lowercase characters when defining tags. 

### HTML attributes

HTML attributes provide additional information about HTML elements.

- All HTML elements can have attributes
- Attributes usually come in name/value pairs like: name="value"
- Attributes are always specified in the start tag
- Attributes provide additional information about elements

Some examples of html attributes : 

### The src attribute.

We spoke about images earlier so lets discuss the "src" attribute. The `img` tag is used to embed images on a webpage. The "src" attribute specifies the path to the image to be displayed.

```html
<img src="path_to_image" />
```

There are two ways to specify the URL in the src attribute:

1.Absolute URL - Links to an external image that is hosted on another website. Example: src="https://www.w3schools.com/images/img_girl.jpg".

Notes: External images might be under copyright. If you do not get permission to use it, you may be in violation of copyright laws. In addition, you cannot control external images; it can suddenly be removed or changed.

2.Relative URL - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If the URL begins without a slash, it will be relative to the current page. Example: src="img_girl.jpg". If the URL begins with a slash, it will be relative to the domain. Example: src="/images/img_girl.jpg".

Tip: It is almost always best to use relative URLs. They will not break if you change domain.

~ Exert from w3schools.

### The href attribute.

The href attribute is tied to the 'a' tag. It specifies the page the link points to. The syntax is:

```html
<a href="google.com"> Visit Google </a>
```

**Note: ** I recommend using double quotes and lowercase when defining attributes.


## Your first webpage

Open a folder, create a new file `index.html`. Now type `html:5` and then `tab`.

This should scaffold something like this, you can also just copy this : 

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>joshytheprogrammer</title>
</head>
<body>
  
</body>
</html>
```

The title tag, defines the text on the browser tab. I will have an image down below :

![tab-display.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660074468704/ezgbm8j1S.png align="left")

Now inside the body tag, place the following code :

```html
  <h1>Level 1</h1>
  <h2>Level 2</h2>
  <h3>Level 3</h3>
  <h4>Level 4</h4>
  <h5>Level 5</h5>
  <h6>Level 6</h6>
```

This should result in something like this :

![heading-levels.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660075470032/Np018LuAZ.png align="left")

The h's described above stand for heading. Each of the h<no> represent different levels of heading ranging 1 - 6. One is the highest and six is the lowest as seen in the example below. 

There you have it, you created your first web page.

Let's look at other things we can do with html. 

## Text, Links, Lists and Images

**Let's start with text.** In html, you can define text in many ways. You can simply write on the editor without placing any tags and it will display in the browser as plain text. Or, you can define a paragraph `<p></p>`. 

```html
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit?</p>
```

The code above will create a paragraph ( containing the text inside the p tag ) in the browser.

By the way, I don't speak Italian. You can generate this text by typing `lorem10`.

**Next up links.** To create a link we would use the `a` tag. This tag however is not like your regular html element in that it relies on an attribute to function effectively. This attribute is called `href` attribute.  The href attribute specifies the URL of the page the link goes to.
Let's see how it works: 

```html
<a href="https://blog.joshytheprogrammer.com">Visit my blog</a>
```

I have already talked about this in the attributes section of this lesson. 

**Next we have Lists.** HTML lists allow web developers to group a set of related items in lists. They are of two types, ordered lists and unordered lists. 

An ordered lists starts with an `ol` tag. Each list item will have an `li` tag. Ordered lists are numbered by default. 

```html
<p>Foods I like: </p>
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

An unordered lists starts with an `ul` tag. Each list item will have an `li` tag. Unordered lists have bullet points by default. 

```html
<p>YT Channels I like: </p>
<ul>
  <li>joshytheprogrammer</li>
  <li>swagkage</li>
  <li>Matt walsh</li>
</ul>
```

**Lastly, Images.** To add an image to a website we use the `img` tag combined with the src attribute. The src attribute points to the location of the image file.
When we first add an image, the browser will display the full image. We might not want that. To edit an image's width and height, we simply use the width and height attributes. 

```html
<img src="path_to_image" width="480px" height="400px" />
```

That's all for now. This may seem like a lot for now but remember, practice makes perfect. The more you use these concepts, the better you get at using them. Hope you enjoyed, check out my other content below.