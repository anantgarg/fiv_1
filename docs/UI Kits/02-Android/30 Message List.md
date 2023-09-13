`CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. It contains the following list of possible items:

- Text messages and Rich Media if text contains URL. 
- Attachments (media or file) message.
- Collaborative Whiteboard & Document.
- Stickers
- Deleted message (only for current user)
- System message (e.g. some user joined a channel)
- Date separator
- Optimistic UI

You can customize the appearance of this component using method calls at runtime.

![](https://uploads.developerhub.io/prod/x9W8/86ibsl3zs5qhhd1yxc7nqshotw37vnp4h8o415y2x7i84ua88dq6jny0xhkr6jd4.png)

## Components

`CometChatMessageList` mainly contains below components in it.

|  | Component | Description | 
| ---- | ---- | ---- | 
| 1 | CometChatMessageBubble | `CometChatMessageBubble` is the reusable components which forms different types of message bubbles accordingly. | 


---

## How to integrate CometChatMessageList ?

Since `CometChatMessageList` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

```xml
<com.cometchat.chatuikit.messagelist.CometChatMessageList
                android:id="@+id_message_list"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:layout_marginStart="16dp"
                android:layout_marginEnd="16dp"
                android:background="@android:color_transparent" _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setUser** | User | used to set the conversation type and **user** of which messages will be fetched, only one of user or group should be passed | 
