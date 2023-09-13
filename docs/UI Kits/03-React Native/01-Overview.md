---
sidebar_position: 1
title: Overview
slug: /
---

> V4 UI kits offer modular design, extended functionality & > customization for a tailored chat experience. Check out our new UIKits [here](https://www.cometchat.com/docs/v3/react-native-v4-uikit/overview).

The CometChat React Native UI Kit cuts development efforts significantly when integrating text, voice and video messaging into your React Native chat application. 

![React Native Ui Kit](https://res.cloudinary.com/developerhub/image/upload/v1631680113/v2_5163/ro4tukkcu4rijkinwtp6.png)

The React Native UI Kit’s customizable React Native chat UI components simplify the process of integrating text chat and voice/video calling features to your website or mobile application in a few minutes.

<div style={{display: 'flex', boxShadow: '0 0 4px 0 rgb(0 0 0 / 18%)', borderRadius: '3px'}}>
  <div style={{padding: '24px'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to checkout React Native Chat UI Kit.</h4>
    <p>Follow the steps mentioned in the <code>README.md</code> file.</p>
    <p>Kindly, click on below button to download our React Native Chat UI Kit..</p>
    <p><a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/react-native-chat-ui-kit/archive/v3.zip">React Native Chat UI Kit</a></p>
    <p><a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/react-native-chat-ui-kit/tree/v3" target="_blank">View on Github</a></p>
  </div>
  <div style={{padding: '24px', borderLeft: '1px solid #e3e5e7', justifySelf: 'flex-end'}}>
    <h4 style={{fontWeight: 'bold'}}>I want to explore the sample app</h4>
    <p>Kindly, click on below button to download our React Native Chat Sample App.</p>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%', marginBottom: '8px'}} href="https://github.com/cometchat-pro/react-native-chat-app/archive/v3.zip">React Native Sample App</a>
    <a style={{display: 'inline-block', backgroundColor: '#7c55c9', padding: '8px', textAlign: 'center', textTransform: 'uppercase', border: '1px solid #e3e5e7', borderRadius: '3px', color: 'white', width: '100%'}} href="https://github.com/cometchat-pro/react-native-chat-app/tree/v3" target="_blank">View on Github</a>
  </div>
</div>


## Prerequisites

Before you begin, ensure you have met the following requirements:

1. A text editor. (e.g. Visual Studio Code, Notepad++, Sublime Text, Atom, or VIM)
2. [Node](https://nodejs.org/en/)
3. [npm](https://www.npmjs.com/get-npm)
4. [React-Native](https://reactnative.dev/docs/environment-setup)

## Installing the React Native Chat UI Kit

> Please follow the steps provided in the [Key Concepts](https://www.cometchat.com/docs/v3/more/key-concepts) to create V3 apps before you proceed.

### Setup

1. Register on CometChat
    - To install React Native UI Kit, you need to first register on the CometChat Dashboard. Click [here](https://app.cometchat.com/) to Sign Up.

2. Get your application keys
    - Create a new app.
    - Head over to the QuickStart or API & Auth Keys section and note the App ID, Auth Key, and Region.

3. Add the CometChat dependency

```javascript
npm install @cometchat-pro_react-native-chat@3.0.2 --save
```



Other required dependencies
These packages help make the ui-kit smooth and functioning

```none
react-native-sound
react-native-vector-icons 
react-native-elements 
react-native-fast-image
react-native-image-picker
react-native-document-picker
react-native-gesture-handler
react-native-reanimated
reanimated-bottom-sheet
react-native-video
react-native-video-controls
@react-navigation_bottom-tabs
@react-navigation_native
@react-navigation_stack
@react-native-picker_picker
react-native-async-storage_async-storage
@cometchat-pro_react-native-calls
rn-fetch-blob
react-native-autolink
react-native-screens
emoji-mart-native
react-native-keep-awake
react-native-safe-area-context
react-native-webview
react-native-swipe-list-view
```



### Configure CometChat inside your React Native app

- Initialize CometChat 🌟

The init() method initializes the settings required for CometChat. We suggest calling the init() method on app startup, preferably in the created() method of the Application class.

```javascript
import {CometChat} from '@cometchat-pro_react-native-chat';

const appID = 'APP_ID';
const region = 'REGION';
const appSetting = new CometChat.AppSettingsBuilder()
  .subscribePresenceForAllUsers()
  .setRegion(region)
  .build();
CometChat.init(appID, appSetting).then(
  () => {
    console.log('Initialization completed successfully');
    __ You can now call login function.
  },
  (error) => {
    console.log('Initialization failed with error:', error);
    __ Check the reason for error and take appropriate action.
  },
);
```



> Replace APP_ID and REGION with your CometChat App ID and Region in the above code

- Login your user 👤

This method takes UID and Auth Key as input parameters and returns the User object containing all the information of the logged-in user.

```javascript
import {CometChat} from '@cometchat-pro_react-native-chat';

const authKey = 'AUTH_KEY';
const uid = 'SUPERHERO1';

CometChat.login(uid, authKey).then(
  (user) => {
    console.log('Login Successful:', { user });
  },
  (error) => {
    console.log('Login failed with exception:', { error });
  },
);
```



> Replace AUTH_KEY with your CometChat Auth Key in the above code.

> We have set up 5 users for testing having UIDs: SUPERHERO1, SUPERHERO2, SUPERHERO3, SUPERHERO4, and SUPERHERO5.> > We have used uid SUPERHERO1 as an example here. You can create a User from CometChat Dashboard as well.

### Add the React Native chat UI components to your project

- Clone this repository.

```none
https:__github.com_cometchat-pro_cometchat-pro-react-native-ui-kit.git -b v3
```



- Copy the `cometchat-pro-react-native-ui-kit` folder to your source folder.
- Copy all the peer dependencies from package.json into your project's package.json and install them using npm install

### Launch CometChat

CometChatUI is an option to launch a fully functional chat application using the React Native Chat UI Kit. In CometChatUI all the UI Components are interlinked and work together to launch a fully functional chat on your website/application.

![CometChat UI](https://res.cloudinary.com/developerhub/image/upload/v1631680116/v2_5163/ktdms8zezicpqfsdpufa.png)

```javascript
import React from 'react';
import {View} from 'react-native';
import {CometChatUI} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatUIView() {
  return (
    <View style={{flex: 1}}>
      <CometChatUI _>
    <_View>
  );
}
```



## Check out our React Native sample app

Visit our [React Native repo](https://github.com/cometchat-pro/react-native-chat-app/tree/v3) to run a sample app featuring these React Native chat components.