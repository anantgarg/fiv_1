CometChatGroupMembers is a component that displays all members of a group. By default, for each group member that will be listed, the name of member will be displayed in the title of every list item, the leading view will contain the avatars of the member and status indicator will indicate if that member is online and the trailing view will contain the scope of that member in the group.

`CometChatGroupMembers` sets up the following functionality internally:

- Search input that can be shown or hidden and allows users to search for specific group member by name or guid.
- fetching list of group members.

## Components

CometChatGroupMembers is composed of the [CometChatListBase](https://www.cometchat.com/docs/v3/android-v4-uikit/list-base) and [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item).

| Component | Description | 
| ---- | ---- | 
| **CometChatListBase** | `CometChatListBase` is a reusable container component having title, search box, customizable background and a List View | 
| **CometChatListItem** | is a component that renders data obtained from a GroupMember object on a Tile having a title, subtitle, leading and trailing view | 


## How to integrate CometChatGroupMembers ?

Since `CometChatGroupMembers` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.groupmembers.CometChatGroupMembers
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_group_member"
        _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setGroup** | Group | the group for which the group members will be listed. A required parameter. | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | GroupMembersStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button widget | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching group members | 
| **hideSeparator** | boolean | used to hide the divider separating the group member items | 
| **disableUsersPresence** | boolean | used to control visibility of group member indicator shown if group member is online | 
| **setListItemView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every group member item | 
| **setListItemStyle** | ListItemStyle | used to set style to Tile which displays data obtained from a GroupMember object | 
| **setSubtitleView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every group member item | 
| **setTailView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to generate a custom trailing view for the group member item, by default it shows the scope of the member in the group | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | Function3&lt;Context, GroupMember, Group, List&lt;CometChatOption&gt;&gt; | used to set options affecting the group member item in some way, for example- banning the group member, kicking the group member etc. These options will be visible on swiping any group member item to the left | 
| **setSelectionIcon** | @DrawableRes int selectionIcon | used to override the of the default item selection icon | 
| **setSubmitIcon** | @DrawableRes int submitIcon | used to override the default selection complete icon | 
| **setSelectionMode** | SelectionMode | used to set the number of group members that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected group members to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping or long press on a group member item | 
| **addOnBackPressListener** | OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching group members | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the group members are being fetched | 
| **emptyStateText** | String | used to set a custom text response when the fetched list of group members is empty | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the group members has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of group members | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of group members | 
| **setGroupMembersRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 
| **setSearchRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder to perform search | 


### GroupMembersStyle

allows you to set styling properties for CometChatGroupMembers View

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackground** | @ColorInt\n\nint | Used to set the background color | 
| **setBorderWidth** | int | Used to set border | 
| **setBorderColor** | @ColorInt\n\nint | Used to set border color | 
| **setCornerRadius** | float | Used to set border radius | 
| **setBackground** | Drawable | Used to set background Drawable | 
| **setTitleAppearance** | @StyleRes\n\nint | Used to customise the appearance of the title in the app bar | 
| **setBackIconTint** | @ColorInt\n\nint | Used to set the color of the back icon in the app bar | 
| **setSearchBackground** | @ColorInt\n\nint | Used to set the background color of the search box | 
| **setSearchBorderRadius** | int | Used to set the border radius of the search box | 
| **setSearchIconTint** | @ColorInt\n\nint | Used to set the color of the search icon in the search box | 
| **setSearchBorderWidth** | int | Used to set the border width of the search box | 
| **setSearchTextAppearance** | @StyleRes\n\nint | Used to set the style of the text in the search box | 
| **setLoadingIconTint** | @ColorInt\n\nint | Used to set the color of the icon shown while the list of group members is being fetched | 
| **setEmptyTextAppearance** | @StyleRes\n\nint | Used to set the style of the response text shown when fetchig the list of group members has returned an empty list | 
| **setErrorTextAppearance** | @StyleRes\n\nint | Used to set the style of the response text shown in case some error occurs while fetching the list of group members | 
| **setOnlineStatusColor** | @ColorInt\n\nint | Used to set the color of the status indicator shown if a group member is online | 
| **setSeparatorColor** | @ColorInt\n\nint | Used to set the color of the divider separating the group member items | 


```java
CometChatGroupMembers groupMembers=findViewById(R.id.group_member);

GroupMembersStyle groupMembersStyle = new GroupMembersStyle();     groupMembersStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark))
groupMembersStyle.setTitleColor(getResources().getColor(R.color.primary));

groupMembers.setStyle(groupMembersStyle);
```



---

## GroupMembersRequestBuilder

GroupMembersRequestBuilder acts like a filter for fetching group members. It contains the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setLimit** | int | sets the number group members that can be fetched in a single request, suitable for pagination | 
| **setSearchKeyword** | String | used for fetching  group members  matching the passed string | 
| **setScopes** | List&lt;String&gt; | used for fetching group members having matching scopes which may be of participant, moderator, admin and owner | 


```java
CometChatGroupMembers groupMembers=findViewById(R.id.group_member); 

GroupMembersRequest.GroupMembersRequestBuilder groupMembersRequestBuilder= new GroupMembersRequest.GroupMembersRequestBuilder(id).setLimit(limit);

groupMembers.setGroupMembersRequestBuilder(groupMembersRequestBuilder)
```



## CometChatGroupMemberOption

`CometChatOption` is the class providing structure for options to be shown for group members

### Properties

| Properties | Type | Description | 
| ---- | ---- | ---- | 
| **onClick** | OnClick | the action to perform on a item in the list of group members | 
| **id** | String | unique ID for the option | 
| **title** | String | a text to display below the icon | 
| **icon** | @DrawableRes\n\nint | the path of the image to display as icon for the option | 
| **backgroundColor** | @ColorInt\n\nint | used to set background color | 
