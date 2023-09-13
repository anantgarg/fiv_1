
Shared components are segregated into three main classes as follows:

1. **Primary Components**
2. **SDK Derived Components**
3. **Secondary Components**

## Primary Components

Primary Components are used across UI Kit & app both in multiple places. at global level.


| Method | Description |  | 
| ---- | ---- | ---- | 
| `CometChatListBase` | `CometChatListBase` is a container component having title(navigationBar), search(search-bar), background, and a container to embed any list view | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/list-base) | 
| `CometChatTheme` | Theme provides various customizations options for colors, typography etc. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/theme) | 
| `CometChatSoundManager` | `CometChatSoundManager` is a subclass of `NSObject` that is responsible for playing different types of audio which is required for incoming & outgoing events in UI Kit. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/sound-manager) | 
| `CometChatLocalize` | `CometChatLocalize` is a class that includes methods related to locale. Developers can use these methods to change the language of UI Kit library. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/localize) | 
| `CometChatConfigurations` | `CometChatConfigurations` will allow for customization of all the child components in a public facing component. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/configurations) | 



---

## SDK Derived Components

SDK derived components are derived from the SDK's main objects.


| Method | Description |  | 
| ---- | ---- | ---- | 
| CometChatConversationListItem | The CometChatConversationListItem is a reusable component that is present in CometChatConversationList. CometChatConversationListItem is tightly coupled with SDK's Conversation object. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/conversation-list-item) | 



---

## Secondary Components

Secondary components are smaller components which are being used in many places across UI Kit.


| Method | Description |  | 
| ---- | ---- | ---- | 
| `CometChatAvatar` | The `CometChatAvatar` component displays an image OR users avatar with fallback to the first two letter of the username OR groups icon with fallback to the first two letter of the group name. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/avatar) | 
| `CometChatBadgeCount` | The CometChatBadgeCount component displays the unread count of messages for 1-1/group chats. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/badge-count) | 
| `CometChatStatusIndicator` | The CometChatStatusIndicator component show the user presence as colored dots. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/status-indicator) | 
| `CometChatMessageReceipt` | The CometChatMessageReceipt component renders the status (read receipts, pending state indicator etc.) of a message. | [Launch](https://app.developerhub.io/cometchat-documentation/v3/react-chat-ui-kit/message-receipt) | 


---

