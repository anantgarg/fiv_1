Using Vue UI Kit, you can integrate your Nuxt.js application with CometChat.

## Pre-requisites

#### First, if not already installed, add Vue from your terminal using the following command.

```javascript
npm install vue
```



## Install CometChat SDK

use the following command

```javascript
npm install @cometchat-pro_chat@3.0.5 --save
```



## Include Vue UI Kit

```javascript
git clone https:__github.com_cometchat-pro_cometchat-pro-vue-ui-kit.git
```



- Copy the cloned repository to your **pages** folder
- Copy all the dependencies from package.json into your project's package.js and install them

## Build Chat component

### Create _`Chat.vue`_ file in your **pages** folder with the following code

```javascript
<template>
    <client-only>
        <CometChatNoSSR><_CometChatNoSSR>
    <_client-only>
<_template>
<script>
export default {
    name: "RTBChat",
    ssr: false,
    components: {
        'CometChatNoSSR': () => import('.._CometChatNoSSR.vue')
    },
    mounted() {
        window.CometChat = require('@cometchat-pro_chat').CometChat
    }
}
<_script>
```



> Replace APP_ID, REGION, and AUTH_KEY with your CometChat App ID, Region, and in the below code.

### Create `consts.js` file with ComeChat details at `root` level

```javascript
module.exports = {
  APP_ID: "APP_ID",
  REGION: "REGION",
  AUTH_KEY: "AUTH_KEY"
}
```



### Create `CometChatNoSSR.vue` component at **`root `**level

> Replace UID in the below code.

```javascript
<template>
  <div
    v-if="Object.keys(user).length"
    :style="{ width: `100%`, height: '100vh' }">
    <client-only>
      <comet-chat-uI _>
    <_client-only>
  <_div>
<_template>

<script>
import { CometChatUI } from "._cometchat-pro-vue-ui-kit_CometChatWorkspace_src";
import { COMETCHAT_CONSTANTS } from '._CONSTS';

export default {
  name: "CommetChat",
  ssr: false,
  components: {
    CometChatUI,
  },
  data: () => ({
    user: {},
    chatId: COMETCHAT_CONSTANTS.APP_ID,
    region: COMETCHAT_CONSTANTS.REGION,
    authKey: COMETCHAT_CONSTANTS.AUTH_KEY,
  }),
  mounted() {
    const appSetting = new window.CometChat.AppSettingsBuilder()
      .subscribePresenceForAllUsers()
      .setRegion(this.region)
      .build();
    window.CometChat.init(this.chatId, appSetting)
      .then(() => {
        const UID = "SUPERHERO1";
        const apiKey = this.authKey;
        window.CometChat.login(UID, apiKey)
          .then((user) => {
            this.user = user;
            console.log(user);
          })
          .catch((error) => console.log("Login failed with exception:", error));
        __ You can now call login function.
      })
      .catch((error) =>
        console.log("Initialization failed with error:", error)
      );
  },
};
<_script>
```



#### Add Webpack config to compile sound files in nuxt.config.js

```javascript
build: {
    extend(config, ctx) {
      config.module.rules.push({
        test: _\\.(ogg|mp3|wav|mpe?g)$_i,
        loader: 'file-loader',
        options: {
          name: '[path][name].[ext]'
        }
      })
    },
}
```

