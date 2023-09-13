You can modify the [CometChatThreadedMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/threaded-messages) component's properties using the `ThreadedMessagesConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `ThreadedMessagesConfiguration` supports the following configurations:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setCloseIcon** | @DrawableRes\n\nint | used to set the icon to exit the widget | 
| **setMessageBubbleView** | Function2&lt;Context, BaseMessage, View&gt; | Sets the custom message bubble view for the parent message of the  ThreadedMessages Component. | 
| **setMessageActionView** | Function2&lt;Context, BaseMessage, View&gt; | used to override the default UI component that displays the number of replies | 
| **setMessageListConfiguration** | [MessageListConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list-configuration) | used to customize the `CometChatMessageList` component being used internally | 
| **setMessageComposerConfiguration** | [MessageComposerConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer-configuration) | used to customize the `CometChatMessageComposer` component being used internally | 
| **setStyle** | ThreadedMessageStyle | used to customize the appearance of the widget | 


## How to create a ThreadedMessagesConfiguration and use it ?

please refer the below code snippet to create the object of ThreadedMessagesConfiguration and configure it

```java
ThreadedMessagesConfiguration threadedMessagesConfiguration=new ThreadedMessagesConfiguration().setTitle("Thread messages");
```



## Usage

ThreadedMessagesConfiguration can be used in a widget where CometChatThreadedMessages is present as a child component. We just pass that ThreadedMessagesConfiguration object to that parent widget.

```java
__pass it to CometChatMessages
cometChatMessages.setThreadedMessagesConfiguration(threadedMessagesConfiguration);
```

