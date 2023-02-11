# Relevant HTML tags - Beginner HTML

Good day everyone 👋. Welcome back to my blog.

In the last post, I tried to help my aspiring developers get their feet wet with HTML. In order to not too overwhelm you, I decided to break that post into multiple posts. If you happened to stumble upon my blog, welcome. My name is Joshua and I am a full-stack web developer and I love to help aspiring web developers learn and gain experience quickly. If you are one of these aspiring developers, and you need to learn HTML quickly, check out this post [here](https://blog.joshytheprogrammer.com/html-for-beginners). It is called HTML for beginners and I have used it to teach HTML in several schools and to several students.

## Introduction

In this post we will be looking at some tags that every web developer knows. This lesson is designed for beginners so I will try to go as slow as possible.

We covered some elements in the previous post, lets go over those for the sake of newcomers :- The elements covered are, the heading element, the paragraph element, the image element, the link element and the list element.

### Recap

HTML elements are depicted using tags. These tags generally follow this syntax.

```html
<tagname> content </tagname>
```

There are also tags that don't follow this general pattern. These tags are called self-closing or empty tags. They are simply as :-

```html
<tagname  > or <tagname />
```

**The heading element** is used to define page headings. In HTML, the heading tag has six levels.

```html
<h1> Level 1 </h1>
<h2> Level 2 </h2>
<h3> Level 3 </h3>
<h4> Level 4 </h4>
<h5> Level 5 </h5>
<h6> Level 6 </h6>
```

**The paragraph element** is used to define paragraphs. It is defined using the p tag:

```html
<p> content </p>
```

Some HTML elements require attributes. Attributes pass information to elements. An example of this is

**The image element.** This is used to display images on a document. It is defined using the self-closing tag "img" and the attribute "src" :

```html
<img src="path_to_image" />
```

**The anchor element.** This is used to define text that can refer users to other webpages. They are often called links. It is defined using the "a" tag and the attribute "href" :

```html
<a href="https://blog.joshytheprogrammer.com> check out my blog </a>
```

**The list element.** This is used to define lists. There are two types of lists, ordered lists and unordered lists. They are defined using the "ol" and "ul" tags respectively. Lists have items, these are defined using the "li" tag :

```html
<ul>
  <li> list item 1 </li>
  <li> list item 2 </li>
</ul>
```

The ul can be replaced with ol for an ordered list.

## HTML buttons

The button element defines clickable buttons on the document. It is depicted using the button tag and the type attribute. The type attribute when used with the button element, defines the purpose of the button.

```html
<button type="button" > Click me ! </button>
```

Inside a element you can put text (and tags like `<i>`, `<b>`, `<strong>`, `<br>`, `<img>`, etc.). Styling buttons is also very easy although we wont look at that today. HTML forms The form elements defines forms for the user to input data. It doesn't make any visible change in the browser but it acts as a house for the elements that do. It is defined using the "form" tag. `<form> </form>` The form element can house one or more of the following elements : `<input>` `<textarea>` `<button>` `<select>` `<option>` `<optgroup>` `<fieldset>` `<label>` `<output>` \*\*The input element. \*\* The input element is used to define input fields for users. It is the most important form element. The input tag is a self-closing tag. The input element can be displayed in different ways depending on the value of the type attribute sent with it. `<input type="button">` `<input type="checkbox">` `<input type="color">` `<input type="date">` `<input type="datetime-local">` `<input type="email">` `<input type="file">` `<input type="hidden">` `<input type="image">` `<input type="month">` `<input type="number">` `<input type="password">` `<input type="radio">` `<input type="range">` `<input type="reset">` `<input type="search">` `<input type="submit">` `<input type="tel">` `<input type="text"` (default value) `<input type="time">` `<input type="url">` `<input type="week">` Each of these attribute values will give you a different result. Feel free to try them out. \*\*The label element. \*\* The label element is used to label input elements. It is defined using the "label" tag and the "for" attribute. The "for" attribute's value should be the value of the "id" attribute used on the input element. Does it sound confusing? See an example `<label for="name"> Full Name </label> <input id="name" type="text" >` Notice how the "for" attribute on the label tag is the same as the "id" attribute on the input tag. That is how labels are bound to input elements. The same can be said of most form elements. Always use the `<label>` tag to define labels for `<input type="text">`, `<input type="checkbox">`, `<input type="radio">`, `<input type="file">`, and `<input type="password">`. Proper use of labels with the elements above will benefit: Screen reader users (will read out loud the label, when the user is focused on the element) Users who have difficulty clicking on very small regions (such as checkboxes) - because when a user clicks the text within the element, it toggles the input (this increases the hit area). The are many other form elements that I wanted to write about but this post is already getting too long. I'll save that topic for another post. I built a contact form using html and css, you can check that out [here](https://blog.joshytheprogrammer.com/how-to-build-a-simple-contact-form-using-html-and-css) The table element and other related tags The table element defines a table in the browser. It is defined using the "table" tag. An HTML table consists of one `<table>` element and one or more `<tr>`, `<th>`, and `<td>` elements. The `<tr>` element defines a table row, the `<th>` element defines a table header, and the `<td>` element defines a table cell. `<table> <tr> <th>Month</th> <th>Savings</th> </tr> <tr> <td>January</td> <td>$100</td> </tr> <tr> <td>February</td> <td>$80</td> </tr> </table>` You can also group the table elements into `thead`, `tbody`, `tfoot` `<table> <thead> <tr> <th>Month</th> <th>Savings</th> </tr> </thead> <tbody> <tr> <td>January</td> <td>$100</td> </tr> <tr> <td>February</td> <td>$80</td> </tr> </tbody> <tfoot> <tr> <td>Sum</td> <td>$180</td> </tr> </tfoot> </table>` The video element Just as you can add images to webpages, you can also add videos. The `<video>` tag is used to embed video content in a document, such as a movie clip or other video streams. The `<video>` tag can contain one or more `<source>` tags with different video sources. The browser will only choose the first source it supports. You can also add the "src" attribute to the video tag just as you do with the image tag. There are three supported video formats in HTML: MP4, WebM, and OGG. `<video src="path_to_video" > </video>` The video tag like the image tag accepts multiple attributes. These include : \*\*The controls attribute \*\*: The controls attribute is a Boolean attribute. When present, it specifies that video controls should be displayed. **The autoplay attribute**: This specifies that the video will start playing as soon as it is ready/ loaded. **The width & height attribute**: This specifies the width and height of the video player. **The loop attribute**: This tells the browser to replay the video every time it is finished playing. **The muted attribute**: This specifies that the audio output of the video should be muted. **The poster attribute**: This specifies the image to be shown while the video is downloading, or until the user hits the play button. `poster="path_to_image"` There are a few more but I feel this is enough for this post. Some relevant text based tags There are some tags in HTML designed to make text look better. This is called HTML formatting. **Bold text**: This is used to make texts in HTML bolder. The text is placed inside the "b" or "strong" tags. `<p> This text should be <b>boldened</b> </p> <p> This text should be <strong>boldened</strong> </p>` **Italic text**: This is used to make texts in HTML enclose in italics font. The text is placed inside the "em" or "i" tags. `<p> This text should be <i>placed in italic text</i> </p> <p> This text should be <em>placed in italic text</em> </p>` **Highlighted text**: It is possible to mark or highlight text in html. The text is placed inside the "mark" tag. `<h2> I have <mark>marked</mark> his face </h2>` **Underlined text**: It is possible to underline text in html. The text is place inside the "u" tag. `<p> The <u>boy</u> is very nice </p>` **Strike text**: It is possible to strike through text in html. The text is placed inside the "strike" tag. `<p> I will <strike>strike</strike> this out. </p>` **Superscript text**: It is possible display half a character's height above the other characters (similar to power in math). The text is placed inside the "sup" tag. `<p>Hello <sup>Write Your First Paragraph in superscript.</sup></p>` **Subscript text**: It is possible to display half a character's height below the other characters (similar to base in math). The text is placed inside the "sub" tag. `<p>Hello <sub>Write Your First Paragraph in subscript.</sub></p>` Some others (edited): **Line break**: `<p> Hello <br> World </p>` **Horizontal rule** `<p> Hello World </p> <hr> <p> Good bye world </p>` There are a few more text formatting techniques that exist but I feel this is enough for this post. Conclusion That's all for now folks. This post ended up being much longer than I expected but its worth it. If you think its much, remember that all of these tags were created for you. See you in the next post.