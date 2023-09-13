---
sidebar_position: 3
title: UI Components
slug: /UI Components
---

CometChat's UIKit is a set of prebuilt UI components that allows you to easily craft an in-app chat with all the essential messaging features.


![](https://uploads.developerhub.io/prod/x9W8/fipfi7mlkmxqrfi7lszpyan1jmjxchkzj5uw8hyfs1buvtlu5o4unwlk04vl2kng.png)


---

UI Components are divided into different modules:

1. **Conversations**
2. **Messages**
3. **Shared**

---

**Conversations**

Conversations module consist of multiple components such as:


| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatConversations` | Independent component used to set up a screen that displays the recent conversations with Users or Groups and chat with them. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversations) | 
| `CometChatConversationList` | CometChatConversationList component renders a scrollable list of recent chats that a CometChat logged-in user has been a part of. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversation-list) | 



---

**Messages**

CometChatMessages displays the chat window for the `User` or `Group` entities where it shows the list of messages.


| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatMessages` | Displays chat window which is used to send and receive real-time messages for users and groups. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/messages) | 
| `CometChatMessageList` | Displays the list of recent messages | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/message-list) | 
| `CometChatMessageHeader` | Displays pertinent information regarding the currently active user/group. It also shows the typing indicator when the other user starts typing in the Message Composer. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/message-header) | 
| `CometChatMessageComposer` | An independent and critical component that allows users to compose and send text messages or rich media messages | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/message-composer) | 



---

**Shared**

Shared components are segregated into three main classes as follows:

1. **Primary Components**
2. **SDK Derived Components**
3. **Secondary Components**

---

**Primary Components**

Primary Components are used across UI Kit & app both in multiple places at global level.


| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatListBase` | Container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed any list view | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/list-base) | 
| `CometChatSoundManager` | Class lets you play and pause notification sound for incoming/outgoing messages and calls. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/sound-manager) | 
| `CometChatLocalize` | Allows you to detect the language of your users based on their browser or device settings and set the language accordingly. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/localize) | 
| `CometChatConfigurations` | Configurations component allows for customisation of all the child components in a public facing component | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/configurations) | 



**SDK Derived Components**

SDK derived components are derived from the SDK's main objects.


| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatConversationListItem` | Reusable component that is present in `CometChatConversationList`. This component renders an individual (SDK's) conversation object | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversation-list-item) | 



---

**Secondary Components**

Secondary components are smaller components which are being used in many places across UI Kit.


| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatAvatar` | Displays an image (or) users avatar with fallback to the first two letter of the username (or) groups icon with fallback to the first two letter of the group name. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/avatar) | 
| `CometChatBadgeCount` | Displays the unread count of messages for one-on-one / group conversations. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/badge-count) | 
| `CometChatStatusIndicator` | Displays the user presence as colored dots. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/status-indicator) | 
| `CometChatMessageReceipt` | Renders the status of a message. (for eg. read receipts, pending state indicator etc.) | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/message-receipt) | 



