
# <img src="https://cdn.glitch.com/b75055dd-03c2-47e5-9f5d-7923ac439cc1%2Ffirebaselogo.png?1554747103332" height="60">FireBase in 5 Minutes


<!-- Place an a Screen Shoot of the app above this sentence. -->
Firebase is a mobile and web application development platform developed by Firebase, Inc. in 2011, then acquired by Google in 2014. As of October 2018, the Firebase platform has 18 products, which are used by 1.5 million apps.



## Weaknesses
Shared data between used will not be updated right away for all users unless specified.
JSON objects can be nested 32 levels deep so navigating the database can be difficult
Not adapted by big enterprises yet

## Strengths
Data is nosql ( tree structure) which allows it to access the data extremely quickly.
Firebase authentication is built on  auth 2.0 so apps can handle email, password combinations, and oauth tokens ( also from other authorized providers) securely.
Ability to configure security and data modeling in a console.
Ability to implement microservices with NodeJS (called functions in firebase)



## Prerequisites:
<!-- Make Sure to Change the links below -->

Before you begin, you'll need a JavaScript (web or Node.js) app to add Firebase to. If you don't have an app already, you can download one of the Firebase's [Quickstart samples.](https://firebase.google.com/docs/samples/?hl=th#web)


# Add Firebase to your app
To add Firebase to your app, you'll need a Firebase project and a short snippet of initialization code that has a few details about your project.

1. Create a Firebase project in the [Firebase Console.](https://console.firebase.google.com/u/0/?hl=th&pli=1) 
- If you don't have an existing Firebase project, click Add project, then enter either an existing Google Cloud Platform project name or a new project name.
- If you have an existing Firebase project that you'd like to use, select that project from the console.

2. From the project overview page in the [Firebase console](https://console.firebase.google.com/u/0/?hl=th&pli=1) , click Add Firebase to your web app. If your project already has an app, select Add App from the project overview page.

3. Copy and paste your project's customized code snippet in the <head> tag of your page, before other script tags.

## Below is an example initialization code snippet:


<img src='https://cdn.glitch.com/b75055dd-03c2-47e5-9f5d-7923ac439cc1%2FFireBaseSDK.png?1554745322717' height='500'>







# Run a local web server for development

If you're building a web app, some parts of the Firebase JavaScript SDK require that your web app be served from a server rather than from the local filesystem. You can use the Firebase CLI to run a local server like this:

```
$ npm install -g firebase-tools
$ firebase init    # Generate a firebase.json (REQUIRED)
$ firebase serve   # Start development server`
```


# Host your web app using Firebase Hosting

If you're building a web app and your web app is entirely static content, you can deploy it using [Firebase Hosting.](https://firebase.google.com/docs/hosting/).

Firebase Hosting is a developer-focused static web hosting for modern front-end web applications. Using Firebase Hosting, you can deploy SSL-enabled web apps to your own domain on a global content delivery network (CDN) using a single command.


## SDK imports and implicit initialization

Web apps hosted with Firebase Hosting can benefit from [simpler project configuration](https://firebase.google.com/docs/hosting/). Paste the following code snippets into your application HTML to import the Firebase SDK and configure it automatically for the project your app is hosted on:


```
    <!-- Firebase App is always required and must be first -->
    <script src="/__/firebase/5.9.3/firebase-app.js"></script>

    <!-- Add additional services that you want to use -->
    <script src="/__/firebase/5.9.3/firebase-auth.js"></script>
    <script src="/__/firebase/5.9.3/firebase-database.js"></script>
    <script src="/__/firebase/5.9.3/firebase-messaging.js"></script>
    <script src="/__/firebase/5.9.3/firebase-functions.js"></script>

    <!-- Comment out (or don't include) services that you don't want to use -->
    <!-- <script src="/__/firebase/5.9.3/firebase-storage.js"></script> -->

    <script src="/__/firebase/init.js"></script>

```


## Initialize multiple apps


In most cases, you only have to initialize a single, default app. You can access services from that app in two equivalent ways:

```
// Initialize the default app
var defaultApp = firebase.initializeApp(defaultAppConfig);

console.log(defaultApp.name);  // "[DEFAULT]"

// You can retrieve services via the defaultApp variable...
var defaultStorage = defaultApp.storage();
var defaultDatabase = defaultApp.database();

// ... or you can use the equivalent shorthand notation
defaultStorage = firebase.storage();
defaultDatabase = firebase.database();

```


Some use cases require you to create multiple apps at the same time. For example, you might want to read data from the Realtime Database of one Firebase project and store files in another project. Or you might want to authenticate one app while have another app be unauthenticated. The Firebase SDK allows you to create multiple apps at the same time, each with their own configuration information.


```

// Initialize the default app
firebase.initializeApp(defaultAppConfig);

// Initialize another app with a different config
var otherApp = firebase.initializeApp(otherAppConfig, "other");

console.log(firebase.app().name);  // "[DEFAULT]"
console.log(otherApp.name);        // "other"

// Use the shorthand notation to retrieve the default app's services
var defaultStorage = firebase.storage();
var defaultDatabase = firebase.database();

// Use the otherApp variable to retrieve the other app's services
var otherStorage = otherApp.storage();
var otherDatabase = otherApp.database();
```

## Next steps

Learn about Firebase:

- Explore [sample Firebase apps] (https://firebase.google.com/docs/samples/)
- Get hands-on experience with the [Firebase Web Codelab.](https://codelabs.developers.google.com/codelabs/firebase-web/)
- Explore the [open source code in GitHub](https://github.com/firebase/firebase-js-sdk)

