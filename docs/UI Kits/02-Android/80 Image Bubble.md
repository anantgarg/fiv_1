`CometChatImageBubble` is the content view for a MediaMessage if the media sent is an image.

## Methods

| Methods | Parameters | Description | 
| ---- | ---- | ---- | 
| **setImageUrl** | (String url, @DrawableRes int placeHolderImage, boolean isGif) | It used to set image url which to be rendered in image bubble | 
| **setCaption** | (String caption) | a text to display below the image | 
| **setStyle** | (ImageBubbleStyle style) | used to customize appearance of this widget | 
| **setOnClick** | (OnClick onClick) | custom action on tapping the image | 


## ImageBubbleStyle

 ImageBubbleStyle is the class containing attributes to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTextAppearance** | @StyleRes\n\nint | used to set style of the caption text | 
| **setBackground** | @ColorInt\n\nint | used to set background color | 
| **setBackground** | Drawable | used to set a gradient background | 
| **setBorderWidth** | int | used to set border | 
| **setCornerRadius** | float | used to set border radius | 


## Usage

```xml
<com.cometchat.chatuikit.shared.views.CometChatImageBubble.CometChatImageBubble
        android:id="@+id_image_bubble"
        android:layout_width="228dp"
        android:layout_height="168dp" _>
```



```java
CometChatImageBubble cometChatImageBubble=view.findViewById(R.id.image_bubble);

cometChatImageBubble.setImageUrl("https:__images.pexels.com_photos_1496372_pexels-photo-1496372.jpeg",R.drawable.black_placeholder,false);
```
