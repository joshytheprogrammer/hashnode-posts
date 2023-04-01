---
title: "Getting started with Nuxtjs"
datePublished: Sat Apr 01 2023 12:50:41 GMT+0000 (Coordinated Universal Time)
cuid: clfxz1xtl000609jwd24a83wv
slug: getting-started-with-nuxtjs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1660601567140/ymJpOmB8c.png
tags: vuejs, getting-started, nuxt

---

## Introduction

Nuxt is a popular open-source framework based on Vue.js for building server-rendered, static and single-page web applications. The latest version of Nuxt, Nuxt 3, was released in October 2021, and it comes with a lot of new features and improvements. In this blog post, we'll provide a step-by-step guide on how to get started with Nuxt 3.

## Prerequisites

Before you can start building with Nuxt 3, you'll need to have some basic knowledge of HTML, CSS, and JavaScript, as well as familiarity with the Vue.js framework. Additionally, you'll need to have Node.js and npm installed on your computer.

## Getting started

To create a new Nuxt 3 project, you can use the Nuxt CLI, which is a command-line interface that helps you generate a new project with pre-configured settings and tools. Here are the steps to create a new Nuxt 3 project:

1. Open your terminal and navigate to the directory where you want to create the new project.
    
2. Run the following command to install the Nuxt CLI:
    

```bash
npm install -g nuxt
```

1. Run the following command to create a new Nuxt project:
    

```bash
nuxt create my-nuxt-app
```

1. Follow the prompts to choose the options for your new project, such as the type of project (Universal, SPA, or Static), the package manager (npm or yarn), and the UI framework (Bootstrap, Tailwind CSS, etc.).
    

Once the project is created, you can navigate to the project directory and start the development server by running the following command:

```bash
cd my-nuxt-app
npm run dev
```

This will start the development server on [http://localhost:3000](http://localhost:3000).

## Key features of Nuxt 3

Nuxt 3 comes with a lot of new features and improvements over the previous version, Nuxt 2. Here are some of the key features of Nuxt 3:

### Improved performance

Nuxt 3 has been optimized for faster performance, with reduced build times and faster page loads. This is achieved through the use of several new tools and techniques, such as the new JIT mode for the Vue.js compiler, the new Vite build tool, and improved server-side rendering.

### Better developer experience

Nuxt 3 has been designed with developer experience in mind, with improved documentation, better error handling, and easier configuration. The Nuxt team has also introduced several new tools and plugins to make development easier, such as the new Nuxt Auth module, which provides easy authentication and authorization for Nuxt apps.

### Modular architecture

Nuxt 3 has a modular architecture that allows developers to add or remove features as needed. This makes it easier to build custom apps with only the features you need, without having to include unnecessary dependencies.

### Improved TypeScript support

Nuxt 3 has improved support for TypeScript, with better type checking and integration with popular TypeScript tools and libraries.

## Building your first Nuxt 3 app

Now that you have a basic understanding of Nuxt 3 and its key features, let's build a simple app to see how it works in practice. In this example, we'll build a basic website with two pages: a home page and an about page.

### Creating the pages

To create a new page in Nuxt 3, you simply need to create a new .vue file in the `pages` directory. Let's create two new files: `index.vue` for the home page and `about.vue` for the about page.

```xml
<template>
  <div>
    <h1>Welcome to my Nuxt 3 app!</h1>
    <p>This is the home page.</p>
    <p>
      Go to the <nuxt-link to="/about">about page</nuxt-link>.
    </p>
  </div>
</template>

<script>
export default {
  name: 'Index',
}
</script>

<style scoped>
h1 {
  font-size: 3rem;
  color: #333;
  margin-bottom: 1rem;
}

p {
  font-size: 1.5rem;
  color: #666;
}
</style>
```

This code defines a simple `div` element that displays a welcome message, a brief description of the page, and a link to the `about.vue` page using the `nuxt-link` component.

```xml
<template>
  <div>
    <h1>About Page</h1>
    <p>This is the about page</p>
  </div>
</template>
```

### Adding navigation

To navigate between the two pages, we need to create a navigation menu. We can do this by creating a new component called `Navigation.vue`.

```xml
<!-- components/Navigation.vue -->

<template>
  <nav>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </nav>
</template>
```

Then we need to include this component in our `Layout.vue` file.

```xml
<!-- layouts/default.vue -->
<template>
  <div>
    <Navigation />
    <nuxt />
  </div>
</template>

<script>
import Navigation from '~/components/Navigation.vue'

export default {
  components: {
    Navigation,
  },
}
</script>
```

### Styling the pages

To style our pages, we can use CSS or any other CSS preprocessor like SCSS or Less. We can also use CSS frameworks like Tailwind CSS or Bootstrap to make styling easier.

For this example, let's use Tailwind CSS. We can install it using npm:

```bash
npm install tailwindcss
```

Then we can create a new file called `tailwind.config.js` in the root directory of our project:

```javascript
// tailwind.config.js

module.exports = {
  mode: 'jit',
  purge: ['./public/**/*.html', './src/**/*.{vue,js,ts,jsx,tsx}'],
  theme: {},
  variants: {},
  plugins: [],
}
```

This configures Tailwind CSS to use the just-in-time (JIT) compiler mode and to purge any unused styles from our project.

Then we need to import Tailwind CSS in our `main.js` file:

```javascript
// main.js

import 'tailwindcss/tailwind.css'
```

Now we can add some basic styles to our pages:

```xml
<!-- pages/index.vue -->

<template>
  <div class="bg-gray-100">
    <h1 class="text-2xl font-bold text-center my-4">Welcome to my Nuxt 3 app</h1>
    <p class="text-center text-lg">This is the home page</p>
  </div>
</template>

<!-- pages/about.vue -->

<template>
  <div class="bg-gray-100">
    <h1 class="text-2xl font-bold text-center my-4">About Page</h1>
    <p class="text-center text-lg">This is the about page</p>
  </div>
</template>
```

### Building and deploying the app

Once we've built our app, we can deploy it to a web server or a cloud service like AWS or Firebase. To build the app, we can run the following command:

```bash
npm run build
```

This will generate a production-ready version of our app in the `dist` directory. We can then deploy this directory to a web server or cloud service.

Alternatively, we can use a service like Vercel to deploy our app automatically when we push changes to our Git repository. To do this, we need to connect our repository to Vercel and configure the deployment settings.

## Conclusion

In this blog post, we've provided a step-by-step guide on how to get started with Nuxt 3, including creating pages, adding navigation, styling the pages, and building and deploying the app. We've also covered some of the basic features of Nuxt 3, including layouts, components, and routing.

With this knowledge, you can start building your own Nuxt 3 apps and take advantage of the benefits it provides, such as performance optimization, automatic code splitting, and server-side rendering.

Keep in mind that this is just the beginning of your Nuxt 3 journey. Nuxt 3 has many more features and capabilities that can help you build powerful and scalable web applications. As you continue to learn and explore Nuxt 3, you'll discover new ways to leverage its features and take your web development skills to the next level.

I hope this guide has been helpful in getting you started with Nuxt 3. If you have any questions or comments, please feel free to leave them below. Good luck on your journey to becoming a Nuxt 3 developer!