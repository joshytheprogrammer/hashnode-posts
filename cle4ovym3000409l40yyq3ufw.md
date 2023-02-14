# How to create a spinner/loader UI with HTML and CSS

Welcome back, dear readers.

In the last post, I wrote about 9 CSS projects you can build as a beginner CSS developer. The post was designed for beginner front-end developers who want to hit the ground running. If you missed that post, and you feel like you need it you can open [this](https://blog.joshytheprogrammer.com/9-css-projects-you-can-build-to-get-better) in a new tab.

In today's post, we will be working on the first project I required you to be capable of building. It is by far the easiest project on our list. A spinner/loader. The project itself needs no introduction. We have all encountered spinner/loader UIs at some point and today you will be building your very own.

Our project will look something like what you see below, and it is the very same spinner I used on the Neas Fashion website found [here](http://neasfashion.demo.joshytheprogrammer.com/).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676403653266/11c6739a-a445-4b3c-be8e-7ca9808f3697.gif align="center")

## The HTML

The HTML for spinners is very, very basic. All it requires is one div with a class of spinner or loader or whatever.

```xml
<div class="loader"></div>
```

The CSS is where the magic really happens. This single div is what will be transformed into the infinitely rotating circular spinner you see above.

## The CSS

```css
.loader {
    margin: 2rem 0;
    width: 60px; 
    height: 60px;
    border: 8px solid $light;
    border-top: 5px solid hsl(351, 81%, 27%);
    border-radius: 50%;
    animation: spin .5s linear infinite;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}
```

Firstly, we are going to target the loader class and give it a margin-top-bottom of 2rem. The reason I did this was to leave some space between our Navigation bar and our actual spinner. As it stands, you probably can't see anything on your document but be patient, it's coming.

Next up, we are going to give it a fixed width and height of 60px. This actually determines the size of the spinner, so feel free to change it up as much as you like.

Next up, I would have you set the value of the border & border-top property to what you see in the code above. This should result in a straight line bar. It is this bar that will later rotate to give us the spinner. It should look something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676404738230/e4a1ecc2-d101-4e48-8a4b-a166bc918ed2.png align="center")

Lastly (for the design), let's instruct CSS to give it a border radius of 50%. This will curve the horizontal bar into something resembling the curved structure we are looking for.

The last line of CSS code that will be in the loader class selector is one that instructs it to apply the simple rotating animation we will be building. We CSS to add the spin animation and repeat it every 0.5 seconds infinitely. You have probably noticed that nothing happened, the reason is that we haven't yet told CSS what the spin animation is. We will be doing this using `@keyframes`

We spin keyframe we created simply tells CSS to rotate the circle 360 degrees. This keyframe combined with the animation property is what allows CSS to rotate the div from 0 to 360 degrees in 0.5 seconds infinitely.

## The Conclusion

And there you have it. Your very own spinner. Keep in mind that there are many different kinds of spinners out there, and even this one can be infinitely customized to fit your needs. So keep practicing and Happy Coding.