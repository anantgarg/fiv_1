You can modify the  [CometChatGroups](https://www.cometchat.com/docs/v3/android-v4-uikit/groups) component's properties using the `GroupsConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `GroupsConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | GroupsStyle | used to set styling properties | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an Group object | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group is private or password protected | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **setBackButtonIcon** | @DrawableRes int | used to set back button widget | 
| **setShowBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int | used to set search Icon in the search field | 
| **setHideSearch** | boolean | used to toggle visibility for search box | 
| **setHideSeparator** | boolean | used to hide the divider separating the group items | 
| **setPasswordGroupIcon** | Widget | used to set icon shown in place of status indicator for password protected group | 
| **setPrivateGroupIcon** | Widget | used to set icon shown in place of status indicator for private group | 
| **setCustomView** | Widget Function(Group) | used to set a custom view for every group item | 
| **setSubtitle** | Widget Function(BuildContext, Group) | used to set a custom subtitle for every group item | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | Function2&lt;Context, Group, List&lt;CometChatOption&gt;&gt; | used to set options affecting the group item in some way, for example- leaving the group, deleting the group etc. These options will be visible on swiping any group item to the left | 
| **setSelectionMode** | SelectionMode | used to set the number of groups that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | CometChatGroups.OnSelection | used to set a custom callback that would utilize the selected groups to execute some task | 
| **setItemClickListener** | OnItemClickListener&lt;Group&gt; | used to set a callback that would be triggered on tapping a groups item | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching groups | 
| **setLoadingStateView** | @LayoutRes int | used to set a custom UI response when the groups are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when the fetched list of groups is empty | 
| **setEmptyStateView** | @LayoutRes int | used to set a custom UI response when fetching the groups has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of groups | 
| **setErrorStateView** | @LayoutRes int | used to set a custom UI response when some error occurs on fetching the list of groups | 
| **setGroupsRequestBuilder** | GroupsRequestBuilder | used to set a custom groups request builder | 
| **setGroupsSearchRequestBuilder** | GroupsRequestBuilder | used to set a custom groups request builder to perform custom search | 


## How to create a GroupsConfiguration object and use it ?

please refer the below code snippet to create the object of GroupsConfiguration and configure it

```java
GroupsConfiguration configuration=new GroupsConfiguration().setHideSearch(true);
```



## Usage

ConversationsConfiguration can be used in a widget where CometChatGroups is present as a child component. We just pass that `GroupsConfiguration` object to the CometChatGroups widget.

```java
cometChatGroupsWithMessages.setCreateGroupConfiguration(configuration);
```

