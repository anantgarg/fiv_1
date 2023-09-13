`CometChatGroups` is a widget that shows a list of groups available in the app and gives users the ability to search for a specific group. By default, for each group that will be listed, the name of the group will be displayed in the title of every list item, the number of members in the subtitle, the icon of the group in the leading view and status indicator icons for indicating a private or password protected group.

`CometChatGroups` sets up the following functionality internally:

- a Search box that can be shown or hidden and allows users to search for specific group by name or guid.
- List of groups.

![](https://uploads.developerhub.io/prod/x9W8/fwmi0z2vhxx8w3jdfqzqvl2q3v1xzyx67zq9d3zeraxwmb3nr5ux2cjasyvddl6s.png)

## Components

CometChatGroups is composed of the [CometChatListBase](https://www.cometchat.com/docs/v3/android-v4-uikit/list-base) and [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item).

| Components | Description | 
| ---- | ---- | 
| **CometChatListBase** | `CometChatListBase` is a container component having a title, search box, customizable `background`, and a List View | 
| **CometChatListItem** | is a component that renders data obtained from a Group object on a Tile having a  title, subtitle, leading and trailing view | 


## How to integrate CometChatGroups ?

Since `CometChatGroups` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.groups.CometChatGroups
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_groups"_>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | GroupsStyle | used to set styling properties | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an Group object | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group is private or password protected | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button widget | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching groups | 
| **hideSeparator** | boolean | used to hide the divider separating the group items | 
| **setPasswordGroupIcon** | @DrawableRes int res | used to set icon shown in place of status indicator for password protected group | 
| **setPrivateGroupIcon** | @DrawableRes int res | used to set icon shown in place of status indicator for private group | 
| **setListItemView** | Function2&lt;Context, Group, View&gt; | used to set a custom view for every group item | 
| **setSubtitleView** | Function2&lt;Context, Group, View&gt; | used to set a custom subtitle for every group item | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | Function2&lt;Context, Group, List&lt;CometChatOption&gt;&gt; | used to set options affecting the group item in some way, for example- leaving the group, deleting the group etc. These options will be visible on swiping any group item to the left | 
| **setSelectionMode** | SelectionMode | used to set the number of groups that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected groups to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping or long press on a group item | 
| **addOnBackPressListener** | OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching groups | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the groups are being fetched | 
| **emptyStateText** | String | used to set a custom text response when the fetched list of groups is empty | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the groups has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of groups | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of groups | 
| **setGroupsRequestBuilder** | GroupsRequest.GroupsRequestBuilder | used to set custom group request builder | 
| **setSearchRequestBuilder** | GroupsRequest.GroupsRequestBuilde[r](/cometchat-documentation/v3/flutter-uikit-beta/groups#groupsrequestbuilder) | used to set a custom groups request builder to perform search. | 


### GroupsStyle

allows you to set styling properties for CometChatGroups widget

#### Properties

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt int | Used to set the background color | 
| **setBorderWidth** | int | Used to set border | 
| **setBorderColor** | @ColorInt int | Used to set border color | 
| **setCornerRadius** | float | Used to set border radius | 
| **setBackground** | Drawable | Used to set background Drawable | 
| **setTitleAppearance** | @StyleRes int | Used to customise the appearance of the title in the app bar | 
| **setBackIconTint** | @ColorInt int | Used to set the color of the back icon in the app bar | 
| **setSearchBackground** | @ColorInt int | Used to set the background color of the search box | 
| **setSearchBorderRadius** | int | Used to set the border radius of the search box | 
| **setSearchIconTint** | @ColorInt int | Used to set the color of the search icon in the search box | 
| **setSearchBorderWidth** | int | Used to set the border width of the search box | 
| **setSearchTextAppearance** | @StyleRes int | Used to set the style of the text in the search box | 
| **setLoadingIconTint** | @ColorInt int | Used to set the color of the icon shown while the list of group members is being fetched | 
| **setEmptyTextAppearance** | @StyleRes int | Used to set the style of the response text shown when fetchig the list of group members has returned an empty list | 
| **setErrorTextAppearance** | @StyleRes int | Used to set the style of the response text shown in case some error occurs while fetching the list of group members | 
| **setOnlineStatusColor** | @ColorInt int | Used to set the color of the status indicator shown if a group member is online | 
| **setSeparatorColor** | @ColorInt int | Used to set the color of the divider separating the group member items | 
| **setSubTitleTextAppearance** | @StyleRes int | Used to customise the appearance of the subtitle Text in the group List item | 


```dart
CometChatGroups cometChatGroups=findViewById(R.id.groups);

GroupsStyle groupsStyle=new GroupsStyle();
groupsStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark));
groupsStyle.setTitleColor(getResources().getColor(R.color.primary));
cometChatGroups.setStyle(groupsStyle);
```



### GroupsRequestBuilder

GroupsRequestBuilder acts like a filter for fetching groups. 

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setLimit** | int | sets the number groups that can be fetched in a single request, suitable for pagination | 
| **setSearchKeyWord** | String | used for fetching groups matching the passed string | 
| **joinedOnly** | bool | used for fetching only those groups in which logged in user is a member | 
| **setTags** | List&lt;String&gt; | used for fetching groups containing the passed tags | 
| **withTags** | bool | used for fetching groups with tags | 


```java
cometChatGroups.setGroupsRequestBuilder(new GroupsRequest.GroupsRequestBuilder()
                                        .setLimit(10).joinedOnly(false));
```



---

## Events

To handle events supported by `CometChatGroups` you have to add corresponding listeners by using `CometChatGroupEventListener`

| Events | Description | 
| ---- | ---- | 
| ccGroupCreated | This will get triggered when the logged in user creates a group | 
| ccGroupDeleted | This will get triggered when the logged in user deletes a group | 
| ccGroupLeft | This will get triggered when the logged in user leaves a group | 
| ccGroupMemberScopeChanged | This will get triggered when the logged in user changes the scope of another group member | 
| ccGroupMemberBanned | This will get triggered when the logged in user bans a group member from the group | 
| ccGroupMemberKicked | This will get triggered when the logged in user kicks another group member from the group | 
| ccGroupMemberUnbanned | This will get triggered when the logged in user unbans a user banned from the group | 
| ccGroupMemberJoined | This will get triggered when the logged in user joins a group | 
| ccGroupMemberAdded | This will get triggered when the logged in user add new members to the group | 
| ccOwnershipChanged | This will get triggered when the logged in user transfer the ownership of their group to some other member | 


```java
CometChatGroupEvents.addGroupListener("LISTENER_TAG", new CometChatGroupEvents() {
            @Override
            public void ccGroupCreated(Group group) {
                super.ccGroupCreated(group);
            }

            @Override
            public void ccGroupDeleted(Group group) {
                super.ccGroupDeleted(group);
            }

            @Override
            public void ccGroupLeft(Action actionMessage, User leftUser, Group leftGroup) {
                super.ccGroupLeft(actionMessage, leftUser, leftGroup);
            }

            @Override
            public void ccGroupMemberJoined(User joinedUser, Group joinedGroup) {
                super.ccGroupMemberJoined(joinedUser, joinedGroup);
            }

            @Override
            public void ccGroupMemberAdded(List<Action> actionMessages, List<User> usersAdded, Group userAddedIn, User addedBy) {
                super.ccGroupMemberAdded(actionMessages, usersAdded, userAddedIn, addedBy);
            }

            @Override
            public void ccGroupMemberKicked(Action actionMessage, User kickedUser, User kickedBy, Group kickedFrom) {
                super.ccGroupMemberKicked(actionMessage, kickedUser, kickedBy, kickedFrom);
            }

            @Override
            public void ccGroupMemberBanned(Action actionMessage, User bannedUser, User bannedBy, Group bannedFrom) {
                super.ccGroupMemberBanned(actionMessage, bannedUser, bannedBy, bannedFrom);
            }

            @Override
            public void ccGroupMemberUnBanned(Action actionMessage, User unbannedUser, User unBannedBy, Group unBannedFrom) {
                super.ccGroupMemberUnBanned(actionMessage, unbannedUser, unBannedBy, unBannedFrom);
            }

            @Override
            public void ccGroupMemberScopeChanged(Action actionMessage, User updatedUser, String scopeChangedTo, String scopeChangedFrom, Group group) {
                super.ccGroupMemberScopeChanged(actionMessage, updatedUser, scopeChangedTo, scopeChangedFrom, group);
            }

            @Override
            public void ccOwnershipChanged(Group group, GroupMember newOwner) {
                super.ccOwnershipChanged(group, newOwner);
            }
        });
```

