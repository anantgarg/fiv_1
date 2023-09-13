## Overview

`CometChatMessageBubble` is the reusable components which forms different types of message bubbles accordingly.

![](https://uploads.developerhub.io/prod/x9W8/nqh5mxz21jgxz3v1zxagjygvehl63l591hernozql0l8fmgiya6d2b98etew1xfh.png)

It supports following types of messages:

1. **Text**
2. **Image**
3. **Video**
4. **File**
5. **Sticker**
6. **Location**
7. **Whiteboard**
8. **Document**
9. **Poll**

It Also supports multiple extensions such as:

1. **Profanity Filter**
2. **Data Masking**
3. **Link Preview**
4. **Message Translation**
5. **Thumbnail Generation**
6. **Image Moderation**
7. **Sticker**
8. **Collaborative Whiteboard**
9. **Collaborative Document**
10. **Poll**

---

## Components

`CometChatMessageBubble` mainly contains below component in it.

1. **Avatar**
2. **Date**
3. **Receipt**
4. **CustomView**
5. **Background**
6. **Message Bubbles**

These are the below list of bubbles used in the CometChatMessageBubble.

#### Text Message

![](https://uploads.developerhub.io/prod/x9W8/o6a32zmw8a87xp9m78pvcmpclv67gory5g2xko8uczpopxzk0shv2mirowyh6gsq.png)

This is the most commonly used bubble across all message types. This bubble takes `TextMessage` object as an input and render the data with the help `CometChatMessageBubble.` User can pass it's own view to it using `CometChatMessageTemplate` if he wants to modify the layout of the bubble. By default, user can modify it's properties using `CometChatTheme`  class.

---

#### Text Message - When the data is masked

![](https://uploads.developerhub.io/prod/x9W8/8x6glklm6qfmcrm2pca9n6fqzoage51wd03zmpi31fpircpkp3ywsgx6dw5lfqp5.png)

When the `Profanity Filter` or `Data Masking` extension is enabled at that time, those extensions will truncate the data such as bad words, US Based Phone numbers, emails etc as per users choice.

---

#### Text Message - When the message is Translated

![](https://uploads.developerhub.io/prod/x9W8/i2cxqh534spv0rhtgu3nb7xh0uawdsw0lsxyvfmnw1zz0gmkdqq1kmhy865z0ijq.png)

When user clicks on `Translate` button in action sheet then it triggers `Message Translation` extension interally to show the translated message. This bubble only show the translated text if the message language dosen't matches to the system language.

---

#### Text Message - When the message detects link

![](https://uploads.developerhub.io/prod/x9W8/p9umnmgculxsqzhwpinp39f7kvspejyv462laop924pp4xqgq1onuv9an9ti7op9.png)

Whenever the text message contains any links in it when the `link preview` extension is enabled at that time `CometChatLinkPreviewBubble` will get triggered and it will render the data as per the information present in the metadata of the message.

---

#### Deleted Message

![](https://uploads.developerhub.io/prod/x9W8/ppvu16t4p4ep5nwl99suro0njayvm2ghwe8g6wu36fh1lz04jehtu2jlecq82wrx.png)

Whenever the message gets deleted by the user then it will set the deletedAt and using this field `CometChatMessageBubble`renders **CometChatDeletedMessage** view on to the UI.

---

#### Image Message

![](https://uploads.developerhub.io/prod/x9W8/dqgcobo2mujdh5lwk5h9psuvyo6imjh6lt1wqrbmiytybdbvrnjlh1o94x5ywekr.png)

Whenever user sends any Image from the camera of media library at that time it will trigger `CometChatMessageBubble.` It takes MediaMessage object and message type internally as a .image and renders CometChatImageBubble using the data present in the media message object.

---

#### Image Message - When the Image is Moderated

![](https://uploads.developerhub.io/prod/x9W8/p7riug7i2kp6436fy0h7dlyao54k6l2v6u3g7vr9sf1btq0shroi40eeizst9ciy.png)

When the user sends any image which contains nudity in it and if the image moderation extension is enabled.

Whenever `Image Moderation` extension detects unsafe content it shows unsafe content view using the flag **yes** in the metadata of the extension of that particular media message.

---

#### Video Message

![](https://uploads.developerhub.io/prod/x9W8/pbiy1mqfh165qsmsz6i6p0cf945zrcn5gsvmyempnjizje197fo65osgijpph3lb.png)

Whenever user sends any Video from the camera of media library at that time it will trigger `CometChatMessageBubble.` It takes **MediaMessage** object and message type internally as a `.video` and renders **CometChatVideoBubble** using the data present in the media message object.

---

#### File Message

![](https://uploads.developerhub.io/prod/x9W8/nacjt50p1eso2n77cmfmdasi1s4k56snvwo1vtlplqezfgzx28874t4j87kux3yi.png)

Whenever user sends any File from the document library at that time it will trigger `CometChatMessageBubble.` It takes **MediaMessage** object and message type internally as a .file and renders **CometChatFileBubble** using the data present in the media message object.

---

#### Sticker Message

![](https://uploads.developerhub.io/prod/x9W8/sphh4xu69p1efwk8a44ibx31po0urxx47u7xzqrmb58y74qx3ss6if0y6cut06ud.png)

Whenever user sends any sticker from the sticker keyboard at that time it will trigger `CometChatMessageBubble.` It takes **CustomMessage** object and message type internally as a extension_sticker and renders **CometChatStickerBubble** using the data present in the custom message object. Sticker bubble takes sticker url to form the sticker message.

---

#### Collaborative Whiteboard

![](https://uploads.developerhub.io/prod/x9W8/ggmzz9qv4od7msgb7gcmcthzb9eoptk49km11vyvu30bwymjlg8xwxoyetfwft05.png)

Whenever user sends whiteboard from the action sheet at that time it will trigger `CometChatMessageBubble.` It takes **CustomMessage** object and message type internally as a extension_whiteboard and renders **CometChatWhiteboardBubble** using the data present in the custom message object. Whiteboard bubble takes whiteboard url to form the whiteboard message and it will open collaborative whiteboard using the same url.

---

#### Collaborative Document

![](https://uploads.developerhub.io/prod/x9W8/6cmr2h539r8bfe1qcneeo1t04fl84jzm1upihy5plsb3c2p3xvjagi6mlcb4imlz.png)

Whenever user sends collaborative document from the action sheet at that time it will trigger `CometChatMessageBubble.` It takes **CustomMessage** object and message type internally as a `extension_document` and renders **CometChatWhiteboardBubble** using the data present in the custom message object. Document bubble takes document url to form the document message and it will open collaborative document using the same url.

---

#### Poll Message

![](https://uploads.developerhub.io/prod/x9W8/7yv2dqkp4mhqtz9h96a67cnok2lbps1x6vov2yjffg4b23ar0abejxui7mmr9n1g.png)

Whenever user creates a poll at that time It takes `CustomMessage` object and message type internally as a extension_poll and renders `CometChatPollBubble` using the data present in the custom message object. Poll bubble takes data to form the poll message and it will display the options for the poll accordingly.

---

## How to integrate CometChatMessageBubble ?

Since `CometChatMessageBubble` is a custom view, it can be launched by adding it into the XML layout file. `CometChatMessageBubble` includes various methods to customize its UI.

#### Usage in XML

```xml
<com.cometchatworkspace.components.messages.message_list.message_bubble.CometChatMessageBubble
       android:layout_width="wrap_content"
       android:id="@+id_messageBubble"
       android:layout_height="wrap_content"_>
```



## Methods

### **Background Color**

You will be able to modify the background using the below methods:

| Methods | Description | 
| ---- | ---- | 
| backgroundColor(int[] colorArray, GradientDrawable.Orientation orientation) | This method will set the gradient color in  background | 
| backgroundColor(@ColorInt int bgColor) | This method will set the background color | 


```java
__ syntax for backgroundColor(@ColorInt int color)
messageBubble.backgroundColor(getResources().getColor(R.color.background));

__syntax for backgroundColor(int[] colorArray, GradientDrawable.Orientation orientation)
int colorArray[]={Color.parseColor("#7141e2"),Color.parseColor("#d46cb3")};
messageBubble.backgroundColor(colorArray, GradientDrawable.Orientation.BL_TR);
```



### **User Name**

The userName is a UI Label which specifies a title for **`MessageBubble`**. You can modify the title using the below methods:

| Methods | Description | 
| ---- | ---- | 
| userName(String username) | Sets the title for `MessageBubble`. | 
| userNameColor(@ColorInt int color) | Sets the title color for `MessageBubble` | 
| userNameFont(String font) | Sets the title font for `MessageBubble` | 
| userNameVisibility(int visibility) | hide/unhide title for MessageBubble | 


```java
__syntax for userName
messageBubble.userName("title");

__syntax for userNameColor
messageBubble.userNameColor(getResources().getColor(R.color.background));

__syntax for userNameFont
messageBubble.userNameFont("Roboto-Regular.ttf");

__syntax for userNameVisibility
messageBubble.userNameVisibility(View.VISIBLE);__ unhide

messageBubble.userNameVisibility(View.GONE);__ hide
```



### **Corner Radius**

Corner Appearance of the Message Bubble can be modify by using methods mentioned in table below.

| Methods | Description | 
| ---- | ---- | 
| cornerRadius(float topLeft, float topRight, float bottomLeft, float bottomRight) | Sets different corner to the each edge of the bubble. | 
| cornerRadius(float radius) | Sets same corner to the each each bubble | 
| cornerRadius(ShapeAppearanceModel shapeAppearanceModel) | Sets Shape Appearance Object to the bubble | 


```java
__syntax for cornerRadius(float topLeft, float topRight, float bottomLeft, float bottomRight)
messageBubble.cornerRadius(12,12,12,12);

__syntax for cornerRadius(float radius)
messageBubble.cornerRadius(12);

__syntax for cornerRadius(ShapeAppearanceModel shapeAppearanceModel)
 ShapeAppearanceModel shapeAppearanceModel =new ShapeAppearanceModel()
                .toBuilder()
                .setAllCorners(CornerFamily.ROUNDED,12)
   							.build();
messageBubble.cornerRadius(shapeAppearanceMode);
```



### **Avatar**

It specifies an avatar for **`MessageBubble`**. You can change  the Avatar using the below methods.

| Methods | Description | 
| ---- | ---- | 
| avatar(Drawable avatarDrawable) | Used to set Drawable image in CometChatAvatar Component. | 
| avatar(String url, String initials) | Used to set the image & text incase url is null. | 
| avatarVisibility(int visibility) | Used to hide/unhide avatar from the message Bubble. | 


```java
__syntax for avatar(Drawable avatarDrawable)
messageBubble.avatar(getResources().getDrawable(R.drawable.image));

__syntax for avatar(String url, String initials)
messageBubble.avatar("url","name");

__syntax for avatar(int visibility)
messageBubble.avatarVisibility(VISIBLE);
```



### **Border**

User can modify the border properties using below methods:

| Methods | Description | 
| ---- | ---- | 
| borderWidth(int width) | Sets the border width for `MessageBubble`. | 
| borderColor(@ColorInt int color) | Sets the border color for `MessageBubble` | 


```java
__syntax for borderWidth(int width)
messageBubble.borderWidth(10);

__syntax for borderColor(@ColorInt int color)
messageBubble.borderColor(getResources().getColor(R.color.border_color));
```



### **Message Alignment**

The Message List alignment can be set by using method in the table below:

| Methods | Description | 
| ---- | ---- | 
| messageAlignment(@Alignment.MessageAlignment String mAlignment) | Used to set message bubbles in a list left or standard align | 


```java
____syntax for messageAlignment(@Alignment.MessageAlignment String mAlignment)
messageBubble.messageAlignment(Alignment.LEFT);
```



### Message Object

This method will set the message object using the SDK's `BaseMessage`object. `MessageBubble`will render it's view as shown above as per the message type present in the `BaseMessage` object.

| Methods | Description | 
| ---- | ---- | 
| messageObject(BaseMessage baseMessage) | Sets the SDK's BaseMessage object and renders the  bubble according to the type present in the object of BaseMessage. | 


```java
__syntax for messageObject(BaseMessage baseMessage)
messageBubble.messageObject(BaseMessage baseMessage)
```



### **Time**

These Methods are used to modify time by using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| messageTimeAlignment(TimeAlignment timeAlignment) | Used to set message Time in a bubble TOP or BOTTOM align. | 
| timeStampVisibility(int visible) | Used to hide/unhide the time in message bubble. | 


```java
__syntax for messageTimeAlignment(TimeAlignment timeAlignment)
messageBubble.messageTimeAlignment(TimeAlignment.BOTTOM);

__syntax for timeStampVisibility(int visible)
messageBubble.timeStampVisibility(View.VISIBLE);
```



### **Receipt**

This Method is use to control the visibility of message Receipt.

| Method | Description | 
| ---- | ---- | 
| receiptVisibility(int visible) | It will hide/unhide the visibility of message receipt. | 


```java
__syntax for 
messageBubble.receiptVisibility(View.VISIBLE);
```



### **Message bubble Listener**

setMessageBubbleListener method will return the onClick , OnLongClick and  onReactionClick callback.

| Callback | Description | 
| ---- | ---- | 
| onClick | Return onClick callback when click action is performed in MessageBubble. | 
| OnLongClick | Return OnLongClick callback when long click action is performed in MessageBubble. | 
| onReactionClick | Return onReactionClick callback when click action is performed in reactions of the MessageBubble. | 


```java
messageBubble.setMessageBubbleListener(new MessageBubbleListener() {
            @Override
            public void onLongCLick(BaseMessage baseMessage) {
               
            }

            @Override
            public void onClick(BaseMessage baseMessage) {

            }

            @Override
            public void onReactionClick(Reaction reaction, int baseMessageID) {
              
            }
        });
```



### **Message Input Data**

MessageInputData class is used to control the visibility of inner components such as avatar, username, time and receipt.

| Method | Description | 
| ---- | ---- | 
| messageInputData(MessageInputData messageInputData) | Used to control the visibility of inner components such as avatar, username, time and receipt. | 


| Parameters | Description | 
| ---- | ---- | 
| thumbnail | Used to hide/unhide visibilty of avatar. | 
| title | Used to hide/unhide visibilty of Title. | 
| readReceipts | Used to hide/unhide visibilty of read receipt. | 
| timeStamp | Used to hide/unhide visibilty of time stamp. | 


```java
__syntax to create MessageInputData
MessageInputData messageInputData= new MessageInputData(true,true,true,true,true);

__syntax to use messageInputData(MessageInputData messageInputData)
messageBubble.messageInputData(messageInputData);
```



### **Configuration**

This methods are used to configure there child components - `CometChatAvatar` and `CometChatMessageReceipt` 

| Method | Description | 
| ---- | ---- | 
| setConfiguration(CometChatConfigurations configuration) | this method will require the object of `AvatarConfiguration /`MessageReceiptConfiguration as an parameter | 


```java
__ creating object of AvatarConfiguration
AvatarConfiguration avatarConfiguration=new AvatarConfiguration(getContext());
__ setting value to the object 
avatarConfiguration.setBorderWidth(30).setCornerRadius(30);

__ creating object of StatusIndicatorConfiguration
StatusIndicatorConfiguration statusIndicatorConfiguration= new StatusIndicatorConfiguration(getContext());
__ setting value to the object 
statusIndicatorConfiguration.setColor(getResources().getColor(R.color.colorPrimary), CometChatStatusIndicator.STATUS.ONLINE);

__ syntax for setting avatar configuration to DataItem
messageBubble.setConfiguration(avatarConfiguration);
```

