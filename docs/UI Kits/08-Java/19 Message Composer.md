`CometChatComposer` is an independent and critical component that allows users to compose and send various types of messages includes text, image, video and custom messages.

It supports the following features:

- ❤️ **Live Reaction -** Allow users to share reaction on their chat.
- ⭐ **Attachments** - Shows BottomSheet to display list of attachments.
- ⌨️ **Typing events** - Handles typing indicator internally.
- ✍️ **Editing messages** - Includes view used to "Edit" to a specific message.

![](https://uploads.developerhub.io/prod/x9W8/s3u0nq8mhlkezd07a86jbn4nezi1mfu6lpyj9jyudosgyhdvpfoje189gpnazegq.png)

---

## Components

`CometChatMessageComposer` mainly contains below component:

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | CometChatActionSheet | `CometChatActionSheet` is a component which present list of options in a list mode as well as grid mode as per the user's choice | [Naviagte](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/action-sheet) | 


## How to integrate CometChatComposer ?

Since `CometChatComposer` is a custom view, it can be launched by adding it into the XML layout file. `CometChatComposer` includes various Attributes and methods to customize its UI.

#### Usage in XML

```xml
<com.cometchatworkspace.components.messages.composer.CometChatComposer
            android:id="@+id_message_box"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"_>
```



## XML Attributes

There are various XML Attributes that can be used to customize the appearance of the CometChatMessageComposer. The most useful ones include:

| Attributes | Description | 
| ---- | ---- | 
| `app:composerBackground` | It is used to set background color of `CometChatComposer`. | 
| `app:corner_radius` | It is used to set corner radius of `CometChatComposer`. | 
| `app:attachmentIcon` | It is used to set the icon of attachment button in `CometChatComposer`. | 
| `app:sendIcon` | It is used to change the icon of send button in `CometChatComposer`. | 
| app:sendIconTint | It is used to set the color of send button in `CometChatComposer`. | 
| app:attachmentIconTint | It is used to set the color of attachment button in `CometChatComposer`. | 
| `app:placeholder` | It is used to set the string as placeholder in `CometChatComposer`. | 
| `app:placeholderColor` | It is used to change the placeholder text color in `CometChatComposer`. | 
| `app:hideAttachment` | It is used to hide/show Attachment button shown in `CometChatComposer`. | 


```xml
<com.cometchatworkspace.components.messages.composer.CometChatComposer
            android:id="@+id_composer"
            android:layout_width="match_parent"
            app:sendIcon="@drawable_send_ic"
            android:layout_height="wrap_content"_>
```



![](https://uploads.developerhub.io/prod/x9W8/8hnun5dacgw1xw6v4cg42gjrvi2sei85t5nixvr0xu5j16it4976l5ou4tcxtdoy.png)

---

### Methods

### **User**

`CometChatComposer` takes SDK's `User` object and manipulates the other components in `CometChatComposer`**.** It is use to send messages to the user.

| Methods | Description | 
| ---- | ---- | 
| `setUser(User user)` | This method set the User object in message composer to send the message | 


```java
composer.setUser(user);
```



### **Group**

`CometChatComposer` takes SDK's Group object and manipulates the other components in `CometChatComposer`**.** It is use to send messages to the group.

| Methods | Description | 
| ---- | ---- | 
| setGroup(Group group) | This method set the Group object in message composer to send the message | 


```java
composer.setGroup(user);
```



### **Background**

You will be able to modify the background using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| background(@ColorInt int color) | This method will set the background color for `CometChatComposer` | 
| background(Drawable drawable) | This method will set the background drawable for `CometChatComposer` | 


```java
__syntax for background(@ColorInt int color)
composer.background(Color.parseColor("#FF606D"));

__syntax for background(Drawable drawable)
composer.background(getResources().getDrawable(R.drawable.background));
```



![](https://uploads.developerhub.io/prod/x9W8/t5bdi5391wisjicw6qpzw8ataij8fc0qbba80sulck7aqxosdvgcct3tl8s1vtu8.png)

### **Attachments**

You will be able to modify the Attachments using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| attachmentIcon(Drawable icon) | This method will set the icon of Attachment button. | 
| attachmentIcon(int icon) | This method will set the icon of Attachment button. | 
| attachmentIconTint(@ColorInt int color) | This method will change the Attachment icon color. | 
| hideAttachment(boolean b) | This method will hide/unhide the Attachment icon from the composer | 


```java
__ syntax for attachmentIcon(Drawable icon)
composer.attachmentIcon(getResources().getDrawable(R.drawable.background));

__ syntax for attachmentIcon(int icon)
composer.attachmentIcon(R.drawable.heart_reaction);

__syntax for attachmentIconTint(@ColorInt int color)
composer.attachmentIconTint(getResources().getColor(R.color.background));

__syntax for hideAttachment(boolean b)
composer.hideAttachment(true);
```



### **Send**

You will be able to modify the Send button using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| sendIcon(Drawable sendIcon) | This method will set the icon of send button. | 
| sendIcon(int sendIcon) | This method will set the icon of send button. | 
| sendIconTint(@ColorInt int color) | This method will change the send icon color. | 
| hideSend(boolean b) | This method will hide/unhide the send button from the composer | 


```java
__ syntax for sendIcon(Drawable icon)
composer.sendIcon(getResources().getDrawable(R.drawable.background));

__ syntax for sendIcon(int icon)
composer.sendIcon(R.drawable.heart_reaction);

__syntax for sendIconTint(@ColorInt int color)
composer.sendIconTint(getResources().getColor(R.color.background));

__syntax for hideSend(boolean b)
composer.hideSend(false);
```



### **Placeholder**

You will be able to modify the hint on composer using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| placeHolder(String placeHolder) | This method will set the Composers's hint. | 
| placeHolderColor(@ColorInt int color) | This method will set the Composer's hint color. | 
| placeHolderFont(String font) | This method will set the Composer's hint Appearance | 


```java
__ syntax for placeHolderColor(@ColorInt int color)
composer.placeHolderColor(Color.parseColor("#FF606D"));

__ syntax for placeHolder(String placeHolder)
composer.placeHolder("Enter your message here");

__syntax for placeHolderFont(String font)
composer.placeHolderFont("Roboto-Regular.ttf");
```



![](https://uploads.developerhub.io/prod/x9W8/d1g1ivfbxmiqazcie3eab8u3n9ahdeemgrzpqpz1nsmwwpusz1vu9g2gwcuzreay.png)

### **Text**

You will be able to modify the Composer's Text using method in the table below:

| Method | Description | 
| ---- | ---- | 
| textColor(@ColorInt int color) | This method will set the Composer's Text color. | 


```java
__ syntax for textColor(@ColorInt int color)
composer.textColor(Color.parseColor("#FF606D"));
```



![](https://uploads.developerhub.io/prod/x9W8/ua12222herhek6s3icxdi70w9yj2itjt1dgl8nqszb9btg0h95dc39ublut1zcmg.png)

### **Live Reaction**

You will be able to modify the Composer's Live Reaction using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| liveReactionIcon(int icon) | This method will set the Composers's Live Reaction icon. | 
| hideLiveReaction(boolean value) | This method will hide/unhide the Live Reaction icon from the composer. | 


### **Style**

You can modify the **background** and **corner radius**  of `CometChatComposer` using `setStyle(Style style)`. It is used to customize the inner components as per the user's requirements.

| Methods | Description | 
| ---- | ---- | 
| cornerRadius(float cornerRadius) | Sets the Composer's corner radius. | 
| gradientBackground(int[] colors, GradientDrawable.Orientation orientation) | Sets the gradient on Composer's background | 


```java
int colorArray[]={Color.parseColor("#7141e2"),Color.parseColor("#d46cb3")};

Style style=new Style()
     .gradientBackground(colorArray, GradientDrawable.Orientation.BL_TR)
     .cornerRadius(12);

composer.setStyle(style);
```



### **Configuration**

This method is used to configure Composer

| Method | Description | 
| ---- | ---- | 
| setConfiguration(CometChatConfigurations configuration) | This method will set the composer's configuration and modify the inner properties | 


```java
ComposerConfiguration composerConfiguration=new ComposerConfiguration()
                .attachmentIcon(R.drawable.add_circle)
                .liveReactionIcon(R.drawable.heart_reaction)
                .hideAttachment(false);
```

