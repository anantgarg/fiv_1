`CometChatMessageHeader`displays the `User` or `Group` information using SDK's `User` or `Group` object. It also shows the typing indicator when the user starts typing in `MessageComposer`.

## Components

`CometChatMessageHeader`is a wrapper which contains Back Button and [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item).

| Components | Description | 
| ---- | ---- | 
| `CometChatListItem` | This component’s view consists of **avatar**, **status indicator** , **title**, and **subtitle**. The fields are then mapped with the SDK’s `user`, `group` class. | 


## How to integrate CometChatMessageHeader ?

Since `CometChatMessageHeader` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.messageheader.CometChatMessageHeader
                android:id="@+id_header"
                android:layout_width="match_parent"
                android:layout_height="56dp" _>
```



## Methods

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| **setUser** | User | used to pass user object of which header specific details will be shown | 
| **setGroup** | Group | used to pass group object of which header specific details will be shown | 
| **hideBackIcon** | boolean | used to toggle back button visibility | 
| **setBackIcon** | View | used to set back button widget | 
| **disableTyping** | boolean | used to enable /disable typing indicators | 
| **setMenu** | Function3&lt;Context, User, Group, View&gt; | used to add options in app bar | 
| **setSubtitleView** | Function3&lt;Context, User, Group, View&gt; | used to set custom subtitle view | 
| **setStyle** | MessageHeaderStyle | used to set styling properties for message header | 
| **setAvatarStyle** | AvatarStyle | used to set avatar styling | 
| **setListItemStyle** | ListItemStyle | used to set List item styling | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | Used to set status indicator styling | 
| **disableUsersPresence** | boolean | used to toggle functionality to show user's presence | 
| **setProtectedGroupIcon** | @DrawableRes int icon | used to set custom protected group icon | 
| **setPrivateGroupIcon** | @DrawableRes int icon | used to set custom private group icon | 
| **setListItemView** | View | used to set custom list item view | 


> Have to pass either User or Group

### Menu

used to add options in app bar which is visible at the tail of message header. 

```java
CometChatMessageHeader messageHeader = view.findViewById(R.id.header);
        messageHeader.setMenu((context, user, group) -> {
            TextView textView = new TextView(context);
            if (user != null) textView.setText(user.getName());
            else if (group != null) textView.setText(group.getName());
            return textView;
        });
```



### SubtitleView

used to set custom subtitle view for cometChatMessageHeader , visible below title of message header . We receive user or Group as an parameter of callback

```java
messageHeader.setSubtitleView((context, user, group) -> {
            TextView textView = new TextView(context);
            if (user != null) textView.setText(user.getName());
            else if (group != null) textView.setText(group.getName());
            return textView; 
        });
```



### style

Parameter to alter styling properties of message header

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setBorderWidth | int | used to set border | 
| setBorderColor | @ColorInt int | used to set border color | 
| setCornerRadius | float | used to set corner radius | 
| setBackground | @ColorInt int | used to set background colour | 
| setBackground | Drawable | used to set Drawable in background | 
| setBackIconTint | @ColorInt int | used to set back button icon tint | 
| setTypingIndicatorTextAppearance | @StyleRes int | used to set typing indicator textStyle | 
| setTypingIndicatorTextColor | @ColorInt int | used to set typing indicator text color | 
| setSubtitleTextAppearance | @StyleRes int | used to set subtitle text style | 
| setSubtitleTextColor | @ColorInt int | used to set subtitle text color | 
| setOnlineStatusColor | @ColorInt int | used to set online status colour | 


## Usage

for instance you want to change typing indicator text color of header

```java
MessageHeaderStyle style = new MessageHeaderStyle();
style.setTypingIndicatorTextColor(Color.parseColor("#ff0000"));
messageHeader.setStyle(style);
```

