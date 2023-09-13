You can modify the [CometChatMessageList](https://www.cometchat.com/docs/v3/android-v4-uikit/message-list) component's properties using the `MessageListConfiguration` object. To use a configuration, you simply need to pass it to the `CometChatMessage`.

The `MessageListConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setMessagesRequestBuilder** | MessagesRequestBuilder | used to set set various filters to the messages to be fetched in one request | 
| **setListAlignment** | UIKitConstants.MessageListAlignment | used to set the alignment of messages in `CometChatMessageList`. It can be either "**leftAligned**" or "**standard**" | 
| **setEmptyStateText** | String | used to set text which will be visible when no messages are available | 
| **setErrorStateText** | String | used to set text which will be visible when error in messages retrieval | 
| **setLoadingStateView** | @LayoutRes\n\nint | used to set custom view which will be visible when loading list | 
| **setEmptyStateView** | @LayoutRes\n\nint | used to set custom view which will be visible when list is empty | 
| **setErrorStateView** | @LayoutRes\n\nint | used to set custom view which will be visible when list has some error | 
| **setStyle** | MessageListStyle | used to set messages list styling properties | 
| **setAvatarStyle** | AvatarStyle | used to set styling prop for avatar | 
| **disableReceipt** | boolean | used to enable/disable sound for incoming/outgoing messages , default false | 
| **setReadIcon** | @DrawableRes\n\nint | used to set custom read icon visible at read receipt | 
| **setDeliverIcon** | @DrawableRes\n\nint | used to set custom delivered icon visible at read receipt | 
| **setSentIcon** | @DrawableRes\n\nint | used to set custom sent icon visible at read receipt | 
| **setWaitIconIcon** | @DrawableRes\n\nint | used to set custom wait icon visible at read receipt | 
| **showAvatar** | boolean | used to toggle visibility for avatar | 
| **setTimeStampAlignment** | UIKitConstants.TimeStampAlignment | used to set receipt's time stamp alignment .It can be either "**top**" or "**bottom**" | 
| **setDatePattern** | Function1&lt;BaseMessage, String&gt; | used to set custom date pattern visible in receipts , returned string will be visible in receipt's date place | 
| **setNewMessageIndicatorText** | String | used to set new message indicator text | 
| **scrollToBottomOnNewMessages** | boolean | should scroll to bottom on new message? ,  by default false | 
| **setOnThreadRepliesClick** | CometChatMessageList.ThreadReplyClick | call back for click on thread indicator | 
| **setHeaderView** | View | used to sets custom widget to header of message list | 
| **setFooterView** | View | used to sets custom widget to footer | 
| **disableReceipt** | boolean | used to control visibility of read receipts , also disables logic executed inside onMessagesRead and onMessagesDelivered listeners | 
| **setTemplates** | List&lt;CometChatMessageTemplate&gt; | used to set the type, category of messages to be shown and their respective views | 
| **setMessageInformationConfiguration** | [MessageInformationConfiguration](MessageInformationConfiguration) | Used to configure [CometChatMessageInformation](CometChatMessageInformation) component | 


## Step 1: Create MessageListConfiguration Object.

```java
MessageListConfiguration messageListConfiguration=new MessageListConfiguration().setListAlignment(UIKitConstants.MessageListAlignment.LEFT_ALIGNED);
```



## Step 2: Provide it to Configurations in the particular module

for instance you want to pass messageList properties from `CometChatConversationWithMessages`

```dart
cometChatMessages.setMessageHeaderConfiguration(messageListConfiguration);
```

