`CometChatConversations` is a independent component used to set up a screen that shows the recent conversations and gives them the ability to search for a specific conversation. On slide of each conversation, "_Delete_" option is shown that is used to delete specific conversation.

`CometChatConversations` sets up the following functionality internally:

- Header with customizable title.
- List of recent conversations with pagination.
- Delete Conversation Option on the slide of specific conversation.

It includes all the business logic and options to customize the UI according to our default design system.

![](https://res.cloudinary.com/developerhub/image/upload/v1645041528/v2_5163/hix3bhsmxclnhsngsqrc.png)

`CometChatConversations` is a container component that wraps and formats the `CometChatListBase` and `CometChatConversationList` component with no behaviour of its own.

---

## Launch Conversations

To launch `CometChatConversations`, you will be able to launch it using below code snippet.

```javascript
import React from "react";
import { CometChatConversations } from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatConversations title="Recent Chats" conversationType="both" _>
  )
}
```



---

## Events

`CometChatConversations` provides the following event listeners which will allow you to provide callbacks with custom functionality.

To listen to those events provided by `CometChatConversations` user must use CometChatConversationEvents.

| Name | Description | 
| ---- | ---- | 
| `onItemClick` | When the user clicks on a particular conversation. | 
| `onDeleteConversation` | When the user deletes a particular conversation. | 
| onError | When an error is encountered | 


```javascript
import { CometChatConversationEvents } from "cometchat-react-ui-kit";

CometChatConversationEvents.addListener(CometChatConversationEvents.onDeleteConversation, listenerID, callback);
```

