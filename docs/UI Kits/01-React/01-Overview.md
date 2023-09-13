---
sidebar_position: 1
title: Overview
slug: /
---

> V4 UI kits offer modular design, extended functionality & customization for a tailored chat experience. Check out our new UIKits [here](https://www.cometchat.com/docs/v4/react-uikit/overview).

Our React Chat UI Kit lets developers easily add text, voice & video to your website. It a fully polished UI and the complete business logic.

Don't forget to check out the [Key Concepts](https://www.cometchat.com/docs/v3/react-chat-ui-kit/key-concepts) for your React Chat UI Kit before proceeding.

![React UI Kit](https://res.cloudinary.com/developerhub/image/upload/v1623200296/v2_5163/jrrjch0lwgudmrdz34rw.png)

> - Seamless scaling to over 1M+ concurrent users> - Faster connection & response times> - Higher rate limits> - Supports up to 100K users in a group> - Unlimited groups> - Support for Transient Messages> - Real-time user & group members count> - And more!

CometChat's React UI Kit’s customizable UI components simplify the process of integrating text chat and voice/video calling features to your website or mobile application in a few minutes.

<div style={{display:'flex', boxShadow: '0 0 4px 0 rgb(0 0 0 / 18%)', borderRadius: '3px'}}>
  <div style={{padding: '24px'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to checkout React UI Kit</h4>
    <p>Follow the steps mentioned in the <code>README.md</code> file.</p>
    <p>Kindly, click on below button to download our React UI Kit.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/cometchat-pro-react-ui-kit/archive/master.zip">React UI Kit</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/cometchat-pro-react-ui-kit" target="_blank">View on Github</a>
  </div>
  <div style={{padding: '24px', borderLeft: '1px solid #e3e5e7'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to explore the sample app</h4>
    <p>Kindly, click on below button to download our React Sample App.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/javascript-react-chat-app/archive/master.zip">React Sample App</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/javascript-react-chat-app" target="_blank">View on Github</a>
  </div>
</div>

## Prerequisites

Before you begin, ensure you have met the following requirements:

1. A text editor. (e.g. Visual Studio Code, Notepad++, Sublime Text, Atom, or VIM)
2. [Node](https://nodejs.org/en/)
3. [npm](https://www.npmjs.com/get-npm)
4. [React](https://reactjs.org/)

```javascript
npm install react@17.0.2
```



5. [React DOM](https://reactjs.org/docs/react-dom.html)

```javascript
npm install react-dom@17.0.2
```



6. [React Scripts](https://www.npmjs.com/package/react-scripts)

```javascript
npm install react-scripts@4.0.3
```



## Installing the React Chat UI Kit

> Please follow the steps provided in the [Key Concepts](https://www.cometchat.com/docs/v3/more/key-concepts) to create V3 apps before you proceed.

### Setup

1. Register on CometChat
    - To install React UI Kit, you need to first register on the CometChat Dashboard. Click [here](https://app.cometchat.com) to Sign Up.

2. Get your application keys
    - Create a new app.
    - Head over to the QuickStart or API & Auth Keys section and note the App ID, Auth Key, and Region.

3. Add the CometChat dependency

```javascript
npm install @cometchat-pro_chat@3.0.11 --save
```



### Configure CometChat inside your app

- Import CometChat SDK

```javascript
import { CometChat } from "@cometchat-pro_chat";
```



- Initialize CometChat 

The init() method initializes the settings required for CometChat.
We suggest calling the init() method on app startup, preferably in the index.js file.

```javascript
const appID = "APP_ID";
const region = "REGION";
const appSetting = new CometChat.AppSettingsBuilder().subscribePresenceForAllUsers().setRegion(region).build();
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



> Replace APP_ID and REGION with your CometChat App ID and Region in the above code.

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

- Login your user 

This method takes `UID` and `Auth Key` as input parameters and returns the User object containing all the information of the logged-in user.

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

### Add the React UI Kit to your project

- Clone this repository

```javascript
git clone https:__github.com_cometchat-pro_cometchat-pro-react-ui-kit.git
```



- Copy the cloned repository to your source folder

![Folder structure of React Sample App](https://uploads.developerhub.io/prod/x9W8/5p1s5fydgt07yucxkvc52f3eb71ggc3b2fxpxbxrtqjwlu6ucprecaafptqsubcv.png)

- Copy all the dependencies from package.json into your project's package.json and install them

![package.json of React UI Kit](https://uploads.developerhub.io/prod/x9W8/n4xhanpy3xmvh13e5qh2hk84kojuiotug2silsban3mju3g9rezxm3m3cr8jvn22.png)

### Launch CometChat

Using the CometChatUI component, you can launch a fully functional chat application. In this component, all the UI Screens and UI Components are interlinked and work together to launch a fully functional chat on your website/application.

![CometChatUI](https://res.cloudinary.com/developerhub/image/upload/v1623200307/v2_5163/gdnggnv0jdt90jldpbox.gif)

### Usage

```javascript
import { CometChatUI } from "._CometChatWorkspace_src";

class App extends React.Component {
  
  render() {

    return (
      <div style={{width: '800px', height:'800px' }}>
      	<CometChatUI _>
      <_div>
	);
	}
}
```



## Check out our React chat sample app

Visit our [React sample app](https://github.com/cometchat-pro/javascript-react-chat-app) repository to run the sample app yourself.