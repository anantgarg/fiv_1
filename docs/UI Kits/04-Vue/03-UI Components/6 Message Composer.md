
`CometChatMessageComposer` is an independent and important component that allows users to send various types of messages includes text, image, video and custom messages.

It supports the following features:

- ❤️ **Live Reaction -** Allow users to share reaction on their chat.
- ⭐ **Attachments** - Shows BottomSheet to display list of attachments.
- ⌨️ **Typing events** - Handles typing indicator internally.
- ✍️ **Editing messages** - Includes view used to "Edit" or "Reply" to a specific message.
- 🎤 **Voice Notes -** On click of Mic audio recording gets started and once it get finished, user will have option to either send it or delete it.
- ↩️ **Replies** - Allow users to share their reply on any type of messages.


![](https://uploads.developerhub.io/prod/x9W8/nq7ohymd1aaequvlappa9i2qnddplb6sdh1lhe5dkkc3pacn1f6do46fl91psga4.png)


---

## Properties


| Properties | Description | 
| ---- | ---- | 
| user | Sets the User object in message composer to send the message | 
| group | Sets the Group object in message composer to send the message | 
| background | Sets background in the message composer | 
| hideAttachment | Hides attachment button in the message composer | 
| hideEmoji | Hides emoji option in the message composer | 
| messageFilterList | Sets the message templates to filter the message composer | 


---

## Uses


```javascript
import React from "react";
import {
  CometChatMessageComposer, 
  CometChatMessageTemplate, 
  CometChatMessageTypes,
	CometChatMessageOptions
} from "cometchat-react-ui-kit";
import imageMessageIcon from "assets";

const App = props => {
  
  const imageMessage = new CometChatMessageTemplate({
		type: CometChatMessageTypes.image,
		icon: imageMessageIcon,
		name: "Image",
		options: [CometChatMessageOptions.edit, CometChatMessageOptions.delete],
	});
  const messageFilterList = [imageMessage];
  
  return (
  	<CometChatMessageComposer 
    group={{guid: "supergroup"}} 
  	messageFilterList={messageFilterList} 
		liveReaction="❤️" _>
  )
}
```




---

