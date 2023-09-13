
`CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. It can contain the following list of possible messages:

- Text messages and Rich Media if text contains URL.
- Attachments (media or file) message.
- Location Sharing
- Collaborative Whiteboard & Document.
- Stickers
- Deleted message (only for current user)
- Sentiment Analysis (e.g. autoblocked message with inappropriate content)
- System message (e.g. some user joined a channel)
- Giphy preview
- Date separator
- Optimistic UI


![](https://uploads.developerhub.io/prod/x9W8/00vut21gw2wzio3tuq0u2l32ilj61zztioedsbwcl9ysfyw49om7icxtwss2eby2.png)


---

## Properties


| Props | Description | 
| ---- | ---- | 
| user | Sets the `User` object in message list to fetch recent list of messages | 
| group | Sets the `Group` object in message list to fetch recent list of messages | 
| background | Sets background in message list | 
| messageAlignment | Sets alignment of the message bubbles to either leftAligned or standard format | 


---

## Uses


```javascript
import React from "react";
import {CometChatMessageList} from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatMessageList user={{uid: "superhero1"}} messageAlignment="standard" _>
  )
}
```




---

