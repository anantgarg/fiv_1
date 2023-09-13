You can modify the [CometChatTransferOwnership](https://www.cometchat.com/docs/v3/android-v4-uikit/transfer-ownership) component's properties using the `TransferOwnershipConfiguration` object. To use a configuration, you simply need to pass it to `CometChatTransferOwnership` from its parent component.

The `TransferOwnershipConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | TransferOwnershipStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **setBackButtonIcon** | @DrawableRes int | used to set back button widget | 
| **setShowBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int | used to set search Icon in the search field | 
| **setHideSearch** | boolean | used to toggle visibility for search box | 
| **setHideSeparator** | boolean | used to hide the divider separating the group member items | 
| **setListItemStyle** | ListItemStyle | used to set style to Tile which displays data obtained from a GroupMember object | 
| **setSubtitleView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every group member item | 
| **setCustomView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every group member item | 
| **setSelectionIcon** | @DrawableRes int | used to override the of the default item selection icon | 
| **setSubmitIcon** | @DrawableRes int | used to override the default selection complete icon | 
| **setOnTransferOwnership** | CometChatTransferOwnership.OnTransferOwnership | used to set a custom callback that would override the default functionality of passing ownership to selected group member | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching group members | 
| **setLoadingStateView** | @LayoutRes int | used to set a custom UI response when the group members are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when the fetched list of group members is empty | 
| **setEmptyStateView** | @LayoutRes int | used to set a custom UI response when fetching the group members has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of group members | 
| **setErrorStateView** | @LayoutRes int | used to set a custom UI response when some error occurs on fetching the list of group members | 
| **setMembersRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 
| **setMembersSearchRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 


## How to create a TransferOwnershipConfiguration object and use it ?

please refer the below code snippet to create the object of TransferOwnershipConfiguration and configure it.

```java
TransferOwnershipConfiguration configuration=new TransferOwnershipConfiguration().setTitle("Transfer");
```



### Usage

TransferOwnershipConfiguration can be used in a widget where CometChatTransferOwnership is present as a child component. We just pass that `TransferOwnershipConfiguration` object to its parent widget.

```dart
cometChatDetails.setTransferOwnershipConfiguration(configuration);
```

