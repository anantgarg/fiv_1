`CometChatMessages` displays the chat window either for `User` or `Group` entities, and shows the list of messages where the loggedInUser has sent and received from either of the entities.

![](https://res.cloudinary.com/developerhub/image/upload/v1645041432/v2_5163/buidwx9otz4fmlwpxp3s.png)

---

It provides you with the following features:

- **CometChatMessageHeader**: Displays name of the user or group along with avatar.
- **CometChatMessageList**: Shows a paginated list of messages that are sent or received by logged-in user. It also displays empty or loading state, if the data is not available. It also sets up action handlers and displays a button for quick scroll to bottom action.
- **CometChatMessageComposer**: Handles message input, attachments to share different types of messages like Whiteboard, Stickers, Polls, etc. It also includes features like Live Reactions.

---

## Launch Messages

You will be able to launch `CometChatMessages` using below code snippet.

```javascript
import React from "react";
import {CometChatMessages} from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatMessages user={{uid: "superhero1"}} liveReaction="❤️" hideEmoji="false" _>
  )
}
```

```javascript
import React from "react";
import {CometChatMessages} from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatMessages group={{guid: "supergroup"}} liveReaction="❤️" hideEmoji="false" _>
  )
}
```



---

## Events

CometChatMessages provides event listeners so that you can setup functions whenever the specified event is dispatched.

```javascript
import { CometChatMessageEvents } from "cometchat-react-ui-kit";

CometChatMessageEvents.addListener(CometChatMessageEvents.onMessageSent, listenerID, callback);
```



| Event | Description | 
| ---- | ---- | 
| `onMessageSent` | Triggers when the user sends a text/media/custom message | 
| `onLiveReaction` | Triggers when the user clicks on the live reaction button i.e heart icon | 
| `onMessageError` | Triggers when an error occurs in sending a message | 
