## Overview

`CometChatOutgoingCall` is a independent component used to set up a screen that shows the outgoing call of particular user object.This Component automatically changes into ongoing call screen when receiver accept the call.

## Usage

`CometChatOutgoingCall` can be used inside another widget or can be launched to a new screen.

```xml
<com.cometchat.chatuikit.calls.outgoingcall.CometChatOutgoingCall
        android:id="@+id_outgoing_call"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



```java
CometChatOutgoingCall outgoingCall = findViewById(R.id.outgoing_call);

__pass the user object and call object
outgoingCall.setUser(user);
outgoingCall.setCall(call);
```



## Methods

| Methods | Types | Description | 
| ---- | ---- | ---- | 
| **setCall** | Call | Used to set the call object against which we need to display the outgoing screen | 
| **setUser** | User | Used to set the User object against which we need to display the outgoing screen | 
| **setDeclineButtonText** | String | Used to set the Decline Button Text | 
| **setDeclineButtonIcon** | @DrawableRes int | Used to set Decline button icon | 
| **setDeclineButtonStyle** | ButtonStyle | Used to set Decline Button Style | 
| **setStyle** | OutgoingCallStyle | Used to set Style of the outgoing call component | 
| **setOnDeclineCallClick** | OnClick | Used to set the call back when click event is triggered on decline call button. | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens . | 


## OutgoingCallStyle

OutgoingCallStyle is the class containing attributes to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | used to set the background color | 
| **setBackground** | Drawable | used to set background gradient | 
| **setBorderWidth** | int | used to set border | 
| **setCornerRadius** | float | used to set border radius | 
| **setBorderColor** | @ColorInt int | used to set border color | 
| **setTitleAppearance** | @StyleRes int | used to customise the appearance of the title | 
| **setSubTitleAppearance** | @StyleRes int | used to customise the appearance of the subtitle | 


```java
OutgoingCallStyle style=new OutgoingCallStyle().setBackground(getResources().getColor(R.color.primary));
outgoingCall.setStyle(style);
```



---