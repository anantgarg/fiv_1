`CometChatFileBubble` is the content view for a MediaMessage if the media sent is a file.

## Methods

| methods | Type | Description | 
| ---- | ---- | ---- | 
| **setFileUrl** | String | the path of the image to display | 
| **setTitleText** | String | a text to display as name of the file | 
| **setSubtitleText** | String | a text to display below the name of the file | 
| **setDownloadIcon** | Icon | customize the icon to display to download the file | 
| **setStyle** | FileBubbleStyle | used to customize appearance of this widget | 


## FileBubbleStyle

FileBubbleStyle is the class containing attributes to customize appearance of this widget.

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitleTextAppearance** | TextStyle | used to set style of the name of the file | 
| **setSubtitleTextAppearance** | TextStyle | used to set style of the text below the name of the file | 
| **setDownloadIconTint** | @ColorInt\n\nint | used to provide color to the download icon | 
| **setBackground** | @ColorInt\n\nint | used to set background color | 
| **setBackground** | Drawable | used to set a drawable background | 
| **setBorderColor** | @ColorInt\n\nint | used to set border color | 
| **setBorderWidth** | int | used to set border width | 
| **setCornerRadius** | float | used to set border radius | 


## Usage

```java
CometChatFileBubble fileBubble = new CometChatFileBubble(getContext());
        fileBubble.setFileUrl("https:__images.pexels.com_photos_1496372_pexels-photo-1496372.jpeg", "Sample file", "image");
```

