The `CometChatMessages` widget that is used to handle messages for users and groups.`CometChatMessages` wraps up the three main components in it such as [CometChatMessageHeader](https://www.cometchat.com/docs/v3/java-chat-ui-kit/message-header), [CometChatMessageList](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list) & [CometChatMessageComposer](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer).

![](https://res.cloudinary.com/developerhub/image/upload/v1645621784/v2_5163/ehrsn5qw7xxmtwno3die.png)

---

## Components

CometChatMessages mainly contains below components in it.

| Components | Description | 
| ---- | ---- | 
| CometChatMessageHeader | `CometChatMessageHeader` displays the `User` or `Group` information using CometChat SDK's `User` or `Group object.` It also shows the typing indicator when the user starts typing in `MessageComposer`. | 
| CometChatMessageList | `CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. | 
| CometChatMessageComposer | `CometChatMessageComposer` is an independent and critical component that allows users to compose and send various types of messages includes text, image, video and custom messages. | 


## How to integrate CometChatMessages ?

Since `CometChatMessages` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

**Usage**

```xml
<com.cometchat.chatuikit.messages.CometChatMessages
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_message"
        _>
```



> The CometChatMessages is responsible for managing runtime permissions. To ensure the **ActivityResultLauncher** is properly initialized, its object should be created in the the **onCreate** state of an activity. To ensure that the CometChatMessages is loaded within the fragment, it is important to make sure that the fragment is loaded in the `onCreate` state of the activity.

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setUser | User | Used to pass user  of which the messages need to be fetched with logged in user | 
| setGroup | Group | Used to pass group of which the messages need to be fetched with logged in user | 
| hideMessageComposer | boolean | Used to toggle visibility for **CometChatMessageComposer**, `default false` | 
| hideMessageHeader |  | Used to toggle visibility for **CometChatMessageHeader**, `default false` | 
| disableTyping | boolean | Used to toggle functionality for showing  typing indicator and also enable/disable sending message delivery/read receipts | 
| disableSoundForMessages | boolean | Used to toggle sound for messages | 
| setMessageListConfiguration | [MessageListConfiguration](https://www.cometchat.com/docs/v3/java-chat-ui-kit/message-list-configuration) | Used to set configurational properties for CometChatMessageList | 
| setMessageHeaderConfiguration | [MessageHeaderConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-header-configuration) | Used to set configurational properties for CometChatMessageHeader | 
| setMessageComposerConfiguration | [MessageComposerConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer-configuration) | Used to set configurational properties for CometChatMessageComposer | 
| setDetailsConfiguration | [DetailsConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/details-configuration) | Used to set configurational properties for details module | 
| setCustomSoundForIncomingMessages | @RawRes int sound | Used to set custom sound asset's path for incoming messages | 
| setCustomSoundForOutgoingMessages | @RawRes int sound | Used to set custom sound asset's path for outgoing messages | 
| setThreadedMessagesConfiguration | [ThreadedMessagesConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/threaded-messages-configuration) | Used to set configurational properties for CometChatThreadedMessages | 
| setMessageHeaderView | Function3&lt;Context, User, Group, View&gt; | Used to set custom view for message header. | 
| setMessageComposerView | Function3&lt;Context, User, Group, View&gt; | Used to set custom view for message composer. | 
| setMessageListView | Function3&lt;Context, User, Group, View&gt; | Used to set custom view for message list. | 
| hideDetails | boolean | Used to toggle visibility for details icon in CometChatMessageHeader | 
| setStyle | MessageStyle | Used to set styling properties for messages | 


### MessagesStyle

MessagesStyle is a class that helps to customize the styles of CometChatMessages widget

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setBackground | @ColorInt int | Used to set the background color | 
| setBackground | Drawable | Used to set drawable background | 
| setBorderColor | @ColorInt int | Used to set border color | 
| setBorderWidth | int | Used to set border width | 
| setCornerRadius | float | Used to set corner radius | 


## Configuration

These are respective parameters used to configure child component, child components are `CometChatComposer`, `CometChatMessageList` and  `CometChatMessageHeader, CometChatMessage CometChatThreadedMessages , CometChatDetails` .

```java
CometChatMessages cometChatMessages = findViewById(R.id.message_component);
if (user != null) cometChatMessages.setUser(user);
else if (group != null) cometChatMessages.setGroup(group);
cometChatMessages.setMessageListConfiguration(messageListConfiguration);
```



above  code snippet is showing how to pass message list configuration to the CometChatMessages module 

> Similarly user can create the object for **messageComposerConfiguration**,  **messageHeaderConfiguration**,  **threadedMessagesConfiguration**  and **detailsConfiguration**  pass it to `CometChatMessage` , if you wants to configure those component as well.

## Events

To handle events supported by CometChatMessages you have to add corresponding listeners by using CometChatMessageEventListener

| Event | Description | 
| ---- | ---- | 
| ccMessageSent | Triggers whenever a loggedIn user sends any message, it will have two states such as: \n\ninProgress & sent | 
| ccMessageEdited | Triggers whenever a loggedIn user edits any message from the list of messages .it will have two states such as: inProgress & sent | 
| ccMessageDeleted | Triggers whenever a loggedIn user deletes any message from the list of messages | 
| ccMessageRead | Triggers whenever a loggedIn user reads any message. | 
| ccLiveReaction | Triggers whenever a loggedIn clicks on live reaction | 


```java
CometChatMessageEvents.addListener("LISTENER_TAG", new CometChatMessageEvents() {
            @Override
            public void ccMessageSent(BaseMessage baseMessage, int status) {
                
            }

            @Override
            public void ccMessageEdited(BaseMessage baseMessage, int status) {
                
            }

            @Override
            public void ccMessageDeleted(BaseMessage baseMessage) {
                
            }

            @Override
            public void ccMessageRead(BaseMessage baseMessage) {
                
            }

            @Override
            public void ccLiveReaction(int icon) {
                
            }
        });
```

