## Overview

`CometChatCallButtons` is a independent component used to set up a screen that shows the call buttons for particular user or group object. It is responsible for initiating the call by default however the functionality can be overridden

---

## Usage

`CometChatCallButtons` can be used inside another widget or can be launched to a new screen.

```xml
<com.cometchat.chatuikit.calls.callbuttons.CometChatCallButtons
        android:id="@+id_call_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" _>
```



```java
CometChatCallButtons cometChatCallButtons = view.findViewById(R.id.call_button);
        if (user != null)
            cometChatCallButton.setUser(user);
        else if (group != null)
            cometChatCallButton.setGroup(group);
```



---

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setUser** | User | Used to set User object to the call button | 
| **setGroup** | Group | Used to set Group object to the call button | 
| **setVoiceCallIcon** | @DrawableRes int | Used to set voice call icon | 
| **setVideoCallIcon** | @DrawableRes int | Used to set video call icon | 
| **setVoiceButtonText** | String | Used to set voice call text | 
| **setVideoButtonText** | String | Used to set video call text | 
| **setOnVideoCallClick** | OnClick | Used to override onclick event of video call button | 
| **setOnVoiceCallClick** | OnClick | Used to override onclick event of voice call button | 
| **hideVoiceCall** | boolean | Used to hide voice call button | 
| **hideVideoCall** | boolean | Used to hide video call button | 
| **setStyle** | CallButtonStyle | Used to set Style of CometChatCallButton | 
| **setButtonStyle** | ButtonStyle | Used to set each of CometChatButton used within the component | 
| **setOnError** | OnError | The __OnError __listener to be invoked when an error occurs in the call buttons. | 


## CallButtonsStyle

allows you to set styling properties for CometChatCallButtons widget

| Method | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | Used to set the background color | 
| **setBorderWidth** | int | Used to set border | 
| **setBorderColor** | @ColorInt int | Used to set border color | 
| **setCornerRadius** | float | Used to set border radius | 
| **setBackground** | Drawable | Used to set background Drawable | 


```java
CallButtonsStyle buttonStyle = new CallButtonsStyle();
buttonStyle.setBorderWidth(10);
cometChatCallButtons.setStyle(buttonStyle);
```

