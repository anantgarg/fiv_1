The `CometChatMessageInformation` component is a custom UI view designed to display message-related information, such as delivery and read receipts. It serves as an integral part of the CometChat UI UIKit, extending the `CometChatListBase` class, which provides the underlying infrastructure for CometChat UI components. With its rich set of methods and properties, developers can easily customize and tailor the appearance and behavior of the message information view to suit the specific requirements of their application.

## How to integrate CometChatMesssageInformation ?

Since `CometChatMesssageInformation` is a Widget, it can be added directly to the layout file as shown below.

```xml
<com.cometchat.chatuikit.messageinformation.CometChatMessageInformation
        android:id="@+id_cometchat_message_information"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



```java
CometChatMessageInformation messageInformation = findViewById(R.id.cometchat_message_information);
messageInformation.setMessage(baseMessage);
messageInformation.setTemplate(messageTemplate);
```



## Methods

| Methods | Parameters | Description | 
| ---- | ---- | ---- | 
| **setTemplate(CometChatMessageTemplate template)** | CometChatMessageTemplate | Sets a custom message template for the message information view. | 
| **setMessage(BaseMessage message)** | BaseMessage | Sets the message to be displayed in the message information view. | 
| **setErrorViewVisibility(int visibility)** | int | Sets the visibility of the error view in the message information view. | 
| **setTitle(String title)** | String | Sets the title that will be displayed at the top of the `CometChatContacts` view. This method allows you to customize the title to provide relevant information or context to the users. | 
| **setListItemView(Function3&lt;Context, BaseMessage, MessageReceipt, View&gt; listItemView)** | Function3&lt;Context, BaseMessage, MessageReceipt, View&gt; | Sets a custom list item view for individual  entries in the message information view. | 
| **public void setSubtitleView(Function3&lt;Context, BaseMessage, MessageReceipt, View&gt; subtitleView)** | Function3&lt;Context, BaseMessage, MessageReceipt, View&gt; | Sets a custom subtitle view for individual  entries in the message information view. | 
| **setReceiptDatePattern(Function1&lt;MessageReceipt, String&gt; datePattern)** | Function1&lt;MessageReceipt, String&gt; | Sets a custom date pattern for formatting receipt dates in the message information view. | 
| **setStyle(MessageInformationStyle style)** | MessageInformationStyle | Sets the overall style and appearance for the message information view. | 
| **setReadIcon(@DrawableRes int readIcon)** | @DrawableRes int | Sets the custom icon resource for read receipts in the message information view. | 
| **setDeliveredIcon(@DrawableRes int deliverIcon)** | @DrawableRes int | Sets the custom icon resource for delivered receipts in the message information view. | 
| **setListItemStyle(ListItemStyle listItemStyle)** | ListItemStyle | Sets the style for list items in the message information view. | 
| **setAvatarStyle(AvatarStyle avatarStyle)** | AvatarStyle | Sets the style for avatars in the message information view. | 
| **setError(OnError onError)** | OnError | Sets the error callback to handle any errors that may occur within the message information view. | 
| **emptyStateText(String message)** | String | Sets the text to be displayed in the empty state view of the message information view. | 
| **errorStateText(String errorText)** | String | Sets the error message to be displayed in the error state view of the message information view. | 
| **setEmptyStateView(@LayoutRes int id)** | @LayoutRes int | Sets the custom layout resource for the empty state view of the message information view. | 
| **setErrorStateView(@LayoutRes int id)** | @LayoutRes int | Sets the custom layout resource for the error state view of the message information view. | 
| **setLoadingStateView(@LayoutRes int id)** | @LayoutRes int | Sets the custom layout resource for the loading state view of the message information view. | 
| **setBubbleView(Function2&lt;Context, BaseMessage, View&gt; bubbleView)** | Function2&lt;Context, BaseMessage, View&gt; | This method allows you to set a custom bubble view  in the message information Component. | 
| **setMessageBubbleStyle(MessageBubbleStyle messageBubbleStyle)** | MessageBubbleStyle | The `setMessageBubbleStyle` method is used to set the style and appearance of the message bubble in the `CometChatMessageInformation` component. | 
| **backIcon(@DrawableRes int res)** | @DrawableRes int | The back button is typically displayed at the top-left corner of the message information view, and it allows users to navigate back to the previous screen or close the message information view. | 
| **addOnBackPressListener(OnBackPress onBackPress)** | OnBackPress | This listener is triggered when the back button is pressed within the `CometChatMessageInformation` view. It provides a way to handle the back button press event and implement custom behavior. | 


## MessageInformationStyle

This property is used to customize the appearance of the `CometChatMesssageInformation` component.

| Methods | Parameters | Description | 
| ---- | ---- | ---- | 
| **setSubtitleTextColor(int subtitleTextColor)** | @ColorInt int | Sets the text color for the subtitle | 
| **setSubtitleTextAppearance(int subtitleTextAppearance)** | @StyleRes int | Sets the text appearance for the subtitle | 
| **setTitleFont(String titleFont)** | String | Sets the font for the title | 
| **setEmptyTextFont(String emptyTextFont)** | String | Sets the font for the empty state text | 
| **setTitleAppearance(int titleAppearance)** | @StyleRes int | Sets the text appearance for the title | 
| **setEmptyTextAppearance(int emptyTextAppearance)** | @StyleRes int | Sets the text appearance for the empty state text | 
| **setErrorTextAppearance(int errorTextAppearance)** | @StyleRes int | Sets the text appearance for the error state text | 
| **setTitleColor(int titleColor)** | @ColorInt int | Sets the text color for the title | 
| **setBackIconTint(int backIconTint)** | @ColorInt int | Sets the tint color for the back icon | 
| **setOnlineStatusColor(int onlineStatusColor)** | @ColorInt int | Sets the text color for the online status | 
| **setSeparatorColor(int separatorColor)** | @ColorInt int | Sets the color for the separator | 
| **setLoadingIconTint(int loadingIconTint)** | @ColorInt int | Sets the tint color for the loading icon | 
| **setEmptyTextColor(int emptyTextColor)** | @ColorInt int | Sets the text color for the empty state text | 
| **setErrorTextColor(int errorTextColor)** | @ColorInt int | Sets the text color for the error state text | 
| **setMessageTitleAppearance(int messageTitleAppearance)** | @StyleRes int | Sets the text appearance for the message title | 
| **setMessageInformationTitleAppearance(int messageInformationTitleAppearance)** | @StyleRes int | Sets the text appearance for the message information title | 
| **setMessageTextColor(int messageTextColor)** | @ColorInt int | Sets the text color for the message text | 
| **setMessageInfoTextColor(int messageInfoTextColor)** | @ColorInt int | Sets the text color for the message info text | 
| **setBackground(int background)** | @ColorInt int | Sets the background color | 
| **setBackground(Drawable drawableBackground)** | Drawable | Sets the drawable background | 
| **setCornerRadius(float cornerRadius)** | float | Sets the corner radius | 
| **setBorderWidth(int borderWidth)** | int | Sets the width of the border | 
| **setBorderColor(int borderColor)** | int | Sets the color of the border | 


```java
MessageInformationStyle messageInformationStyle = new MessageInformationStyle()
                .setTitleAppearance(R.style.TitleTextStyle)
                .setEmptyTextAppearance(R.style.EmptyTextStyle)
                .setSubtitleTextColor(getResources().getColor(R.color.subtitle_text_color))
                .setSubtitleTextAppearance(R.style.SubtitleTextStyle)
                .setTitleColor(getResources().getColor(R.color.title_color))
                .setBackIconTint(getResources().getColor(R.color.back_icon_tint))
                .setBorderColor(getResources().getColor(R.color.border_color));
messageInformation.setStyle(messageInformationStyle);
```

