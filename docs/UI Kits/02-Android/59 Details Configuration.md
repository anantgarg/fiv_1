You can modify the [CometChatDetails](https://www.cometchat.com/docs/v3/android-v4-uikit/group-details) component's properties using the `DetailsConfiguration` object. To use a configuration, you simply need to pass it to `CometChatDetails` from its parent component.

The `DetailsConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setStyle** | DetailsStyle | used to customize the appearance of the widget | 
| **showCloseButton** | boolean | used to toggle visibility for back button | 
| **setCloseButtonIcon** | @DrawableRes\n\nint | used to set back button located in the app bar | 
| **setData** | Function3&lt;Context, User, Group, List&lt;CometChatDetailsTemplate&gt;&gt; | used to override list of templates is passed which is used for displaying relevant options | 
| **setGroupMembersConfiguration** | [GroupMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/group-members-configuration) | used to customize `CometChatGroupMembers` being used internally | 
| **setAddMembersConfiguration** | [AddMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/add-members-configuration) | used to customize `CometChatAddMembers` being used internally | 
| **setTransferOwnershipConfiguration** | [TransferOwnershipConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/transfer-ownership-configuration) | used to customize `CometChatTransferOwnerip` being used internally | 
| **setBannedMembersConfiguration** | [BannedMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/banned-members-configuration) | used to customize `CometChatBannedMembers` being used internally | 
| **disableUsersPresence** | boolean | used to control visibility of status indicator shown if user is online | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an Conversation object | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the user and group shown in the leading view of the conversation item | 
| **setPrivateGroupIcon** | @DrawableRes\n\nint | used to set icon shown in place of status indicator if the conversation is taking place in a private group | 
| **setProtectedGroupIcon** | @DrawableRes\n\nint | used to set icon shown in place of status indicator if the conversation is taking place in a password protected group | 
| **setSubtitleView** | Function3&lt;Context, User, Group, View&gt; | used to set a custom subtitle for every conversation item | 
| **setCustomProfileView** | Function3&lt;Context, User, Group, View&gt; | provides a customized view profile for users | 
| **hideProfile** | bool | hides view profile option for users | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching conversations | 


## How to create a DetailsConfiguration object and use it ?

please refer the below code snippet to create the object of `DetailsConfiguration` and configure it.

```java
DetailsConfiguration configuration=new DetailsConfiguration().hideProfile(false);
```



### Usage

`DetailsConfiguration` can be used in a widget where `CometChatDetails` is present as a child component. We just pass that `DetailsConfiguration` object to its parent widget.

```java
cometChatMessages.setDetailsConfiguration(configuration);
```

