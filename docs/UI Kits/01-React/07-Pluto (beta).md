---
sidebar_position: 7
title: Pluto(beta)
slug: /pluto
---

## Overview

**Pluto UIKit for React** is a set of prebuilt UI components that allow you to easily craft an in-app chat system with all the essential messaging features. Our new UI kit is divided into multiple smaller modules and components and each and every component is customizable using **Theme & Configurations.**You can customize these components to create an interactive messaging interface unique to your brand identity.

---

## Requirements

The minimum requirements for UI Kit for React are:

- `React 17.0.2`
- `React DOM 17.0.2`
- `CometChatPro Chat SDK for JavaScript 3.0.0 and later`

## Before you begin

Before installing CometChatPro Javascript SDK, you need to create a CometChat application on the [CometChatPro](https://app.cometchat.com/)[ Dashboard](https://dashboard.sendbird.com/), which comprises everything required in a chat service including users, groups, calls & messages. You will need the `App ID` , `AuthKey`, `Region` of your CometChat application when initializing the SDK.

> **Note**: Each CometChat application can be integrated with a single client app. Within the same application, users can communicate with each other across all platforms, whether they are on mobile devices or on the web.

---

## Get started

You can start building a modern messaging experience in your app by installing Pluto UIKit. The minimum requirement of Chat SDK for JavaScript is 3.0.0 or later.

---

## Install UI Kit

You can install UI Kit for React through [**npm**](https://www.npmjs.com/package/cometchat-react-ui-kit). 

Enter the following code on the command line.

#### Install with npm

```javascript
npm install @cometchat-pro_chat cometchat-react-ui-kit
```



#### Install with yarn

```javascript
yarn add @cometchat-pro_chat cometchat-react-ui-kit
```



---

### Configure CometChat inside your app

**i. Initialize CometChat 🎬**

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



The `init()` method initializes the settings required for CometChat. We suggest calling the `init()` method on app startup, preferably in the index.js file.

**ii. Log in your User**👤

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



The `login()` method returns the User object containing all the information of the `logged-in user.`

> Replace AUTH_KEY with your CometChat Auth Key in the above code.

> - We have set up five users for testing with the following UIDs: SUPERHERO1, SUPERHERO2, SUPERHERO3, SUPERHERO4, and SUPERHERO5.> - We have used uid SUPERHERO1 as an example here. You can create a User from CometChat Dashboard as well.

---

## UI Components

UIKit is a set of prebuilt UI components that allows you to easily craft an in-app chat system with all the essential messaging features. [Learn more about all UI Components](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversations).

It provides the following components:

| Component | Description |  | 
| ---- | ---- | ---- | 
| **`CometChatConversations`** | `CometChatConversations`  displays the `User` or `Group` entities in the list where those entities are interacted with the `loggedInUser` in recent time. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversations) | 
| **`CometChatMessages`** | `CometChatMessages` displays the chat window for the `User` or `Group` entities where it shows the list of messages. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/messages) | 


---

## UI Components Configuration

Each UI Component is configured using configuration objects. [Learn more about how to use configurations on UI Components.](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/configurations)