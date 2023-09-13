`CometChatConversations` is an independent component that shows all conversations involving the logged in user. By default, for each conversation that will be listed, the name of the user or group the logged in user is having conversation with will be displayed in the title of every list item, the subtitle will contain the last message in that conversation along with its receipt status, the leading view will contain the avatars of the user and groups and status indicator will indicate if users are online and icons for indicating a private or password protected group, and the trailing view will contain the time of the last message in that conversation and the number of unread messages.

`CometChatConversations` sets up the following:

- Header with customizable title
- List of recent conversations

![](https://uploads.developerhub.io/prod/x9W8/g5mnnvgyxse30byxljfi12i57ccpnebnu64saifo5a7xrbir8wvyqej7ww9xoz76.jpeg)

## Components

CometChatGroups is composed of the [CometChatListBase](https://www.cometchat.com/docs/v3/android-v4-uikit/list-base) and [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item).

| Component | Description | 
| ---- | ---- | 
| **CometChatListBase** | `CometChatListBase` is a reusable container component having title, search box, customizable background and a List View | 
| **CometChatListItem** | is a component that renders data obtained from a Group object on a Tile having a title, subtitle, leading and trailing view | 


![](https://uploads.developerhub.io/prod/x9W8/24j7sfvo8hv5y85byzvb3uzkfvw30r3c6l88f9c5os19yvl91n805tfltzjagbxt.jpeg)

## How to integrate CometChatConversation ?

Since `CometChatConversations` is a Widget, it can be added directly to the layout file as shown below

```xml
<com.cometchat.chatuikit.conversations.CometChatConversations
        android:id="@+id_conversation"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



---

## Methods

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set the title in the app bar | 
| **setStyle** | ConversationsStyle | used to set styling properties | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **backIcon** | @DrawableRes int res | used to set back button located in the app bar | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching conversations | 
| **hideSeparator** | boolean | used to hide the divider separating the conversation items | 
| **disableUsersPresence** | boolean | used to control visibility of status indicator shown if user is online | 
| **setProtectedGroupIcon** | @DrawableRes int res | used to set icon shown in place of status indicator for password protected group | 
| **setPrivateGroupIcon** | @DrawableRes int res | used to set icon shown in place of status indicator for private group | 
| **setSearchPlaceholderText** | String | used to set placeholder text for the search field | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **setMenu** | View | used to set the options available in the app bar | 
| **disableReceipt** | boolean | used to disable read receipts shown in the subtitle of the conversation item and also disabling the functionality of marking messages as read and delivered | 
| **setSentIcon** | @DrawableRes int res | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is sent | 
| **setDeliveredIcon** | @DrawableRes int res | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is delivered | 
| **setReadIcon** | @DrawableRes int res | used to customize the receipt icon shown in the subtitle of the conversation item if disableReceipt is not true and if the status of the last message in the conversation is read | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the user and group shown in the leading view of the conversation item | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setDateStyle** | DateStyle | used to customise the Avatar of the user and group shown in the trailing view of the conversation item | 
| **setBadgeStyle** | BadgeStyle | used to customise the Badge widget indicating the unread messages count shown in the trailing view of the conversation item | 
| **setDatePattern** | Function1&lt;Conversation, String&gt; | used to display a custom string instead of the timestamp show at the tail of the conversation item | 
| **setListItemView** | Function2&lt;Context, Conversation, View&gt; | used to set a custom view for every conversation item | 
| **setLisItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an Conversation object | 
| **setSubtitleView** | Function2&lt;Context, Conversation, View&gt; | used to set a custom subtitle for every conversation item | 
| **setTail** | Function2&lt;Context, Conversation, View&gt; | used to generate a custom trailing view for the conversation item, by default it shows the time sent of the last message and the unread messages count | 
| **setOptions** | Function2&lt;Context, Conversation, List&lt;CometChatOption&gt;&gt; | used to set options affecting the conversation item in some way, for example- deleting the conversation, blocking the user etc. These options will be visible on swiping any conversation item to the left | 
| **setSelectionMode** | SelectionMode | used to set the number of conversations that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **onSelection** | Function(List&lt;Conversation&gt;, BuildContext) | used to set a custom callback that would utilize the selected conversations to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping or long press on a Conversation item | 
| **addOnBackPressListener** | addOnBackPressListener | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching conversations | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the conversations are being fetched | 
| **emptyStateText** | String | used to set a custom text response when fetching the conversations has returned an empty list | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the conversations has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of conversations | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of conversations | 
| **disableTyping** | boolean | if true stops indicating if a participant in a conversation is typing | 
| **setConversationsRequestBuilder** | ConversationsRequest | used to set a custom conversations request | 


### ConversationsStyle

This property is used to customize the appearance of the CometChatConversations component

#### Methods

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | Used to set the background color | 
| **setBorderWidth** | int | Used to set border | 
| **setBorderColor** | @ColorInt int | Used to set border color | 
| **setCornerRadius** | float | Used to set border radius | 
| **setBackground** | Drawable | Used to set background Drawable | 
| **setTitleAppearance** | @StyleRes int | Used to customise the appearance of the title in the app bar | 
| **setBackIconTint** | @ColorInt int | Used to set the color of the back icon in the app bar | 
| **setSearchBackground** | @ColorInt int | Used to set the background color of the search box | 
| **setSearchBorderRadius** | int | Used to set the border radius of the search box | 
| **setSearchIconTint** | @ColorInt int | Used to set the color of the search icon in the search box | 
| **setSearchBorderWidth** | int | Used to set the border width of the search box | 
| **setSearchTextAppearance** | @StyleRes int | Used to set the style of the text in the search box | 
| **setLoadingIconTint** | @ColorInt int | Used to set the color of the icon shown while the list of group members is being fetched | 
| **setEmptyTextAppearance** | @StyleRes int | Used to set the style of the response text shown when fetchig the list of group members has returned an empty list | 
| **setErrorTextAppearance** | @StyleRes int | Used to set the style of the response text shown in case some error occurs while fetching the list of group members | 
| **setOnlineStatusColor** | @ColorInt int | Used to set the color of the status indicator shown if a group member is online | 
| **setSeparatorColor** | @ColorInt int | Used to set the color of the divider separating the group member items | 
| **setLastMessageTextAppearance** | @StyleRes int textAppearance | Used to set the style of the text for the last message. | 
| **setTypingIndicatorTextAppearance** | @StyleRes int textAppearance | Used to set the style of the text for the typing indicator . | 
| **setThreadIndicatorTextAppearance** | @StyleRes int textAppearance | Used to set the style of the text for the thread indicator . | 
| **setErrorTextColor** | @ColorInt int | Used to set the color of the text for the error Text . | 
| **setLastMessageTextColor** | @ColorInt int | Used to set the color of the text for the last message . | 
| **setTypingIndicatorTextColor** | @ColorInt int | Used to set the color of the typing indicator text . | 
| **setThreadIndicatorTextColor** | @ColorInt int | Used to set the color of thread indicator text | 


```java
CometChatConversations conversations = view.findViewById(R.id.conversation);
 ConversationsStyle style = new ConversationsStyle();
   style.setTitleColor(getResources().getColor(R.color.primary));
        conversations.setStyle(style);
```



### AvatarStyle

```java
AvatarStyle style = new AvatarStyle();
style.setBorderWidth(10);
conversations.setAvatarStyle(style);
```



### StatusIndicatorStyle

```dart
StatusIndicatorStyle style= new StatusIndicatorStyle();
style.setBorderWidth(10);
conversations.setStatusIndicatorStyle(style);
```



### BadgeStyle

```java
BadgeStyle style= new BadgeStyle();
style.setBorderWidth(10);
conversations.setBadgeStyle(style);
```



### ListItemStyle

```java
ListItemStyle style= new ListItemStyle();
style.setBorderWidth(10);
conversations.setListItemStyle(style);
```



### DateStyle

```java
DateStyle dateStyle = new DateStyle();
dateStyle.setTextAppearance(R.style.TextAppearance_AppCompat);
conversations.setDateStyle(dateStyle);
```



### ConversationsRequestBuilder

ConversationsRequestBuilder acts like a filter for fetching conversations.

| Methods | Type | Descriptions | 
| ---- | ---- | ---- | 
| **setLimit** | int | sets the number conversations that can be fetched in a single request, suitable for pagination | 
| **setConversationType** | String | used for fetching conversation type user or group | 
| **withTags** | bool | used for fetching conversations containing tags | 
| **setTags** | List&lt;String&gt; | used for fetching groups containing the passed tags | 


```java
ConversationsRequest conversationsRequest=new ConversationsRequest.ConversationsRequestBuilder().setLimit(10).build();

conversations.setConversationsRequestBuilder(conversationsRequest);
```



---

### Events

To handle events supported by `CometChatConversations` you have to add corresponding listeners by using `CometChatConversationEventListener`

| Event | Description | 
| ---- | ---- | 
| ccConversationDeleted | This event will be triggered when the logged in user deletes a conversation | 


```java
CometChatConversationEvents.addListener("LISTENER_TAG", new CometChatConversationEvents() {
            @Override
            public void ccConversationDeleted(Conversation conversation) {
                super.ccConversationDeleted(conversation);
            }
        });
```

