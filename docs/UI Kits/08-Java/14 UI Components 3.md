CometChat's UIKit is a set of pre-built UI components that allows you to easily craft an in-app chat with all the essential messaging features.

The UI Components are divided into three modules modules:

1. **Chats**
2. **Users**
3. **Groups**
4. **Messages**
5. **Shared**

---

## Conversations

The conversations module consists of multiple sub-modules:

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatConversationsWithMessages` | Conversation with Messages component allows you to interact with any user or group in your conversation list. On click of any list item in the conversation list you will be taken to the Messages page, where you can interact with that user or group. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatconversationswithmessages) | 
| `CometChatConversations` | Independent component used to set up a screen that displays the recent conversations with Users or Groups and chat with them. It also allows you to search for a specific conversation. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversations) | 
| `CometChatConversationList` | This is a subclass of **MaterialCardView** which forms a list of recent conversations. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversation-list) | 
| `CometChatConversationListItem` | The `CometChatConversationListItem` is a reusable component that is present in `CometChatConversationList`. It is tightly coupled with SDK's Conversation object. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversation-list-item) | 


---

## Users

The user module consists of multiple sub-modules:

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatUsersWithMessages` | `CometChatUsersWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any user shown in user list. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatuserswithmessages) | 
| `CometChatUsers` | Independent component used to set up a screen that displays the list of groups . It also allows you to search for a specific user using name or guid of the group. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/users) | 
| `CometChatUserList` | This is a subclass of **MaterialCardView** which forms a list of users. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/userlist) | 
| `CometChatDataItem` | `CometChatDataItem` is a custom component’s view consists of **thumbnail**, **status**, **title**, and **subtitle** fields. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/users-dataitem) | 


---

## Groups

The user module consists of multiple sub-modules:

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatGroupsWithMessages` | `CometChatGroupsWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any group shown in group list. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatgroupswithmessages) | 
| `CometChatGroups` | Independent component used to set up a screen that displays the recent conversations with Users or Groups and chat with them. It also allows you to search for a specific conversation. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/groups) | 
| `CometChatGroupList` | This is a subclass of **MaterialCardView** which forms a list of recent conversations. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatgrouplist) | 
| `CometChatDataItem` | `CometChatDataItem` is a custom component’s view consists of **thumbnail**, **status**, **title**, and **subtitle** fields. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/groups-dataitem) | 
| `CometChatCreateGroup` | `CometChatCreateGroup` a independent component used to set up a screen that shows the functionality to create a specific type of group. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatcreategroup) | 
| `CometChatJoinProtectedGroup` | `CometChatJoinProtectedGroup` a independent component used to set up a screen that shows the functionality to join a password protected group. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/join-protected-group) | 


---

## Messages

`CometChatMessages` displays the chat window for the `User` or `Group` entities where it shows the list of messages.

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatMessages` | Displays chat window which is used to send and receive real-time messages for users and groups. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/messages) | 
| `CometChatMessageList` | Displays the list of recent messages | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatmessagelist) | 
| `CometChatMessageHeader` | Displays pertinent information regarding the currently active user/group. It also shows the typing indicator when a user starts typing in the Message Composer. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/message-header) | 
| `CometChatMessageComposer` | An independent and critical component that allows users to compose and send text messages or rich media messages | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/messagecomposer) | 
| `CometChatMessageBubble` | `CometChatMessageBubble`  is reusable components which forms different types of message bubbles accordingly. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/message-bubble) | 
| `CometChatActionSheet` | `CometChatActionSheet` is a component which present list of options in a list mode as well as grid mode as per the user's choice. By default, CometChatActionSheet is an integral part of CometChatMessageComposer to deliver multiple types of media as well as custom messages. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/action-sheet) | 
| `CometChatMessageReceipt` | This component is of class `AppCompatImageView` and is customizable to display `CometChatMessageReceipt`. | [Learn More](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatmessagereceipt) | 


---

## Shared

Shared components are split into three main classes as follows:

1. **Primary Components**
2. **SDK Derived Components**
3. **Secondary Components**

---

**Primary Components**

Primary components are used in both the UI Kit and the app in multiple places at a global level.

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatListBase` | Container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed any list view | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/listbase) | 
| `CometChatSoundManager` | Subclass of `NSObject` that is responsible for playing different types of audio which is required for incoming and outgoing events in UI Kit | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/soundmanager) | 
| `CometChatConfigurations` | Configurations component allows for customisation of all the child components in a public facing component | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/configurations) | 
| CometChatTheme | Theme class provides endless number of customisations to improve or transform the look and feel of the UI Kit as per your application need. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchattheme) | 


**SDK Derived Components**

SDK derived components are derived from the SDK's main objects.

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatConversationListItem` | Reusable component that is present in `CometChatConversationList`. It is tightly coupled with the SDK's `Conversation` object. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversation-list-item) | 
| `CometChatDataItem` | `CometChatDataItem` is a custom component’s view consists of **thumbnail**, **status**, **title**, and **subtitle** fields. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. | [Learn more(User)](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/users-dataitem)\n\n\n[Learn more(Group)](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/groups-dataitem) | 


---

**Secondary Components**

Secondary components are smaller components which are being used in many places across UI Kit.

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatAvatar` | Displays an image (or) users avatar with fallback to the first two letter of the username (or) groups icon with fallback to the first two letter of the group name. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/avatar) | 
| `CometChatBadgeCount` | Displays the unread count of messages for one-on-one / group conversations. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/badgecount) | 
| `CometChatStatusIndicator` | Displays the user presence as colored dots. | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/status-indicator) | 
| `CometChatMessageReceipt` | Renders the status of a message. (for eg. read receipts, pending state indicator etc.) | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatmessagereceipt) | 
