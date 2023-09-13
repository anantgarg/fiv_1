You can modify the [CometChatMessageComposer](https://www.cometchat.com/docs/v3/android-v4-uikit/message-composer) component's properties using the `MessageComposerConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageComposerConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setStyle** | MessageComposerStyle | used to set styling properties | 
| **setPlaceHolderText** | String | used to set composer's placeholder text | 
| **setAuxiliaryButtonView** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, View&gt; | used to set set auxiliary button/s view | 
| **setSecondaryButtonView** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, View&gt; | used to set secondary button View | 
| **setSendButtonView** | View | used to set send button view | 
| **setText** | String | used to set predefined text | 
| **setMaxLine** | int | maximum lines allowed to increase in the input field | 
| **setAuxiliaryButtonAlignment** | AuxiliaryButtonsAlignment | controls position auxiliary button view , can be **left** or   **right .** default right | 
| **setAttachmentIcon** | @DrawableRes\n\nint | sets the icon to show in the attachment button | 
| **setSendButtonClick** | CometChatMessageComposer.SendButtonClick | callback to be triggered when clicked on send button | 
| **hideLiveReaction** | boolean | used to toggle visibility for live reaction component | 
| **setHeaderView** | View | used to set header view of composer | 
| **setFooterView** | View | used to set footer view for composer | 
| **setAttachmentOption** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, List&lt;CometChatMessageComposerAction&gt;&gt; | used to set  attachment options | 
| **setLiveReactionIcon** | @DrawableRes\n\nint | used to set custom live reaction icon | 
| **setVoiceRecordingIcon** | @DrawableRes int | Sets custom drawable resources for the record buttons. | 
| **setPauseIcon** | @DrawableRes int | Sets custom drawable resources for the pause buttons. | 
| **setPlayIcon** | @DrawableRes int | Sets custom drawable resources for the play buttons. | 
| **setDeleteIcon** | @DrawableRes int | Sets custom drawable resources for the delete buttons. | 
| **setStopIcon** | @DrawableRes int | Sets custom drawable resources for the stop buttons. | 
| **setMediaRecorderStyle** | MediaRecorderStyle | This is used to customize the appearance of the CometChatMediaRecorder component. | 
| **setVoiceRecordingVisibility** | int | The visibility constant for the voice recording view. Use View.VISIBLE,   View.INVISIBLE or View.GONE. | 
| **setOnError** | OnError | callback triggered in case of any error | 


this parameter sets the styling properties for message composer

## Step 1: Create MessageComposerConfiguration Object.

```java
MessageComposerConfiguration composerConfiguration = new MessageComposerConfiguration().hideLiveReaction(true);
```



## Step 2: Provide it to Configurations in the particular module

for instance you are using CometChatMessages and need to provide configuration for composer

```java
cometChatMessages.setMessageComposerConfiguration(composerConfiguration);
```

