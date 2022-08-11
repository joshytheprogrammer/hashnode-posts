## How to create a custom modal with html and css.

Let's build a custom alert notification modal. There will be no JS involved simply HTML and CSS. This post is targeted towards beginners, I'll have a more advanced course targeted towards those that know Nuxtjs soon.

Firstly, this is the end result of our work. 
![custom-alert-end-result-img.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659554194556/kXQapsw4f.png align="left")

The source code will be available on GitLab through this link -> [https://gitlab.com/joshytheprogrammer/custom-alert-html-css](https://gitlab.com/joshytheprogrammer/custom-alert-html-css).

## Default Scaffolds
Generate a new html 5 document and link it to your style.css. Once you have done this, create a div with a class of container inside it. As for the basic css, we will simply add a font and some css re-setters. Copy and paste the following code into your project - 

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', Verdana, Georgia, 'Times New Roman', Times, serif;
}

body {
  width: 100%;
  background-color: #E4E3E3;
}
```

## The simple container
If you were to be building a real project, this wouldn't necessary. We are adding it to give our application some beauty and color. In your css, attach the following styles. Feel free to customize as you see fit. 

```css
.container {
  display: flex;
  width: 80%;
  height: 720px;
  padding: 1rem;
  margin: 2rem auto;
  background: #000;
  border-radius: 12px;
}
```

**Note: ** The display set to flex centers all components within the container.

## Let's start building

Create a div with the class of alert. This div will house all the other components in the alert. Essentially, we will be building three components. The header, body and footer. The header houses the type of message or the title of the message. The body will go into further detail about the error/warning/success message and the footer will have simply the close button. The button's color will change depending on the type of message being sent.


### The alert

Within your class of alert, create another div with a class of head. Within this div, create a h2 tag. Simply, 

```html
<div class="alert">
  <div class="head">
    <h2> An error occurred </h2>
  </div>
</div>
```

Now let's style the alert : ->
```css
.alert {
  display: flex;
  flex-direction: column;
  margin: auto;
  background-color: #fff;
  width: 500px;
  height: 300px;
  border-radius: 8px;
}
```

Let me quickly run through the code : 

The display of flex combined with the flex-direction property set to column, makes the components display vertically. The margin, when set to auto - centers the entire alert component in the center. You should be familiar with the remaining elements.

### The alert header

The class of head has the following styes : ->

```css
.alert .head{
  height: 50px;
  padding: 1rem;
  border-bottom: 1px solid #000;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
 ```

If you recall earlier I set the height of the alert component to 300px, this was no mistake. I set a fixed height because I would like to distribute the heights of each component, I don't want the browser to decide. The header and the footer will take 50px, while the body takes 200px.

The rules from the border-bottom property and below all help me align the h2 tag in the center both vertically and horizontally. 

### The alert body

Create a div with a class of body. Within that div, create a new paragraph tag. Within that paragraph tag, type `lorem40`. This will generate some fake paragraphs for you to use to style. The amount of words in these paragraphs will correspond to the number you type after lorem. Now let's get to styling : -> 

```css
.alert .body {
  height: 200px;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
```

I won't explain any of this because I have done so already, Basically, I am defining a fixed height, and setting it center itself vertically and horizontally. It's starting to look really good.

### The alert footer and close button

Let's quickly talk about the alert footer. Create a div with a class of footer. Within that footer, create a button and label it close. Like so : ->

```html
  <div class="footer">
    <button>Close</button>
  </div>
```

Now for the css : ->

```css
.alert .footer {
  height: 50px;
  border-top: 1px solid #000;
  padding: 1rem;

  display: inline-flex;
  align-items: center;
  justify-content: flex-end;
}
```

The justify-property set to flex end, tells the browser to push the content of the footer as far away to the right as possible within the confines of the div's width. 

```css
.alert .footer button {
  height: 30px;
  padding: 0.4rem 0.6rem;
  color: #fff;
  border-radius: 4px;
  cursor: pointer;
  border: none;
}
```

We are now styling the button. Beginners, learn something. You don't have to define the height, it is set to fit-content in buttons by the browser. The cursor property, tells the browser to display that hand click cursor instead of the regular cursor. I don't know how else to describe it sorry. Essentially like 👆. The border property set to none, removes the default ugly button border. This is really important. 

### Conditional styling

I want us to give the button a different background-color depending on the type of alert being sent. Red for error, yellow for warning and green for success.

```css
.alert.error .footer button {
  background: red;
}

.alert.warning .footer button {
  background: rgb(184, 184, 44);
}

.alert.success .footer button {
  background: green;
}
```

This way, if you change the class of the alert div, you change the type of error. 

**Note : - ** You can conditionally change the classes of elements using JavaScript. We wont get into that now though.

### Media Queries

I've already briefly touched on media queries before. They are simply a way for us to change the styles applied to elements based on the user's unique screen width. They are an effective tool in mobile-first/responsive development. Let's make our code responsive : -> 

```css
@media screen and (max-width: 728px){
  .alert {
    width: auto;
    height: auto;
  }
}

@media screen and (max-width: 456px){
  .alert .head h2 {
    font-size: 16px;
    font-weight: 600;
  }

  .alert .body{
    font-size: 14px;
  }
}
```

We are basically telling our browser, that if the user's screen is 728/456 px run the following code. In our case, remove fixed width and height and let the browser decide. Whilst, reducing the font-size and weight of both the h2 and the .body tags. 

And that's all, we have created a responsive alert menu. Should I be deploying my code previews through Netlify, I'll deploy this. You can find it [here](https://custom-alert-jtp-blog.demo.joshytheprogrammer.com/).