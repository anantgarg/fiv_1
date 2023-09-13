`CometChatTextBubble` is the content view shown for TextMessage.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setText** | String | the text to display | 
| **setStyle** | TextBubbleStyle | used to customize appearance of this widget | 
| **setCompoundDrawable** | @DrawableRes int | used  to set image at the start,end,top or bottom of the text. | 
| **setCompoundDrawableIconTint** | @ColorInt int | used to set the image tint color | 


## TextBubbleStyle

`TextBubbleStyle` is the class containing attributes to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTextAppearance** | @StyleRes\n\nint | used to set style of the text of the message | 
| **setBackground** | @ColorInt\n\nint | used to set background color | 
| **setBackground** | Drawable | used to set a Drawable background | 
| **setBorderWidth** | int | used to set border | 
| **setCornerRadius** | float | used to set corner radius | 


## Usage

```xml
<com.cometchat.chatuikit.shared.views.CometChatTextBubble.CometChatTextBubble
        android:id="@+id_text_bubble"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" _>
```



```java
CometChatTextBubble cometChatTextBubble=view.findViewById(R.id.text_bubble);
cometChatTextBubble.setText("Keep calm and chat on!");
```

