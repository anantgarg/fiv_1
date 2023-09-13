`CometChatMessageInput` is a component that provides a skeleton layout for contents of [CometChatMessageComposer](https://www.cometchat.com/docs/v3/swift-chat-ui-kit/message-composer) like `TextField`, auxiliary options, primary button view and attachment options.

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setText** | String | initial text for the input field | 
| **setPlaceHolderText** | String | sets hint text for the input field | 
| **setOnTextChangedListener** | Function(String) | callback to handle change in value of text in the input field | 
| **setStyle** | MessageInputStyle | provides style to this widget | 
| **setMaxLine** | int | maximum lines allowed to increase in the input field | 
| **setSecondaryButtonView** | Widget | additional ui component apart from primary | 
| **setAuxiliaryButtonView** | Widget | additional ui component apart from primary and secondary | 
| **setPrimaryButtonView** | Widget | a ui component that would trigger basic functionality | 
| **setAuxiliaryButtonAlignment** | AuxiliaryButtonsAlignment | controls position auxiliary button view | 


## MessageInputStyle

`MessageInputStyle` helps to customize `CometChatMessageInput`

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBorderWidth** | int | used to set border | 
| **setCornerRadius** | float | used to set border radius | 
| **setBackground** | @ColorInt\n\nint | used to set the background color | 
| **setInputBackground** | @ColorInt\n\nint | Used to set the input text Background color | 
| **setBackground** | Drawable | used to set background drawable | 
| **setInputTextAppearance** | TextStyle | used to set input text style | 
| **setPlaceHolderColor** | TextStyle | used to set text color of the hint text | 
| **setSeparatorTint** | @ColorInt\n\nint | used to set color to the divider separating input field and bottom bar | 