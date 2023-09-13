CometChat's **UIKitBeta** is a set of pre-built UI components that allows you to easily craft an in-app chat with all the essential messaging features.

The UI Components are divided into these modules:

1. **Conversations**
2. **Users**
3. **Groups**
4. **Messages**
5. **Calls**
6. **Shared**
7. **Views**

---

### Conversations

The conversations module consists of multiple sub-modules:

| Component | Description | Navigation | 
| ---- | ---- | ---- | 
| `CometChatConversationWithMessages` | Conversation with Messages component allows you to interact with any user or group in your conversation list. On click of any list item in the conversation list you will be taken to the Messages page, where you can interact with that user or group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations-with-messages) | 
| `CometChatConversations` | Independent component used to set up a screen that displays the recent conversations with Users or Groups and chat with them. It also allows you to search for a specific conversation. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations) | 


---

### Users

The user module consists of multiple sub-modules:

| Component | Description | Navigation | 
| ---- | ---- | ---- | 
| `CometChatUsersWithMessages` | `CometChatUsersWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any user shown in user list. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/users-with-messages) | 
| `CometChatUsers` | Independent component used to set up a screen that displays the list of users . It also allows you to search for a specific user using name or uid of the user. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/users) | 


---

### Groups

The user module consists of multiple sub-modules:

| Component | Description | Navigation | 
| ---- | ---- | ---- | 
| `CometChatGroupsWithMessages` | `CometChatGroupsWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any group shown in group list. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/groups-with-messages) | 
| `CometChatGroups` | Independent component used to set up a screen that displays the recent conversations with Users or Groups and chat with them. It also allows you to search for a specific conversation. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/groups) | 
| `CometChatCreateGroup` | `CometChatCreateGroup` a independent component used to set up a screen that shows the functionality to create a specific type of group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/create-group) | 
| `CometChatJoinProtectedGroup` | `CometChatJoinProtectedGroup` a independent component used to set up a screen that shows the functionality to join a password protected group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/join-protected-group) | 
| `CometChatGroupMembers` | `CometChatGroupMembers` is a component that displays all users member of the group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/group-members) | 
| `CometChatAddMembers` | `CometChatAddMembers` is a component that displays all users available in the app to add them to a group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/add-members) | 
| `CometChatTransferOwnership` | `CometChatTransferOwnership` is a component that displays all members of a group, a member can be selected to be made owner of the group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/transfer-ownership) | 
| `CometChatBannedMembers` | `CometChatBannedMembers` is a component that displays all users banned from the group. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/banned-members) | 


---

### Messages

`CometChatMessages` displays the chat window for the `User` or `Group` entities where it shows the list of messages.

| Component | Description | Navigation | 
| ---- | ---- | ---- | 
| `CometChatMessages` | Displays chat window which is used to send and receive real-time messages for users and groups. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/messages) | 
| `CometChatMessageList` | Displays the list of recent messages | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list) | 
| `CometChatMessageHeader` | Displays pertinent information regarding the currently active user/group. It also shows the typing indicator when a user starts typing in the Message Composer. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/message-header) | 
| `CometChatMessageComposer` | An independent and critical component that allows users to compose and send text messages or rich media messages | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer) | 
| `CometChatThreadedMessages` | is a component that displays all replies made to a particular message in a conversation. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/threaded-messages) | 


---

### Calls

| Components | Description | Navigation | 
| ---- | ---- | ---- | 
| `CometChatCallButtons` | Independent component used to display audio call , video call and conference call buttons as per User or Group. | [Learn More](https://www.cometchat.com/docs/v3/android-v4-uikit/call-buttons) | 
| `CometChatOutgoingCall` | Independent component used to display audio call or video call when user initiates a call. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/outgoing-call) | 
| `CometChatOngoingCall` | Independent component used to start audio call or video call when user accepts a call or user clicks on a join button in conference call. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/ongoing-call) | 


---

### Shared

Resources that are shared across both UI Kit and the app in multiple places at a global level.

| Component | Description |  | 
| ---- | ---- | ---- | 
| `CometChatSoundManager` | It is responsible for playing different types of audio which is required for incoming and outgoing events in UI Kit | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/sound-manager) | 
| `CometChatTheme` | Theme class provides endless number of customisations to improve or transform the look and feel of the UI Kit as per your application need. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/theme) | 
| `CometChatLocalize` | Used to change the language of UI Kit lIbrary. | [Learn more](https://www.cometchat.com/docs/v3/android-v4-uikit/localize) | 


---