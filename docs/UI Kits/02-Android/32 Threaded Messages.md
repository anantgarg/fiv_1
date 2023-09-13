CometChatThreadedMessages is a component that displays all replies made to a particular message in a conversation. By default, the parent message will be displayed at the top, the message composer will be at the bottom and between them a message list will contain all replies.

CometChatThreadedMessages sets up the following functionality internally:

- sets a message list component and fetches relevant messages
- sets up a message composer that will be used to send messages in the thread

## Components

CometChatThreadedMessages is composed of the following components:

| Component | Description | 
| ---- | ---- | 
| [CometChatMessageList](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list) | CometChatMessageList is a component that displays a list of Messages | 
| [CometChatMessageComposer](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer) | CometChatMessageComposer is a component that helps in writing and editing of messages and also sending attachments | 


## How to integrate CometChatThreadedMessages ?

Since `CometChatThreadedMessages` is a custom view, It can be launched by adding the following code snippet into the XML layout file..

#### Usage

```xml
<com.cometchat.chatuikit.threadedmessages.CometChatThreadedMessages
        android:id="@+id_threaded_messages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setParentMessage | BaseMessage | used to to set the message for which the replies need to be fetched | 
| setTitle | String | used to set title in the app bar | 
| setCloseIcon | @DrawableRes int res | used to set the icon to exit the widget | 
| setMessageBubbleView | Function2&lt;Context, BaseMessage, View&gt; | used to override the default UI component that displays the parent message | 
| setMessageActionView | Function2&lt;Context, BaseMessage, View&gt; | used to override the default UI component that displays the number of replies | 
| setMessageListConfiguration | [MessageListConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list-configuration) | used to customize the `CometChatMessageList` component being used internally | 
| setMessageComposerConfiguration | [MessageComposerConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer-configuration) | used to customize the `CometChatMessageComposer` component being used internally | 
| setStyle | ThreadedMessageStyle | used to customize the appearance of the widget | 


```java
__initialize CometChatThreadedMessages object
CometChatThreadedMessages threadedMessages = findViewById(R.id.threaded_messages);

__provide view to show parent message
threadedMessages.setMessageBubbleView((context, baseMessage) -> messageBubble);
__pass message object against which thread need to be open
threadedMessages.setParentMessage(baseMessage);
```



## ThreadedMessageStyle

allows you to set styling properties for CometChatThreadedMessages widget

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt\n\nint | used to set the background color | 
| **setBorderWidth** | int | used to set border | 
| **borderRadius** | double | used to set border radius | 
| **setBackground** | Drawable | used to set background gradient | 
| **setTitleAppearance** | @StyleRes int | used to customise the appearance of the title in the app bar | 
| **setCloseIconTint** | @ColorInt int | used to set the color of the close icon in the app bar | 


```java
__initialize CometChatThreadedMessages object
CometChatThreadedMessages threadedMessages = findViewById(R.id.threaded_messages);

__create ThreadedMessagesStyle object
ThreadedMessagesStyle threadedMessagesStyle=new ThreadedMessagesStyle();
threadedMessagesStyle.setBackground(getResources().getColor(android.R.color.holo_red_light));

__pass style object to the component
threadedMessages.setStyle(threadedMessagesStyle);
```

