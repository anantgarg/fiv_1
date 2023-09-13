`CometChatVideoBubble` is the content view for a MediaMessage if the media sent is a video.

## Properties

| Methods | parameters | Type | Description | 
| ---- | ---- | ---- | ---- | 
| **setVideoUrl** | (String videoUrl, @DrawableRes int placeHolderImage) | String | the url of the video to play | 
| **setThumbnailUrl** | (String thumbnailUrl, @DrawableRes int placeHolderImage) | String | used to set a custom thumbnail for the video | 
| **setStyle** | (VideoBubbleStyle style) | VideoBubbleStyle | used to customize appearance of this widget | 
| **setPlayIcon** | (@DrawableRes int playIcon) | @DrawableRes int | icon to display stacked on top of the bubble | 
| **setOnClick** | (OnClick onClick) | OnClick | custom action on tapping the video bubble play icon | 


## VideoBubbleStyle

VideoBubbleStyle is the class containing attributes to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | used to set the background color | 
| **setBackground** | Drawable | used to set background drawable | 
| **setBorderWidth** | @Dimension int | used to set border | 
| **setCornerRadius** | float | used to set border radius | 
| **setBorderColor** | @ColorInt int | used to set border color | 
| **setPlayIconTint** | @ColorInt int | used to set play icon tint color | 
| **setPlayIconBackgroundColor** | @ColorInt int | used to set play icon background color | 


## Usage

```java
__create video bubble style object
VideoBubbleStyle style=new VideoBubbleStyle()
                .setPlayIconTint(getResources().getColor(R.color.primary));

__create view object for video bubble 
CometChatVideoBubble videoBubble=new CometChatVideoBubble(getContext());

__set style to the view object
videoBubble.setStyle(style);
```

