You can modify the [CometChatConversations](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations) component's properties using the `ConversationsConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `ConversationsConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set the title in the app bar | 
| **setStyle** | [ConversationsStyle](/cometchat-documentation/v3/flutter-uikit-beta/conversations#conversationsstyle) | used to set styling properties | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setBackButtonIcon** | @DrawableRes\n\nint | used to set back button located in the app bar | 
| **hideSeparator** | boolean | used to hide the divider separating the conversation items | 
| **hideSeparator** | boolean | used to hide the text separating grouped conversation items | 
| **disableUsersPresence** | boolean | used to control visibility of status indicator shown if user is online | 
| **setMenu** | View | used to set the options available in the app bar | 
| **disableReceipt** | boolean | used to disable read receipts shown in the subtitle of the conversation item and also disabling the functionality of marking messages as read and delivered | 
| **setSentIcon** | @DrawableRes\n\nint | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is sent | 
| **setDeliveredIcon** | @DrawableRes\n\nint | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is delivered | 
| **setReadIcon** | @DrawableRes\n\nint | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is read | 
| **setPrivateGroupIcon** | @DrawableRes\n\nint | used to set icon shown in place of status indicator if the conversation is taking place in a private group | 
| **setProtectedGroupIcon** | @DrawableRes\n\nint | used to set icon shown in place of status indicator if the conversation is taking place in a password protected group | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the user and group shown in the leading view of the conversation item | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setDateStyle** | DateStyle | used to customise the Avatar of the user and group shown in the trailing view of the conversation item | 
| **setBadgeStyle** | BadgeStyle | used to customise the Badge widget indicating the unread messages count shown in the trailing view of the conversation item | 
| **setDatePattern** | Function1&lt;Conversation, String&gt; | used to display a custom string instead of the timestamp show at the tail of the conversation item | 
| **setCustomView** | Function2&lt;Context, Conversation, View&gt; | used to set a custom view for every conversation item | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an Conversation object | 
| **setSubtitle** | Function2&lt;Context, Conversation, View&gt; | used to set a custom subtitle for every conversation item | 
| **setTail** | Function2&lt;Context, Conversation, View&gt; | used to generate a custom trailing view for the conversation item, by default it shows the time sent of the last message and the unread messages count | 
| **setOptions** | Function2&lt;Context, Conversation, List&lt;CometChatOption&gt;&gt; | used to set options affecting the conversation item in some way, for example- deleting the conversation, blocking the user etc. These options will be visible on swiping any conversation item to the left | 
| **setSelectionMode** | UIKitConstants.SelectionMode | used to set the number of conversations that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | CometChatConversations.OnSelection | used to set a custom callback that would utilize the selected conversations to execute some task | 
| **setItemClickListener** | OnItemClickListener&lt;Conversation&gt; | used to set a callback that would be triggered on tapping a conversation item | 
| **setLoadingStateView** | @LayoutRes\n\nint | used to set a custom UI response when the conversations are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when fetching the conversations has returned an empty list | 
| **setEmptyStateView** | @LayoutRes\n\nint | used to set a custom UI response when fetching the conversations has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of conversations | 
| **setErrorStateView** | @LayoutRes\n\nint | used to set a custom UI response when some error occurs on fetching the list of conversations | 
| **disableTyping** | boolean | if true stops indicating if a participant in a conversation is typing | 
| **setConversationsRequest** | ConversationsRequest | used to set custom conversations request | 


## How to create a ConversationConfiguration object and use it ?

please refer the below code snippet to create the object of ConversationsConfiguration and configure it

```java
ConversationsConfiguration conversationsConfiguration = new ConversationsConfiguration()
                .setConversationsRequest(new ConversationsRequest.ConversationsRequestBuilder().setLimit(2).build());
```



## Usage

ConversationsConfiguration can be used in a widget where CometChatConversations is present as a child component. We just pass that `ConversationsConfiguration` object to the CometChatConversations widget.

```java
CometChatConversationWithMessages.setConversationsConfiguration(conversationsConfiguration);
```

