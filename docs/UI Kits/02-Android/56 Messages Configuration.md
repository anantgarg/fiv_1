You can modify the [MessagesConfiguration](https://www.cometchat.com/docs/v3/java-chat-ui-kit/messages) component's properties using the `CometChatMessagesConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `CometChatMessagesConfiguration` supports the following properties:

## Parameters

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setHideMessageComposer** | bool | Used to toggle visibility for `CometChatMessageComposer` | 
| **setDisableTyping** | bool | Used to toggle functionality for showing  typing indicator | 
| **setDisableSoundForMessages** | bool | Used to toggle sound for messages | 
| **setMessageListView** | Function3&lt;Context, User, Group, View&gt; | used to set a custom message list | 
| **setMessageHeaderView** | Function3&lt;Context, User, Group, View&gt; | used to set a custom message header | 
| **setMessageComposerView** | Function3&lt;Context, User, Group, View&gt; | used to set a custom message composer | 
| **setMessageListConfiguration** | [MessageListConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list-configuration) | used to set configurational property for CometChatMessageList | 
| **setMessageHeaderConfiguration** | [MessageHeaderConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-header-configuration) | used to set configurational property for CometChatMessageHeader | 
| **setMessageComposerConfiguration** | [MessageComposerConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer-configuration) | used to set configurational property for CometChatMessageComposer | 
| **setDetailsConfiguration** | [DetailsConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/details-configuration) | used to set configurational properties for details module | 
| **setCustomSoundForIncomingMessages** | String | used to set custom sound path for incoming messages | 
| **setCustomSoundForOutgoingMessages** | String | used to set  custom sound path for outgoing messages | 
| **setThreadedMessagesConfiguration** | [ThreadedMessagesConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/threaded-messages-configuration) | used to set threaded messages configuration | 
| **hideDetails** | bool? | used to toggle visibility for details icon in \n\n\n\nCometChatMessageHeader | 
| **setStyle** | MessagesStyle | used to set styling properties for messages | 


## How to use CometChatMessages?

## Step 1: Create MessageConfiguration Object.

```java
MessagesConfiguration configuration =new MessagesConfiguration().hideDetails(true);
```



## Step 2: Provide it to messageConfiguration in the parent module

```java
cometChatConversationWithMessages.setMessagesConfiguration(configuration);
```

