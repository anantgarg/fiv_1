`CometChatMessageComposer` is an independent and critical component that allows users to compose and send various types of messages includes text, image, video and custom messages.

It supports the following features:

- ❤️ **Live Reaction -** Allow users to share reaction on their chat.
- ⭐ **Attachments** - Shows BottomSheet to display list of attachments.
- ⌨️ **Typing events** - Handles typing indicator internally.
- ✍️ **Editing messages** - Includes view used to "Edit" to a specific message.

![](https://uploads.developerhub.io/prod/x9W8/ia31645odb8scpt02a6w4jx9vdkkqnc56vcp8g0ynubmmtus8t66ih2emsmcozx8.png)

## Components

`CometChatMessageComposer` is composed of the following widgets:

| Components | Description | 
| ---- | ---- | 
| [CometChatMessageInput](https://www.cometchat.com/docs/v3/android-v4-uikit/message-input) | provides a skeleton layout for contents of this component like TextField and buttons | 
| [CometChatActionSheet](https://www.cometchat.com/docs/v3/android-v4-uikit/action-sheet) | `CometChatActionSheet` is a component which present list of options in a list mode as well as grid mode as per the user's choice | 


## How to integrate CometChatMessageComposer ?

Since `CometChatMessages` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

**Usage**

```xml
<com.cometchat.chatuikit.messagecomposer.CometChatMessageComposer
                android:id="@+id_composer"
                android:layout_width="match_parent"
                android:layout_height="wrap_content" _>
```



> The CometChatMessageComposer is responsible for managing runtime permissions. To ensure the **ActivityResultLauncher** is properly initialized, its object should be created in the the **onCreate** state of an activity. To ensure that the composer is loaded within the fragment, it is important to make sure that the fragment is loaded in the `onCreate` state of the activity.

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setUser** | User | used to set  user | 
| **setGroup** | Group | used to set group | 
| **setStyle** | MessageComposerStyle | used to set styling properties | 
| **setPlaceHolderText** | String | used to set composer's placeholder text | 
| **disableTypingEvents** | boolean | used to disable/enable  typing events , default false | 
| **disableSoundForMessages** | boolean | used to toggle sound for outgoing messages | 
| **setAuxiliaryButtonView** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, View&gt; | used to set set auxiliary button/s view | 
| **setSecondaryButtonView** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, View&gt; | used to set secondary button View | 
| **setSendButtonView** | View | used to set send button view | 
| **setSendButtonIcon** | @DrawableRes int | used to set send button icon | 
| **setText** | String | used to set predefined text | 
| **setMaxLine** | int | maximum lines allowed to increase in the input field | 
| **setVoiceRecordingIcon** | @DrawableRes int | Sets custom drawable resources for the record buttons. | 
| **setVoiceRecordingVisibility** | int | The visibility constant for the voice recording view. Use View.VISIBLE,   View.INVISIBLE or View.GONE. | 
| **setPauseIcon** | @DrawableRes int | Sets custom drawable resources for the pause buttons. | 
| **setPlayIcon** | @DrawableRes int | Sets custom drawable resources for the play buttons. | 
| **setDeleteIcon** | @DrawableRes int | Sets custom drawable resources for the delete buttons. | 
| **setStopIcon** | @DrawableRes int | Sets custom drawable resources for the stop buttons. | 
| **setMediaRecorderStyle** | MediaRecorderStyle | This is used to customize the appearance of the CometChatMediaRecorder component. | 
| **setAuxiliaryButtonAlignment** | AuxiliaryButtonsAlignment | controls position auxiliary button view , can be **left** or   **right .** default right | 
| **setAttachmentIcon** | @DrawableRes int | sets the icon to show in the attachment button | 
| **setOnSendButtonClick** | SendButtonClick | callback to be triggered when clicked on send button | 
| **hideLiveReaction** | boolean | used to toggle visibility for live reaction component | 
| **setCustomSoundForMessages** | String | Used to give custom sounds to outgoing messages | 
| **setHeaderView** | View | used to set header view of composer | 
| **setFooterView** | View | used to set footer view for composer | 
| **setAttachmentOptions** | Function4&lt;Context, User, Group, HashMap&lt;String, String&gt;, List&lt;CometChatMessageComposerAction&gt;&gt; | used to set  attachment options | 
| **setLiveReactionIcon** | @DrawableRes int | used to set custom live reaction icon | 
| **setOnError** | OnError | callback triggered in case of any error | 


## MessageComposerStyle

this Methods sets the styling properties for message composer

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBorderWidth** | int | used to set outermost border | 
| **setBorderColor** | @ColorRes\n\nint | used to set border color | 
| **setCornerRadius** | float | used to outermost corner radius | 
| **setBackground** | @ColorRes int | used to set background color | 
| **setInputBackgroundColor** | @ColorRes int | used to set input background color | 
| **setTextAppearance** | @StyleRes int | used to set input text style | 
| **setPlaceHolderTextColor** | @ColorRes int | used to set placeholder text color | 
| **setBackground** | Drawable | used to set Drawable as background | 
| **setAttachIconTint** | @ColorRes\n\nint | used to set attachment icon tint | 
| **setSendIconTint** | @ColorRes\n\nint | used to set send button icon tint | 
| **setSeparatorTint** | @ColorRes\n\nint | used to set separator color | 
| **setVoiceRecordingIconTint** | @ColorRes int | used to set voice recording icon color | 


### Usage

```java
CometChatMessageComposer cometChatMessageComposer=view.findViewById(R.id.composer);
MessageComposerStyle style=new MessageComposerStyle();
  style.setActionSheetSeparatorTint(getResources().getColor(R.color.purple));

 cometChatMessageComposer.setStyle(style);
```



---

## AttachmentOptions

this parameter takes list of `CometChatMessageComposerAction` and gives option to add different options which will be visible when clicked on attachment icon. CometChatMessageComposerAction has the following properties

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setId** | String | unique id for for the attachment option | 
| **setTitle** | String | the name of the attachment option | 
| **setTitleAppearance** | @StyleRes\n\nint | used to set title text style | 
| **setTitleColor** | @ColorRes\n\nint | used to set title text color | 
| **setIcon** | @DrawableRes int | icon that would show on the left of the option name | 
| **setIconTintColor** | @ColorRes\n\nint | used to set custom color for the icon | 
| **setIconBackground** | @ColorRes\n\nint | used to set custom background color for the icon | 
| **setBackground** | @ColorRes\n\nint | used to set custom background color for the entire attachment option | 
| **setCornerRadius** | int | used to set border radius of the entire attachment option | 
| **setOnClick** | OnClick | the action to perform, could be a sending attachments, navigating to another screen etc | 


For instance if we want to add payment option .

```java
CometChatMessageComposer cometChatMessageComposer = view.findViewById(R.id.composer);
        cometChatMessageComposer.setAttachmentOptions((context, user, group, stringStringHashMap) -> {
            List<CometChatMessageComposerAction> actionList = ChatConfigurator.getUtils().getAttachmentOptions(context, user, group, stringStringHashMap);
            actionList.add(new CometChatMessageComposerAction().setTitle("payment").setId("payment").setOnClick(new OnClick() {
                @Override
                public void onClick() {
                    Toast.makeText(context, "payment", Toast.LENGTH_SHORT).show();
                }
            }));
            return actionList;
        });
```

