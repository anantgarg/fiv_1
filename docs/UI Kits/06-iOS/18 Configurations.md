All child components of a public facing component support a set of configurations that will allow the end-user to customize their properties.

E.g in the `CometChatConversations` component, all the child and grand-child components support configuration – i.e. `CometChatConversationList`, `CometChatConversationListItem`, `CometChatAvatar`, `CometChatStatusIndicator`, `CometChatBadgeCount` and `CometChatMessageReceipt.`

Each component is configured using a specific configuration object. Configuration objects are provided for the following components:

| Component | Configuration |  | 
| ---- | ---- | ---- | 
| Avatar | AvatarConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/avatarconfiguration) | 
| BadgeCount | BadgeCountConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/badgecountconfiguration) | 
| StatusIndicator | StatusIndicatorConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/statusindicatorconfiguration) | 
| ConversationList | ConversationListConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/conversationlistconfiguration) | 
| ConversationListItem | ConversationListItemConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/conversationlistitemconfiguration) | 
| UserList | UserListConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/user-list) | 
| UserListItem | UserListItemConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/user-list-item) | 
| GroupList | GroupListConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/grouplist-configuration) | 
| GroupListItem | GroupListItemConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/grouplist-configuration) | 
| MessageReceipt | MessageReceiptConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messagereceiptconfiguration) | 
| Message | CometChatMessagesConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/cometchatmessagesconfiguration) | 
| MessageComposer | MessageComposerConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messagecomposerconfiguration) | 
| MessageHeader | MessageHeaderConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messageheader-configuration) | 
| MessageList | MessageListConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messagelist-configuration) | 
| MessageBubble | MessageBubbleConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messagebubble-configuration) | 


Note: the configuration object names are not completely consistent (e.g. the `Message` configuration object is named `CometChatMessagesConfiguration`).