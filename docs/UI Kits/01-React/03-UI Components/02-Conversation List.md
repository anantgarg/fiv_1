This component retrieves the latest conversations that a CometChat logged-in user is a part of.

![](https://res.cloudinary.com/developerhub/image/upload/v1645684153/v2_5163/asjkxzlx05jgoqg31msn.png)

The state of the component is communicated in 3 ways - **empty**, **loading** and **error**.

---

## Properties

## **Background**

The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method.

| Properties | Description | 
| ---- | ---- | 
| `background` | The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/background) | 


## **Conversation Type**

This property will set the **`conversationType`** for the **`ConversationList`** to display as per the user's choice. Users can display users, groups, or both as per the enum value.  When none then it will show both users as well as groups. You will be able to modify the background using the below methods:

| Props | Description | 
| ---- | ---- | 
| `conversationType` | This property sets the mode for the ConversationList to display as per the user's choice. Users can display users, groups, or none as per the enum value.  When none then it will show both users as well as groups | 


---

## Uses

```javascript
import React from "react";
import { CometChatConversationList } from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatConversationList background="yellow" conversationType="users" _>
  )
}
```

