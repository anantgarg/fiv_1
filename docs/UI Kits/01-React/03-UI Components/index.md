---
sidebar_position: 3
title: UI Components
slug: /ui-components
---

**UI Comui-componentsts** are building blocks of the UI Kit. **UI Components** are a set of custom classes specially designed to build a rich chat app. There are different UI Components available in the
UI Kit Library.

### CometChatUI

**CometChatUI** is an option to launch a fully functional chat application using the UI Kit. In **CometChatUI**  all the **UI Components** are interlinked and work together to launch a fully functional chat on your website/application.

![CometChatUI component](https://res.cloudinary.com/developerhub/image/upload/v1623200308/v2_5163/pl4difurt9bhcrpppaxc.png)

```javascript
import { CometChatUI } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatUI chatWithGroup="supergroup" _>
       <_div>
    );
  }
  
}
```



It takes the following properties:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| chatWithUser | The ID of the user you want to chat with | Optional | 
| chatWithGroup | The ID of the group you want to chat with | Optional | 
| friendsOnly | Value could be _true_ or _false_\n\nThis property when set to true will return only the friends of the logged-in user in the users tab. | Optional | 


> _friendsOnly_ prop is deprecated from version **v 3.0.0-beta5-1**. Please use **userListMode** variable [Customize UI Kit](https://www.cometchat.com/docs/v3/react-chat-ui-kit/customize)

### CometChatUserListWithMessages

The `CometChatUserListWithMessages` is a component with a list of users. The component has all the necessary listeners and methods required to display the user's list and shows the set of the messages/chats of the selected user.

![CometChatUserListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200314/v2_5163/lxwvhlvjvxav1uhenpfh.png)

```javascript
import { CometChatUserListWithMessages } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatUserListWithMessages chatWithUser="superhero5" _>
       <_div>
    );
  }
  
}
```



It takes the following properties:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| chatWithUser | The ID of the user you want to chat with | Optional | 
| friendsOnly | Value could be _true_ or _false_\n\nThis property when set to true will return only the friends of the logged-in user. | Optional | 


> _friendsOnly_ prop is deprecated from version **v 3.0.0-beta5-1**. Please use **userListMode** variable of UIKitSettings class for displaying only friends in the user list. Please refer to this link for documentation: [Customize UI Kit](https://www.cometchat.com/docs/v3/react-chat-ui-kit/customize)

### CometChatGroupListWithMessages

The `CometChatGroupListWithMessages` is a component with a list of groups. The component has all the necessary listeners and methods required to display the group's list and shows the set of the messages/chats of the selected group.

![CometChatGroupListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200318/v2_5163/glpaxbcs4cb6clm9hvv7.png)

```javascript
import { CometChatGroupListWithMessages } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatGroupListWithMessages chatWithGroup="supergroup" _>
       <_div>
    );
  }
  
}
```



It takes the following properties:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| chatWithGroup | The ID of the group you want to chat with | Optional | 


### CometChatConversationListWithMessages

The `CometChatConversationListWithMessages` is a component with a list of recent conversations. The component has all the necessary listeners and methods required to display the recent conversation list and shows the set of the messages/chats of the selected recent conversation

![CometChatConversationListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200326/v2_5163/c3gqlp8takwxlj3d0bje.png)

```javascript
import { CometChatConversationListWithMessages } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatConversationListWithMessages  _>
       <_div>
    );
  }
  
}
```



It takes the following properties:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| chatWithUser | The ID of the user you want to chat with | Optional | 
| chatWithGroup | The ID of the group you want to chat with | Optional | 


### CometChatMessages

The `CometChatMessages` is a component that displays the list of messages for a particular user or group.

```javascript
import { CometChatMessages } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatMessages chatWithGroup="supergroup" _>
       <_div>
    );
  }
  
}
```



It takes the following properties:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| chatWithUser | The ID of the user you want to chat with | Required | 
| chatWithGroup | The ID of the group you want to chat with | Optional | 


### CometChatUserList

The `CometChatUserList` is a component that displays the list of users available to chat. You can use this component within your app if you wish to display the list of users.

![CometChatUserList component](https://res.cloudinary.com/developerhub/image/upload/v1623200332/v2_5163/ddjiknergzlyhclw5nx1.png)

```javascript
import { CometChatUserList } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatUserList friendsOnly={true} _>
       <_div>
    );
  }
  
}
```



It takes the following props:

| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| friendsOnly | Value could be _true_ or _false._\n\nThis property when set to true will return only the friends of the logged-in user. | Optional | 


> _friendsOnly_ prop is deprecated from version **v 3.0.0-beta5-1**. Please use **userListMode** variable of UIKitSettings class for displaying only friends in the user list. Please refer to this link for documentation: [Customize UI Kit](https://www.cometchat.com/docs/v3/react-chat-ui-kit/customize)

### CometChatGroupList

The `CometChatGroupList` is a component that displays the list of groups available. You can use this component within your app if you wish to display the list of groups.

![CometChatGroupList component](https://res.cloudinary.com/developerhub/image/upload/v1623200335/v2_5163/iejkwrhilheaoja1eic5.png)

```javascript
import { CometChatGroupList } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatGroupList _>
       <_div>
    );
  }
  
}
```



### CometChatConversationList

You can use the `CometChatConversationList` component to display the list of recent conversations that the logged-in user was a part of.

![CometChatConversationList component](https://res.cloudinary.com/developerhub/image/upload/v1623200339/v2_5163/hj3ch9tu2dhj9hvjhynx.png)

```javascript
import { CometChatConversationList } from "._cometchat-pro-react-ui-kit_CometChatWorkspace_src";

class App extends React.Component {
  
  render() {
    
     return (
       <div style={{width: '800px', height:'800px' }}>
        <CometChatConversationList _>
       <_div>
    );
  }
  
}
```

