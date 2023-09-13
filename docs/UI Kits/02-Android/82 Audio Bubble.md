`CometChatAudioBubble` is the content view for a MediaMessage if the media sent is an audio.

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setAudioUrl** | String | used to set the Audio url for the bubble | 
| **setTitleText** | String | a text to display as name of the audio file | 
| **setSubtitleText** | String | a text to display below the name of the audio file | 
| **setStyle** | AudioBubbleStyle | used to customize appearance of this widget | 
| **setPlayIcon** | @DrawableRes int | customize the icon to display to play the audio | 
| **setPauseIcon** | @DrawableRes int | customize the icon to display to pause the audio | 
| **setOnClick** | OnClick | Override the click event when tapped on play icon | 


## AudioBubbleStyle

AudioBubbleStyle is the class containing methods to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitleTextAppearance** | @StyleRes\n\nint | used to set style of the name of the audio file | 
| **setSubtitleTextAppearance** | @StyleRes\n\nint | used to set style of the text below the name of the audio file | 
| **setPlayIconTint** | @ColorInt\n\nint | used to provide color to the audio play icon | 
| **setPauseIconTint** | @ColorInt\n\nint | used to provide color to the audio pause icon | 
| **setBackground** | @ColorInt\n\nint | used to set background color | 
| **setBackground** | Drawable | used to set a gradient background | 
| **setBorderWidth** | int | used to set border | 
| **setCornerRadius** | float | used to set border radius | 


## Usage

```java
CometChatAudioBubble videoBubble = new CometChatAudioBubble(getContext());
videoBubble.setAudioUrl("https:__data-us.cometchat.io_208434241880dc4d_media_1676385385_2121040948_0a18fc37cb5afbe4cf833020017274e0.mp3", "Sample Audio", "music");
```

