CometChatMessageHeader displays the `User` or `Group` information using SDK's `User` or `Group` object. It also shows the typing indicator when the user starts typing in `MessageComposer`.

![](https://res.cloudinary.com/developerhub/image/upload/v1644956650/v2_5163/oaiyr9vbotfzuyiea0rv.png)

---

## Components

CometChatMessageHeader is a wrapper which contains Back Button and CometChatDataItem.

|  | Components | Description | link | 
| ---- | ---- | ---- | ---- | 
| 1 | ImageView | ImageView is a android native widget which is used to show Back Button in CometChatMessageheader. | [Navigation](https://developer.android.com/reference/android/widget/ImageView) | 
| 2 | CometChatDataItem | This component’s view consists of **avatar**, **status indicator** , **title**, and **subtitle**. The fields are then mapped with the SDK’s `user`, `group`  class. | [Navigation(User)](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/users-dataitem)\n\n\n[Navigation(Group)](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/groups-dataitem) | 


---

## How to integrate CometChatMessageHeader ?

Since CometChatMessageHeader is a custom view, it can be added directly in the layout file or you can use it in Java. CometChatMessageHeader includes various Attributes and methods to Customize its UI.

#### Usage in XML

```xml
<com.cometchatworkspace.components.messages.header.CometChatMessagesHeader
        android:id="@+id_messageHeader"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"_>
```



## XML Attributes

| Parameter | Description | 
| ---- | ---- | 
| `app:titleColor` | Used to set the text color of Title in `CometChatMessageHeader` | 
| `app:subtitleColor` | Used to set the text color of subtitle in `CometChatMessageHeader` | 
| `app:backIconTint` | Used to set the icon color for back button in `CometChatMessageHeader` | 


```xml
<com.cometchatworkspace.components.messages.header.CometChatMessagesHeader
        android:id="@+id_messageHeader"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:titleColor="#FF606D"
        app:subtitleColor="@color_primaryTextColor"                                                               app:backIconTint="@color_black"_>
```



![](https://uploads.developerhub.io/prod/x9W8/iexahcx8tgc9rcv4vsfpmzdw96qnk63ogvbwlhn2i98hiue99ygcpj7njdridtzf.png)

---

## Methods

### **User**

This will set the SDK's User object in the CometChatMessageHeader and modify the internal component for that user. It will also show if the User is typing message for the loggedin user in real time.

| Method | Description | 
| ---- | ---- | 
| user(User user) | Used set the SDK's User object in the CometChatMessageHeader | 


```java
messageHeader.user(user);
```



### **Group**

This will set the SDK's Group object in the CometChatMessageHeader and modify the internal component for that group. It will also show if the User is typing message for that group in real time

| Method | Description | 
| ---- | ---- | 
| group(Group group) | Used set the SDK's Group object in the CometChatMessageHeader | 


```java
messageHeader.group(group);
```



### **Options**

This method expects List of CometChatOptions to set in Tail view of CometChatDataItem

| Method | Description | 
| ---- | ---- | 
| options(List&lt;CometChatOptions&gt; options) | Used to set list of option in tail view | 


```java
List<CometChatOptions> option_list=new ArrayList<>();
messageHeader.options(option_list);
```



### **Title**

The following methods are use to customise and change the appearance of the Title

| Methods | Description | 
| ---- | ---- | 
| titleColor(@ColorInt int color) | This method will set the title color for MessageHeader | 
| titleFont(String font) | This method will set the title font for MessageHeader | 


```java
messageHeader.titleColor(Color.parseColor("#FF606D"));

messageHeader.titleFont("Roboto-Regular.ttf");
```



![](https://uploads.developerhub.io/prod/x9W8/rthiwfifl0f8723891r3fj20blgis063yn2xxok0qiwh7wnhpokfly9huln1i1dq.png)

### **Subtitle**

The following methods are use to customise and change the appearance of the Subtitle.

| Methods | Description | 
| ---- | ---- | 
| subTitleColor(@ColorInt int color) | This method will set the subtitle color for MessageHeader. | 
| subTitleFont(String font) | This method will set the subtitle font for MessageHeader. | 
| hideSubTitle(boolean isHidden) | This method will hide the subtitle from MessageHeader. | 


```java
__syntax for subTitleColor
messageHeader.subTitleColor(Color.parseColor("#FF606D"));

__syntx for subTitleFont
messageHeader.subTitleFont("Roboto-Regular.ttf");

__syntax for hideSubTitle
messageHeader.hideSubTitle(false);
```



![](https://uploads.developerhub.io/prod/x9W8/cgpgjht7v234rm74di5ozg0rkiuhomdhpp9xuhckg4izpequxt7cbmab0y0hs5uw.png)

### **Back Button**

Back button is  used to pop the current active screen and go back to the previous active screen . You can modify the back button using below methods:

| Methods | Description | 
| ---- | ---- | 
| backButtonIconTint(@ColorInt int color) | Used to change the back icon color. | 
| addListener(String TAG, OnEventListener messageToolbarListener) | Used to handle event when click action is performed on back button. | 


```java
__syntax for backButtonIconTint
messageHeader.backButtonIconTint(Color.parseColor("#FF606D"));

__syntax for addListener
cometchatMessageHeader.addListener("UNIQUE_ID", new CometChatMessagesHeader.OnEventListener() {
            @Override
            public void onBackPressed() {
                getActivity().onBackPressed();
            }
        });
```



![](https://uploads.developerhub.io/prod/x9W8/twfq8ybme91vxgzncl1re1bi5pb50y1jf8osd8qrdaq5gyfuowm6ung1uvnuoozs.png)

### **Background**

You will be able to modify the background using the below methods:

| Methods | Description | 
| ---- | ---- | 
| background(Drawable drawable) | This method will set the background drawable to CometChatMessageHeader. | 
| backgroundColor(@ColorInt int color) | This method will set the background color to CometChatMessageHeader. | 


```java
__ syntax for background(Drawable drawable)
messageHeader.background(getResources().getDrawable(R.drawable.background));

__ syntax for backgroundColor(@ColorInt int color)
messageHeader.backgroundColor(Color.parseColor("#FF606D"));
```



![](https://uploads.developerhub.io/prod/x9W8/ehkimwnw77kc603c061dv0qom2qqishkhyfo343es6ib4z3kdsypjf82g1it43rb.png)

### **Style**

You can modify the  **color, corner radius, border width,border color,**  and other properties of CometChatMessageHeader using `setStyle(Style style)`. It is used to customise the inner components as per the requirements.

| Methods | Description | 
| ---- | ---- | 
| titleColor(@ColorInt int titleColor) | Used to modify the Title text Color of the MessageHeader. | 
| subTitleColor(@ColorInt int subTitleColor) | Used to modify the subTitle color of the MessageHeader. | 
| backIconTint(@ColorInt int backIconTint) | Used to modify the back icon color of the MessageHeader. | 
| cornerRadius(float cornerRadius) | Used to modify the corner radius of MessageHeader. | 
| borderWidth(int width) | Used to modify the border width of MessageHeader. | 
| borderColor(@ColorInt int color) | Used to modify the border color of MessageHeader. | 
| background(@ColorInt int background) | Used to set the background color to MessageHeader. | 
| gradientBackground(int[] colors, GradientDrawable.Orientation orientation) | Used to set the gradient background  to MessageHeader. | 


```java
Style style=new Style()
    .background(getResources().getColor(R.color.background))
    .borderWidth(10)
  	.borderColor(getResources().getColor(R.color.accent900))
    .cornerRadius(12)
    .titleColor(getResources().getColor(R.color.accent900))
    .subTitleColor(getResources().getColor(R.color.primary))
  	.background(getResources().getColor(R.color.background));

messageHeader.setStyle(style);
```



### **Configuration**

This method are used to configure there child component, Here child components are`CometChatDataItem`,  `CometChatAvatar` and `CometChatStatusIndicator` .

| Method | Description | 
| ---- | ---- | 
| setConfiguration(CometChatConfigurations configuration) | This method will require object of HeaderConfiguration as an parameter to set the configuration. | 


```java
__ create instance of InputData
InputData<Group> inputData=new InputData<User>(true,true,true,Group::getScope);
HeaderConfiguration headerConfiguration = new HeaderConfiguration().setInputData(inputData);
messageHeader.setConfiguration(headerConfiguration)
```