| **setGroup** | Group | used to set the conversation type and **group** of which messages will be fetched, only one of user or group should be passed | 
| **setMessagesRequestBuilder** | MessagesRequestBuilder | used to set set limit to the number of messages to be fetched in one request | 
| **setAlignment** | UIKitConstants.MessageListAlignment | used to set the alignmet of messages in `CometChatMessageList`. It can be either "**leftAligned**" or "**standard**" | 
| **emptyStateText** | String | used to set text which will be visible when no messages are available | 
| **errorStateText** | String | used to set text which will be visible when error in messages retrieval | 
| **setLoadingStateView** | @LayoutRes int id | used to set custom view which will be visible when loading list | 
| **setEmptyStateView** | @LayoutRes int id | used to set custom view which will be visible when list is empty | 
| **setErrorStateView** | @LayoutRes int id | used to set custom view which will be visible when list has some error | 
| **hideError** | boolean | used to toggle visibility of error in MessageList | 
| **setStyle** | MessageListStyle | used to set messages list styling properties | 
| **setAvatarStyle** | AvatarStyle | used to set styling prop for avatar | 
| **disableSoundForMessages** | boolean | used to enable/disable sound for incoming/outgoing messages , default false | 
| **setCustomSoundForMessages** | @RawRes int sound | used to set custom sound for outgoing message | 
| **setReadIcon** | @DrawableRes int icon | used to set custom read icon visible at read receipt | 
| **setDeliverIcon** | @DrawableRes int icon | used to set custom delivered icon visible at read receipt | 
| **setSentIcon** | @DrawableRes int icon | used to set custom sent icon visible at read receipt | 
| **setWaitIconIcon** | @DrawableRes int icon | used to set custom wait icon visible at read receipt | 
| **showAvatar** | boolean | used to toggle visibility for avatar | 
| **setDatePattern** | Function1&lt;BaseMessage, String&gt; | used to set custom date pattern visible in receipts , returned string will be visible in receipt's date place | 
| **hideTimestamp** | boolean | used to hide timestamp | 
| **setTimeStampAlignment** | UIKitConstants.TimeStampAlignment | used to set receipt's time stamp alignment .It can be either "**top**" or "**bottom**" | 
| **newMessageIndicatorText** | String | used to set new message indicator text | 
| **scrollToBottomOnNewMessage** | boolean | should scroll to bottom on new message? ,  by default false | 
| **onThreadRepliesClick** | ThreadReplyClick | call back for click on thread indicator | 
| **setHeaderView** | View | used to sets custom widget to header of message list | 
| **setFooterView** | View | used to sets custom widget to footer | 
| **setDateSeparatorPattern** | Function1&lt;BaseMessage, String&gt; | used to set string in date separator | 
| **setOnError** | OnError | callback triggered in case of any error | 
| **disableReceipt** | boolean | used to control visibility of read receipts , also disables logic executed inside onMessagesRead and onMessagesDelivered listeners | 
| **setTemplates** | List&lt;CometChatMessageTemplate&gt; | used to set the type, category of messages to be shown and their respective views | 
| **setMessageInformationConfiguration** | [MessageInformationConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/message-information-configuration) | Used to configure [CometChatMessageInformation](https://www.cometchat.com/docs/v3/android-v4-uikit/messsage-information) component | 


### messagesRequestBuilder

this parameter takes message request builder which is responsible for setting filter while fetching messages . Some of them are listed below 

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **limit** | int | set limit for | 
| **timestamp** | DateTime | set timestamp previous to which messages will be fetched | 
| **messageId** | int | set messages id previous to which messages will be fetched | 
| **updatesOnly** | bool | set filter to only fetch messages which are updated | 
| **hideDeleted** | bool | set filter to not show deleted messages | 


> Following parameters in messageRequestBuilder will always be altered inside message list> > 1. UID> 2. GUID> 3. types> 4. categories

```java
CometChatMessageList cometChatMessageList = view.findViewById(R.id.message_list);

MessagesRequest.MessagesRequestBuilder requestBuilder = new MessagesRequest.MessagesRequestBuilder().hideDeletedMessages(true).setLimit(2).withTags(true);
cometChatMessageList.setMessagesRequestBuilder(requestBuilder);
```



### MessageListStyle

You will be able to modify the styling properties of message list mentioned below:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBorderWidth** | int | set border | 
| **setBorderColor** | @ColorInt\n\nint | set border color | 
| **setCornerRadius** | int | set border radius | 
| **setLoadingIconTint** | @ColorInt\n\nint | set loading icon tint | 
| **setEmptyTextAppearance** | @StyleRes\n\nint | set empty state text Appearance | 
| **setErrorTextAppearance** | @StyleRes\n\nint | set error text Appearance | 
| **setEmptyTextColor** | @ColorInt\n\nint | set empty state text color | 
| **setErrorTextColor** | @ColorInt\n\nint | set error state text color | 
| **setNameTextColor** | @ColorInt\n\nint | set sender/receiver name text color on a message bubble. | 
| **setNameTextAppearance** | @StyleRes\n\nint | set sender/receiver name text appearance on a message bubble | 
| **setTimeStampTextColor** | @ColorInt\n\nint | set time stamp color | 
| **setTimeStampTextAppearance** | @StyleRes\n\nint | set time stamp text appearance | 
| **setThreadReplySeparatorColor** | @ColorInt\n\nint | set thread reply separator color | 
| **setThreadReplyTextColor** | @ColorInt\n\nint | set thread reply text color | 
| **setThreadReplyTextAppearance** | @StyleRes\n\nint | set thread reply text appearance | 
| **setThreadReplyIconTint** | @ColorInt\n\nint | set thread reply icon tint | 
| **setBackground** | @ColorInt\n\nint | This method will set the background color for message list | 
| **setBackground** | Drawable | This will set drawable component for list background | 


```java
CometChatMessageList cometChatMessageList = view.findViewById(R.id.message_list); 
MessageListStyle messageListStyle =new MessageListStyle();
messageListStyle.setBackground(Color.parseColor("#ff606d"));
cometChatMessageList.setStyle(messageListStyle);
```



![](https://uploads.developerhub.io/prod/x9W8/zew5j7p035dqwhw3m46wwvbuya9ao9g0fe33ng7b8ksr7agu8onegqyw4962l67v.png)

### **onThreadRepliesClick**

this will be triggered when clicked on thread replies

```java
cometChatMessageList.setOnThreadRepliesClick(new CometChatMessageList.ThreadReplyClick() {
            @Override
            public void onThreadReplyClick(Context context, BaseMessage baseMessage, CometChatMessageBubble messageBubble) {
                
            }
        });
```



### Templates

 This will set the templates of message types to display them in messages. LoggedIn user can send multiple types of messages in the group/user for which the chat window is opened.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setType** | String | the type of the message | 
| **setCategory** | String | the category of the message | 
| **setHeaderView** | Function3&lt;Context, BaseMessage, UIKitConstants.MessageBubbleAlignment, View&gt; | used to set a view to show up in the header of the message bubble | 
| **setContentView** | Function3&lt;Context, BaseMessage, UIKitConstants.MessageBubbleAlignment, View&gt; | used to set a view to display the main content of the message bubble, it could be a text, image, video etc. | 
| **setFooterView** | Function3&lt;Context, BaseMessage, UIKitConstants.MessageBubbleAlignment, View&gt; | used to set a view to show up in the footer of the message bubble. By default timestamp and message receipt is shown. | 
| **setBubbleView** | Function3&lt;Context, BaseMessage, UIKitConstants.MessageBubbleAlignment, View&gt; | the headerView, contentView and footerView collectively form a  message bubble, passing a bubbleView would override that entire combined structure and present a single UI component instead | 
| **setOptions** | Function3&lt;Context, BaseMessage, Group, List&lt;CometChatMessageOption&gt;&gt; | list of available actions that any user can perform on a message. it could be copying, replying or even forwarding the message etc. | 


```java
__ creating custom template
CometChatMessageTemplate customTemplate = new CometChatMessageTemplate()
  .setCategory(CometChatConstants.CATEGORY_CUSTOM)
  .setType("custom_type")
  .setOptions((context, baseMessage, group) -> ChatConfigurator.getUtils().getCommonOptions(context, baseMessage, group))
  .setBottomView((context, baseMessage, isLeftAlign) -> ChatConfigurator.getUtils().getBottomView(context, baseMessage, isLeftAlign))
  .setContentView((context, baseMessage, alignment) -> {
            if (baseMessage.getDeletedAt() == 0) {
                TextView textView = new TextView(context);
                textView.setText("custom template");
                return textView;
            } else return ChatConfigurator.getUtils().getDeleteMessageBubble(context, alignment);
        });

__adding all the default templates
List<CometChatMessageTemplate> templates = new ArrayList<>(ChatConfigurator.getUtils().getMessageTemplates());

__adding custom template that we have just created
templates.add(customTemplate);

__passing the array of templates to message List
cometChatMessageList.setTemplates(templates);
```



### customSoundForMessages

This method will set custom sound for messages

| Method | Type | Description | 
| ---- | ---- | ---- | 
| setCustomSoundForMessages | @RawRes int | set custom asset url for sound | 


```java
cometChatMessageList.setCustomSoundForMessages(R.raw.incoming_message);
```



### **Message Alignment**

The Message List alignment can be set by following parameter:

| Method | Description | 
| ---- | ---- | 
| setAlignment alignment | Used to set the alignmet of messages in `CometChatMessageList`. It can be either "**leftAligned**" or "**standard**" | 


```java
__setting messages list to standard
cometChatMessageList.setAlignment(UIKitConstants.MessageListAlignment.STANDARD);

__setting messages list to left align 
cometChatMessageList.setAlignment(UIKitConstants.MessageListAlignment.LEFT_ALIGNED);
```



![](https://uploads.developerhub.io/prod/x9W8/8hkjpaq0imr87cv0gu95iedpf2gbgdq4mocmtil4o121ph71y4w77jiiyeb7leyu.png)