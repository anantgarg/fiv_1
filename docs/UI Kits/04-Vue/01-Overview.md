---
sidebar_position: 1
title: Overview
slug: /
---

> V4 UI kits offer modular design, extended functionality & > customization for a tailored chat experience. Check out our new UIKits [here](https://www.cometchat.com/docs/v4/vue-uikit/overview).

The CometChat **Vue JS UI Kit** lets developers integrate text chat & voice/video calling features into websites seamlessly. 

![Vue UI Kit](https://res.cloudinary.com/developerhub/image/upload/v1623200343/v2_5163/jkqfzfanhcnfr6clwfal.png)

> Faster connection & response times > Higher rate limits > > Supports up to 100K users in a group > > Unlimited groups > > Support for Transient Messages > > Real-time user & group members count And more!

The Vue Chat UI Kit’s customizable **VueJS UI components** simplify the process of integrating text chat and voice/video calling features to your website in a few minutes.

<div style={{display: 'flex', boxShadow: '0 0 4px 0 rgba(0, 0, 0, 0.18)', borderRadius: '3px'}}>
  <div style={{padding: '24px'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to checkout Vue UI Kit</h4>
    <p>Follow the steps mentioned in the <code>README.md</code> file.</p>
    <p>Kindly, click on below button to download our Vue UI Kit.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/cometchat-pro-vue-ui-kit/archive/master.zip">Vue UI Kit</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/cometchat-pro-vue-ui-kit/" target="_blank">View on Github</a>
  </div>
  <div style={{padding: '24px', borderLeft: '1px solid #e3e5e7'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to explore the sample app</h4>
    <p>Kindly, click on below button to download our Vue Sample App.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/javascript-vue-chat-app/archive/master.zip">Vue Sample App</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/javascript-vue-chat-app/" target="_blank">View on Github</a>
  </div>
</div>


## Prerequisites

Before you begin, ensure you have met the following requirements:

1. A text editor. (e.g. Visual Studio Code, Notepad++, Sublime Text, Atom, or VIM)
2. [Node](https://nodejs.org/en/)
3. [npm](https://www.npmjs.com/get-npm)
4. [Vue](https://vuejs.org/)

For installing Vue 2

```none
npm install vue@2.6.14
```



For installing Vue 3

```none
npm install vue@3.2.11
```



## Installing Vue JS UI Components

> Please follow the steps provided in the [Key Concepts](https://www.cometchat.com/docs/v3/more/key-concepts) to create V3 apps before you proceed.

### Setup

1. Register on CometChat 🔧
    - To install Vue UI Kit, you need to first register on the CometChat Dashboard. Click here to Sign Up.

2. Get your application keys 🔑
    1. Create a new app.
    2. Head over to the QuickStart or API & Auth Keys section and note the App ID, Auth Key, and Region.

3. Add the CometChat dependency 📦

```none
npm install @cometchat-pro_chat@3.0.2-beta1 --save
```



### Configure CometChat inside your app

- Import CometChat SDK

```javascript
import { CometChat } from "@cometchat-pro_chat";
```



- Initialize CometChat 🌟 

The init() method initializes the settings required for CometChat.
We suggest calling the init() method on app startup, preferably in the created() method of the Application class.

```javascript
const appID = "APP_ID";
const region = "REGION";
const appSetting = new CometChat.AppSettingsBuilder()
  .subscribePresenceForAllUsers()
  .setRegion(region)
  .build();

CometChat.init(appID, appSetting).then(
  () => {
    console.log("Initialization completed successfully");
    __ You can now call login function.
  },
  error => {
    console.log("Initialization failed with error:", error);
    __ Check the reason for error and take appropriate action.
  }
);
```



> Replace APP_ID and REGION with your CometChat App ID and Region in the above code

- Create user

This method takes a `User` object and the `Auth Key` as input parameters and returns the created `User` object if the request is successful.

```javascript
let authKey = "AUTH_KEY";
var uid = "user1";
var name = "Kevin";

var user = new CometChat.User(uid);
user.setName(name);
CometChat.createUser(user, authKey).then(
    user => {
        console.log("user created", user);
    },error => {
        console.log("error", error);
    }
)
```



> Replace AUTH_KEY with your CometChat Auth Key in the above code.

- Login your user 👤 

This method takes UID and Auth Key as input parameters and returns the User object containing all the information of the logged-in user.

```javascript
const authKey = "AUTH_KEY";
const uid = "SUPERHERO1";

CometChat.login(uid, authKey).then(
  user => {
    console.log("Login Successful:", { user });    
  },
  error => {
    console.log("Login failed with exception:", { error });    
  }
);
```



> Replace AUTH_KEY with your CometChat Auth Key in the above code.

> We have set up 5 users for testing having UIDs: SUPERHERO1, SUPERHERO2, SUPERHERO3, SUPERHERO4, and SUPERHERO5.> > We have used uid SUPERHERO1 as an example here. You can create a User from CometChat Dashboard as well.

### Add the Vue Chat UI Kit to your project

- Clone this repository.

```none
git clone https:__github.com_cometchat-pro_cometchat-pro-vue-ui-kit.git
```



- Copy the cloned repository to your source folder

![Folder structure of Vue Sample App](https://res.cloudinary.com/developerhub/image/upload/v1631549878/v2_5163/elkw7lqwj2kbnl7ati3s.png)

- Copy all the dependencies from package.json of `cometchat-pro-vue-ui-kit` into your project's package.json and install them.
- We are using [emoji-mart-vue-fast](https://www.npmjs.com/package/emoji-mart-vue-fast) Please install respective library depending on your Vue version
- 
    - For Vue2 : `npm install emoji-mart-vue-fast@7.0.7`
    - For Vue3 : `npm install emoji-mart-vue-fast@8.0.3`
    - For **Vite** users : `npm install emoji-mart-vue-fast@9.1.2`

![package.json of Vue UI Kit](https://res.cloudinary.com/developerhub/image/upload/v1634215228/v2_5163/hvsnc7kgt4bgutrdmomm.png)

### Support for Vite

If you are using Vite, please update your `vite.config.js`

```javascript
import { defineConfig } from 'vite'
import vue from '@vitejs_plugin-vue'

__ https:__vitejs.dev_config_
export default defineConfig({
  plugins: [vue()],
  resolve: {
    extensions: ['.mjs', '.js', '.ts', '.jsx', '.tsx', '.json', '.vue'],
  },
})
```



### Launch CometChat

Using the `CometChatUI` component from the UI Kit, you can launch a fully functional chat application.
In this component, all the UI Components are interlinked and work together to launch a fully functional chat on your website/application.

![CometChatUI](https://res.cloudinary.com/developerhub/image/upload/v1623200351/v2_5163/minarpi5ez3glnw8v9x2.gif)

### Usage

```html
<template>
 <div id="app">
   <CometChatUI _>
 <_div>
<_template>

<script>
 import { CometChatUI } from "._cometchat-pro-vue-ui-kit_CometChatWorkspace_src";
 export default {
   name: "App",
   components: {
     CometChatUI,
   }
 };
<_script>
```



## Checkout our Vue Chat sample app

Visit our [Vue Chat sample app](https://github.com/cometchat-pro/javascript-vue-chat-app) repo to see it in action.