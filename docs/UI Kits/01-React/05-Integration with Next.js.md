---
sidebar_position: 5
title: Integration with Next.js
slug: /integration-with-nextjs
---

Using React UI Kit, you can integrate your Next.js application with CometChat.

## Pre-requisites

#### First, if not already installed, add React and React DOM from your terminal using the following command.

```javascript
npm install react@17.0.2, react-dom@17.0.2
```



## Install CometChat SDK

use the following command

```javascript
npm install @cometchat-pro_chat@3.0.10 --save
```



## Include React UI Kit

```javascript
git clone https:__github.com_cometchat-pro_cometchat-pro-react-ui-kit.git
```



- Copy the cloned repository to your **root** folder
- Copy all the dependencies from package.json into your project's package.js and install them

## Build Chat component

### Create _`chat.js`_ file in your **pages** folder with the following code

```javascript
import dynamic from "next_dynamic";
import { useEffect } from "react";

const CometChatNoSSR = dynamic(
    () => import('.._CometChatNoSSR'),
    { ssr: false }
);

function Chat() {

    useEffect(() => {
        window.CometChat = require('@cometchat-pro_chat').CometChat
    });

    return (
        <div><CometChatNoSSR _><_div>
    )
}

export default Chat;
```



> Replace APP_ID, REGION, and AUTH_KEY with your CometChat App ID, Region, and in the below code.

### Create `consts.js` file with ComeChat details in your **root** folder

```javascript
module.exports = {
  APP_ID: "APP_ID",
  REGION: "REGION",
  AUTH_KEY: "AUTH_KEY"
}
```



### Create `CometChatNoSSR` component in your **root** folder

> Replace UID in the below code.

```javascript
import { Component } from "react";
import consts from '._consts';
import { CometChatUI } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src_components_index"

export default class CometChatNoSSR extends Component {
    constructor(props) {
        super(props);
        this.state = {
            user: undefined
        }
    }
    componentDidMount() {
      
      _**
      Initialize CometChat
      *_
      let appSetting = new 	      CometChat.AppSettingsBuilder().subscribePresenceForAllUsers().setRegion(consts.REGION).build();
      CometChat.init(consts.APP_ID, appSetting).then(
        () => {
          
          _**
          *Log in user
          *_
          const UID = "SUPERHERO1";
          const authKey = consts.AUTH_KEY;
          CometChat.login(UID, authKey).then(
            user => {
              this.setState({ user })
            },
            error => {
              console.log("Login failed with exception:", {
                error
              });
            }
          );
        },
        error => {
          console.log("Initialization failed with error:", error);
          __ Check the reason for error and take appropriate action.
        }
      );
    }
    render() {
        _**
        Rendering CometChatUI  component of React UIKit
        **_
        if (this.state.user) {
            return (
                <div style={{ width: "100vw", height: "100vh" }}><CometChatUI _><_div>
            );
        } else {
            return (<div>Loading...<_div>);
        }
    }
}
```



### Import images in your Next.js project

```javascript
module.exports = {
	images: {
    	disableStaticImages: true
  	},
	webpack: (config, options) => {
		const { isServer } = options;
		config.module.rules.push({
			test: _\\.(wav|mp3|ogg|mpe?g|png|jpe?g|gif|svg)$_i,
			exclude: config.exclude,
			use: [
				{
					loader: require.resolve("file-loader"),
					options: {
						limit: 10000,
						fallback: require.resolve("url-loader"),
						publicPath: `_next_static_images_`,
						outputPath: `${isServer ? ".._" : ""}static_images_`,
						name: "[name]-[hash].[ext]",
						esModule: config.esModule || false,
					},
				},
			],
		});
		return config;			
	},
};
```



## Disable strict mode

If you are using React v18, make sure to disable strict mode in the next config to circumvent the re-render issue. Read more about the re-render issue [here](https://github.com/vercel/next.js/issues/35822).

```javascript
module.exports = {
  reactStrictMode: false
}
```

