## Overview

`CometChatOngoingCall` is a independent component used to set up a screen that displays the real time ongoing call. It can be default call or direct call.

---

## Usage

`CometChatOngoingCall` can be used inside another widget or can be launched to a new screen.

```xml
<com.cometchat.chatuikit.calls.ongoingcall.CometChatOngoingCall
        android:id="@+id_ongoing_call"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



```java
CometChatOngoingCall ongoingCall = view.findViewById(R.id.ongoing_call); 
ongoingCall.setType(receiverType);
ongoingCall.setSessionId(sessionId);
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setStyle** | OngoingCallStyle | Used to set styling properties. | 
| **setOnError** | OnError | Used to set a callback triggered in case any error happens. | 
| **setSessionId** | String | Used  to set session id to start call. | 
| **setReceiverType** | String | Used to set receiver type either it will be user or group. | 
| **setCallType** | String | Used to set Call type either it will be audio or video | 


## OngoingCallStyle

allows you to set styling properties for CometChatOngoingCall widget

| Method | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | Used to set the background color | 
| **setBorderWidth** | int | Used to set border | 
| **setBorderColor** | @ColorInt int | Used to set border color | 
| **setCornerRadius** | float | Used to set border radius | 
| **setBackground** | Drawable | Used to set background Drawable | 


```java
OngoingCallStyle ongoingCallStyle=new OngoingCallStyle().setBorderWidth(10);
ongoingCall.setStyle(ongoingCallStyle);
```

