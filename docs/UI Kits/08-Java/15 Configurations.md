`Configuration` objects are a group of related classes that allow you to customize the UI kit and its internal components from the top level.

Each internal component has a related configuration class that allows you to modify that component at a core level.

For example, if you need to change the `cornerRadius` and `borderWidth` of a `CometChatAvatar` component being displayed inside a `CometChatConversationListItem`, you can create an `AvatarConfiguration` object and pass it to the top-level `CometChatConversations` object.

> Each Component will have setConfiguration(CometChatConfiguration config) method to handle the customization internally.

| **Configurations Files** | **Description** |  | 
| ---- | ---- | ---- | 
| Avatar | AvatarConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatavatar) | 
| BadgeCount | BadgeCountConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/badgecountconfiguration) | 
| StatusIndicator | StatusIndicatorConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/statusindicatorconfiguration) | 
| ConversationList | ConversationListConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversationsconfigurations) | 
| ConversationListItemConfiguration | ConversationListItemConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/conversationlistitem-configuration) | 
| CometChatMessagesConfiguration | CometChatMessagesConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatmessagesconfiguration) | 
| MessageComposerConfiguration | MessageComposerConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/messagecomposer-configuration) | 
| MessageHeaderConfiguration | MessageHeaderConfiguration | [Learn more](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/messageheaderconfiguration) | 
