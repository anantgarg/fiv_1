You can modify the [CometChatBannedMembers](https://www.cometchat.com/docs/v3/android-v4-uikit/banned-members) component's properties using the `BannedMemberConfiguration` object. To use a configuration, you simply need to pass it to CometChatBannedMembers from its parent component.

The `BannedMemberConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | BannedMembersStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the banned member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a banned member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **setBackButtonIcon** | @DrawableRes\n\nint | used to set back button widget | 
| **setShowBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes\n\nint | used to set search Icon in the search field | 
| **setHideSearch** | boolean | used to toggle visibility for search box | 
| **setHideSeparator** | boolean | used to hide the divider separating the banned member items | 
| **setCustomView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every banned member item | 
| **setListItemStyle** | ListItemStyle | used to set style to Tile which displays data obtained from a GroupMember object | 
| **setSubtitle** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every banned member item | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | Function3&lt;Context, GroupMember, Group, List&lt;CometChatOption&gt;&gt; | used to set options affecting the banned member item in some way, by default option to unban the banned member is available. These options will be visible on swiping any banned member item to the left | 
| **setSelectionMode** | UIKitConstants.SelectionMode | used to set the number of banned members that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | CometChatBannedMembers.OnSelection | used to set a custom callback that would utilize the selected banned members to execute some task | 
| **setOnItemClickListener** | OnItemClickListener&lt;GroupMember&gt; | used to set a callback that would be triggered on tapping a banned member item | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching banned members | 
| **setLoadingStateView** | @LayoutRes\n\nint | used to set a custom UI response when the banned members are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when the fetched list of banned members is empty | 
| **setEmptyStateView** | @LayoutRes\n\nint | used to set a custom UI response when fetching the banned members has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of banned members | 
| **setErrorStateView** | @LayoutRes\n\nint | used to set a custom UI response when some error occurs on fetching the list of banned members | 
| **setBannedMembersRequestBuilder** | BannedGroupMembersRequestBuilder | used to set a custom banned members request builder | 
| **setBannedMembersSearchRequestBuilder** | BannedGroupMembersRequestBuilder | used to set a custom banned members request builder to perform custom search | 


---

## How to create a BannedMemberConfiguration object and use it ?

please refer the below code snippet to create the object of BannedMemberConfiguration and configure it.

```java
BannedMembersConfiguration configuration=new BannedMembersConfiguration()
                .setHideSeparator(true)
                .setHideSearch(false);
```



### Usage

BannedMemberConfiguration can be used in a widget where CometChatBannedMembers is present as a child component. We just pass that `BannedMembersConfiguration` object to its parent widget.

```java
cometChatDetails.setBannedMembersConfiguration(configuration);
```

