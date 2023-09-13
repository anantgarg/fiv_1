You can modify the [CometChatGroupMembers](https://www.cometchat.com/docs/v3/android-v4-uikit/group-members) component's properties using the `GroupMembersConfiguration` object. To use a configuration, you simply need to pass it to CometChatGroupMembers from its parent component.

The `GroupMembersConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | GroupMembersStyle | used to set styling properties | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an GroupMember object | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **setBackButtonIcon** | @DrawableRes\n\nint | used to set back button widget | 
| **setShowBackButton** | boolean | used to toggle visibility for back button | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setSearchBoxIcon** | @DrawableRes\n\nint | used to set search Icon in the search field | 
| **setHideSearch** | boolean | used to toggle visibility for search box | 
| **setHideSeparator** | boolean | used to hide the divider separating the group items | 
| **setCustomView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every group member item | 
| **setSubtitleView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every group member item | 
| **setOptions** | List&lt;CometChatOption&gt; Function(Group, GroupMember, CometChatGroupMembersController, BuildContext) | used to set options affecting the group member item in some way, for example- banning the group member, kicking the group member etc. These options will be visible on swiping any group member item to the left | 
| **setSelectionIcon** | @DrawableRes\n\nint | used to override the of the default item selection icon | 
| **setSubmitIcon** | @DrawableRes\n\nint | used to override the default selection complete icon | 
| **setSelectionMode** | SelectionMode | used to set the number of groups that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | CometChatGroupMembers.OnSelection | used to set a custom callback that would utilize the selected group members to execute some task | 
| **setOnItemClickListener** | OnItemClickListener&lt;GroupMember&gt; | used to set a callback that would be triggered on tapping a group members item | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching group members | 
| **setLoadingStateView** | @LayoutRes\n\nint | used to set a custom UI response when the group members are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when the fetched list of groups is empty | 
| **setEmptyStateView** | @LayoutRes\n\nint | used to set a custom UI response when fetching the group members has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of group members | 
| **setErrorStateView** | @LayoutRes\n\nint | used to set a custom UI response when some error occurs on fetching the list of group members | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an GroupMember object | 
| **setMembersRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 
| **setMembersSearchRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 


## How to create a GroupMembersConfiguration object and use it ?

please refer the below code snippet to create the object of GroupMembersConfiguration and configure it

```java
GroupMembersConfiguration configuration=new GroupMembersConfiguration()
                .setDisableUsersPresence(true)
                .setHideSearch(false);
```



## Usage

GroupMembersConfiguration can be used in a widget where CometChatGroupMembers is present as a child component. We just pass that `GroupMembersConfiguration` object to its parent widget.

```java
cometChatDetails.setGroupMembersConfiguration(configuration);
```

