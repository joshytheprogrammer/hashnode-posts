---
title: "Building a Full-Stack Web App with Nuxt 3 and Firebase"
datePublished: Sat Apr 01 2023 12:21:42 GMT+0000 (Coordinated Universal Time)
cuid: clfxy0o20000209ldac3ocfos
slug: building-a-full-stack-web-app-with-nuxt-3-and-firebase
tags: javascript, firebase, web-development, vuejs, firestore

---

Nuxt.js is a popular open-source framework for building Vue.js applications. It provides developers with an easy-to-use and flexible environment for building powerful web applications. Firebase is a powerful platform that provides backend services for web and mobile applications. In this tutorial, we will explore how to set up Nuxt.js 3 with Firebase, to build a full-stack web application.

## Prerequisites

Before we get started, we need to ensure that we have the following prerequisites installed:

* Node.js v14 or higher
    
* NPM v6 or higher
    
* A Firebase account
    

## Setting up a Firebase project

The first step is to set up a Firebase project. If you haven't already done so, head over to the Firebase console and create a new project. Once you have created a project, go to the project settings and click on the "Add app" button. Choose the "Web" option, and give your app a name.

After you have created a new app, Firebase will provide you with a configuration object that contains all the necessary configuration options for your app. We will use this configuration object later in our Nuxt.js application.

## Creating a new Nuxt.js project

Next, we need to create a new Nuxt.js project. We can do this by running the following command:

```bash
npx create-nuxt-app my-nuxt-firebase-app
```

This command will create a new Nuxt.js project in a directory named `my-nuxt-firebase-app`. During the setup process, we will be prompted to select various options for our project. Make sure to choose the "Universal" option, which will generate a server-side rendered application.

## Installing Firebase

Now that we have our Nuxt.js project set up, we can install the Firebase SDK. We can do this by running the following command:

```bash
npm install --save firebase
```

This command will install the Firebase SDK and add it as a dependency to our project.

## Configuring Firebase in Nuxt.js

Next, we need to configure Firebase in our Nuxt.js application. To do this, we need to create a new file named `firebase.js` in the `plugins` directory of our project. This file should contain the following code:

```javascript
import firebase from 'firebase/app'
import 'firebase/auth'
import 'firebase/firestore'
import 'firebase/storage'

const firebaseConfig = {
  // Your firebase configuration object goes here
}

if (!firebase.apps.length) {
  firebase.initializeApp(firebaseConfig)
}

export const auth = firebase.auth()
export const db = firebase.firestore()
export const storage = firebase.storage()
```

Make sure to replace the `firebaseConfig` object with the configuration object that Firebase provided you with earlier.

## Using Firebase in Nuxt.js

Now that we have Firebase set up in our Nuxt.js application, we can use it to build our application. For example, we can use Firebase authentication to authenticate users and Firebase Firestore to store and retrieve data.

To use Firebase authentication, we can import the `auth` object from our `firebase.js` file and use it to sign users in and out. For example:

```javascript
import { auth } from '@/plugins/firebase'

// Sign in
auth.signInWithEmailAndPassword(email, password)

// Sign out
auth.signOut()
```

To use Firebase Firestore, we can import the `db` object from our `firebase.js` file and use it to store and retrieve data. For example:

```javascript
import { db } from '@/plugins/firebase'

// Add a document to a collection
db.collection('users').add({
  name: 'John Doe',
  email: 'john.doe@example.com'
})

// Retrieve a collection of documents
db.collection('users').get()
  .then(querySnapshot => {
    querySnapshot.forEach(doc => {
      console.log(doc.id, doc.data())
    })
  })
```

## Conclusion

In conclusion, setting up a Nuxt.js 3 application with Firebase is a straightforward process that can be accomplished with just a few steps. By following the steps outlined in this tutorial, you should now have a basic understanding of how to configure Firebase in a Nuxt.js application and how to use Firebase services such as authentication and Firestore to build a full-stack web application. We hope that this tutorial has been helpful in getting you started with Nuxt.js and Firebase, and we encourage you to continue exploring these powerful technologies in your future projects.