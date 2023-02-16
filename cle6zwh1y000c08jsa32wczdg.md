# How to create a full-screen video background with HTML and CSS

Welcome back readers, we will be continuing our series on CSS projects for beginners. If you aren't caught up, there are a few projects you can work on as a beginner front-end developer that will allow you to grow significantly faster than your average beginner. So if you are interested in accelerated growth, check out the post [here](https://blog.joshytheprogrammer.com/9-css-projects-you-can-build-to-get-better).

For today's post, let's build a One Piece AD. That's right. Today we will be building a simple website with a One Piece trailer as the Full Screen Background. The goal is to teach you how you can implement the same with whatever video you want.

The project we will be building has been deployed and can be found [here](https://onepiece-video-bg-blog.demo.joshytheprogrammer.com/). You can also get the code on GitLab [here](https://gitlab.com/joshytheprogrammer/one-piece-video-bg-post). Here is a quick screenshot.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676545422218/960dfc6d-5b14-4461-a707-b4bf7ce0bb27.png align="center")

## The HTML

```xml
<div class="container">
    <video muted autoplay loop src="link-to-your-video" id="fullVid"></video>

    <div class="content">
      <h1>One Piece is Peak</h1>
      <a href="https://zoro.to/one-piece-100">Start Watching</a>
    </div>
</div>
```

## The CSS

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,300&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Lato', Helvetica;
  scroll-behavior: smooth;
}

h1, h2, h3, h4, h5 ,h6 {
  font-family: 'Poppins', Georgia;
}

.container #fullVid {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
}

.container .content {
  position: fixed;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  color: #f1f1f1;
  width: 100%;
  padding: 20px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.container .content a {
  display: block;
  width: fit-content;
  border: none;
  padding: 10px;
  color: #fff;
  margin: 10px 0;
  cursor: pointer;
  font-size: 14px;
  background: #000;
  text-align: center;
  text-decoration: none;
}

.container .content a:hover {
  background: #ddd;
  color: black;
}
```

## Quick Explanation

The styles associated with the video tag are responsible for the full-screen functionality you see. That's right. Just 5 lines of code and you built a video background.

**Please note**:- If you want to be able to scroll through the video, maybe to add extra content to that one page, simply take out the `position: fixed;` rule from both the video and the content selectors.

There's not much to say about this since it's so simple. I won't waste your time but if you have any questions, feel free to ask it in the comments. Have a lovely day.