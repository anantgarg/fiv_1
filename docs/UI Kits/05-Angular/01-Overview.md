---
sidebar_position: 1
title: Overview
slug: /
---

> V4 UI kits offer modular design, extended functionality & > customization for a tailored chat experience. Check out our new UIKits [here](https://www.cometchat.com/docs/v4/angular-uikit/overview).

The CometChat Angular Chat UI Kit lets developers easily add an Angular chat app with text, voice & video to your mobile or desktop web applications. Included are fully polished Angular chat UI components and the complete business logic.

![Angular UI Kit](https://res.cloudinary.com/developerhub/image/upload/v1623200223/v2_5163/qpkpxzv4jsedqawi4fjr.png)

The UI Kit’s customizable Angular chat UI components simplify the process of integrating text chat and voice/video calling features to your website or mobile application in a few minutes.

<div style={{display: 'flex', boxShadow: '0 0 4px 0 rgb(0 0 0 / 18%)', borderRadius: '3px'}}>
  <div style={{padding: '24px'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to checkout Angular UI Kit</h4>
    <p>Follow the steps mentioned in the <code>README.md</code> file.</p>
    <p>Kindly, click on below button to download our Angular UI Kit.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/cometchat-pro-angular-ui-kit/archive/v3.zip">Angular UI Kit</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/cometchat-pro-angular-ui-kit/tree/v3" target="_blank">View on Github</a>
  </div>
  <div style={{padding: '24px', borderLeft: '1px solid #e3e5e7'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to explore the sample app</h4>
    <p>Kindly, click on below button to download our Angular Sample App.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/javascript-angular-chat-app/archive/v3.zip">Angular Sample App</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/javascript-angular-chat-app/tree/v3" target="_blank">View on Github</a>
  </div>
</div>


## Prerequisites

1. A text editor. (e.g. Visual Studio Code, Notepad++, Sublime Text, Atom, or VIM)
2. [Node](https://nodejs.org/en/)
3. [npm](https://www.npmjs.com/get-npm)
4. [Angular CLI](https://angular.io/cli)

```none
npm install -g @angular_cli
```



## Installing the Angular Chat UI Kit

> Please follow the steps provided in the [Key Concepts](https://www.cometchat.com/docs/v3/more/key-concepts) to create V3 apps before you proceed.

### Setup

1. Register on CometChat
    1. To install the Angular Chat UI components, you need to first register on the CometChat Dashboard. Click [here](https://app.cometchat.com) to sign up 

2. Get Your Application Keys 🔑
    - Create a new app
    - Head over to the QuickStart or API & Auth Keys section and note the App ID, Auth Key, and Region.

3. Add the CometChat Dependency

```javascript
npm install @cometchat-pro_chat@3.0.6 --save
```



> Please install `postcss` package using the below command if the Angular version of your project is 11.

```javascript
npm install --save postcss@8.4.27
```



### Configure CometChat inside your Angular app

- Import CometChat SDK

```javascript
import { CometChat } from "@cometchat-pro_chat";
```



- Initialize CometChat 🌟

The `init()` method initializes the settings required for CometChat. We suggest calling the `init()` method on app startup, i.e main.ts file of the application.

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
  (error) => {
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

This method takes UID and Auth Key as input parameters and returns the User object containing all the information of the logged-in user

```javascript
const authKey = "AUTH_KEY";
const uid = "SUPERHERO1";

CometChat.login(uid, authKey).then(
  (user) => {
    console.log("Login Successful:", { user });
  },
  (error) => {
    console.log("Login failed with exception:", { error });
  }
);
```



> Replace AUTH_KEY with your CometChat Auth Key in the above code.

> We have set up 5 users for testing having UIDs: SUPERHERO1, SUPERHERO2, SUPERHERO3, SUPERHERO4, and SUPERHERO5.> > We have used uid SUPERHERO1 as an example here. You can create a User from CometChat Dashboard as well.

### Add the Angular Chat UI components to your project

- Clone the repository

```none
git clone https:__github.com_cometchat-pro_cometchat-pro-angular-ui-kit.git
```



- Copy the cloned repository into your project src folder.

![Folder structure of Angular Sample App](https://res.cloudinary.com/developerhub/image/upload/v1638284257/v2_5163/oncqamu1oeosonf2vnwz.png)

- Import the Components in the respective module where the component will be used.
- Install @ctrl/ngx-emoji-mart according to the angular version of your project @ctrl/ngx-emoji-mart
- Add these styles to your angular.json
- Wrap all the selectors in a div with class=responsive as shown in the next step

```javascript
"styles": [
  "node_modules_@ctrl_ngx-emoji-mart_picker.css",
  "src_cometchat-pro-angular-ui-kit_CometChatWorkspace_src_css_styles.scss"
]
```



### Launch CometChat

CometChatUI is an option to launch a fully functional chat application using the Angular Chat UI Kit. In UI Kit all the UI Components are interlinked and work together to launch a fully functional chat on your website/application.

![CometChatUI](https://res.cloudinary.com/developerhub/image/upload/v1623200230/v2_5163/mt00pg6yda8ejckg9exp.gif)

### Usage

```html
import { CometChatUI } from ".._components_CometChatUI_CometChat-Ui_cometchat-ui.module";

#Use this selector in your html file

<div class="responsive">
  <CometChatUI><_CometChatUI>
<_div>
```



## See our Angular Chat sample app

Visit our [Angular chat sample app](https://github.com/cometchat-pro/javascript-angular-chat-app) repo to see a UI with all the Angular chat components in action.