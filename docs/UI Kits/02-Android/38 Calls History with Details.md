## Overview

`CometChatCallHistoryWithDetails` a independent component used to set up a screen that shows the list of recent call logs and on click of it will open call details. . It inherits all the properties and methods from the `CometChatCallsHistory` class.

`CometChatCallHistoryWithDetails` sets up the following functionality internally:

- List of call logs
- Opens call details
- Header with customizable title.

It includes all the business logic and options to customize the UI according to our default design system.

---

## Components

`CometChatCallsHistory` mainly contains below components in it.

| Components | Description | 
| ---- | ---- | 
| CometChatCallHistory | `CometChatCallsHistory` a independent component used to set up a screen that shows the list of recent call logs | 


---

## Usage

`CometChatCallHistoryWithDetails` can be launched by adding the following code snippet into XML layout file.

```xml
<com.cometchat.chatuikit.calls.callhistorywithdetails.CometChatCallHistoryWithDetails
        android:id="@+id_call_history_details"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



## Methods

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching calls | 
| **setOptions** | Function2&lt;Context, BaseMessage, List&lt;CometChatOption&gt;&gt; | used to set options affecting the call item in some way, These call item to the left | 
| **emptyStateText** | String | used to set a custom text response when fetching the users has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of users | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the users has returned an empty list | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of users | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the users are being fetched | 
| **setSubtitleView** | Function2&lt;Context, BaseMessage, View&gt; | used to set a custom subtitle for every call item | 
| **setListItemView** | Function2&lt;Context, BaseMessage, View&gt; | used to set a custom view for every call item | 
| **setStyle** | CallHistoryStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the caller | 
| **setDateStyle** | DateStyle | Used to customaize the Date of call item | 
| **setListItemStyle** | ListItemStyle | used to set the list item style | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected calls to execute some task | 
| **setSelectionMode** | UIKitConstants.SelectionMode | used to set the number of users that can be selected. By default it is `SelectionMode.multiple`. SelectionMode can be single, multiple or none. | 
| **setSubmitIcon** | @DrawableRes int | used to override the default selection complete icon | 
| **setSelectionIcon** | @DrawableRes int | used to override the default selection complete icon | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setIncomingAudioCallIcon** | @DrawableRes int | Used to set the incoming audio call icon | 
| **setIncomingVideoCallIcon** | @DrawableRes int | Used to set the incoming video call icon | 
| **setInfoIcon** | @DrawableRes int | Used to set the info icon | 
| **setItemClickListener** | OnItemClickListener&lt;BaseMessage&gt; | used to set a callback that would be triggered on tapping or long press on a call item | 
| **setOnInfoIconClickListener** | OnInfoIconClick | Used to set a callback that would be trigger on tapping on a info icon. | 
| **setCallDetailsConfiguration** | CallDetailsConfiguration | Used to configure Call Details component | 


## CallHistoryStyle

allows you to set styling properties for CometChatCallHistoryWithDetails widget

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| setBackground | @ColorInt int | Used to set the background color | 
| setBorderWidth | int | Used to set border | 
| setBorderColor | @ColorInt int | Used to set border color | 
| setCornerRadius | float | Used to set border radius | 
| setBackground | Drawable | Used to set background Drawable | 
| setTitleAppearance | @StyleRes int | Used to customise the appearance of the title in the app bar | 
| setBackIconTint | @ColorInt int | Used to set the color of the back icon in the app bar | 
| setLoadingIconTint | @ColorInt int | Used to set the color of the icon shown while the list of call is being fetched | 
| setEmptyTextAppearance | @StyleRes int | Used to set the style of the response text shown when fetchig the list of call has returned an empty list | 
| setErrorTextAppearance | @StyleRes int | Used to set the style of the response text shown in case some error occurs while fetching the list of call | 
| setSeparatorColor | @ColorInt int | Used to set the color of the divider separating the call items | 
| setIncomingAudioCallIconTint | @ColorInt int | Used to set the color of the audio call icon | 
| setIncomingVideoCallIconTint | @ColorInt int | Used to set the color of the video call icon | 
| setCallStatusColor | @ColorInt int | Used to set the color of the call status | 
| setMissedCallTitleColor | @ColorInt int | Used to set the color of the missed called title | 
| setInfoIconTint | @ColorInt int | Used to set the color of the info icon | 


```java
CometChatCallHistoryWithDetails cometChatCallHistory=view.findViewById(R.id.call_history);
CallHistoryStyle style=new CallHistoryStyle()
                .setInfoIconTint(getResources().getColor(android.R.color.darker_gray));
cometChatCallHistory.setStyle(style);
```

