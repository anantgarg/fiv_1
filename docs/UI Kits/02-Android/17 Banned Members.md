CometChatBannedMembers is a component that displays all users banned from the group. By default, for each banned member that will be listed, the name of member will be displayed in the title of every list item, the leading view will contain the avatars of the member and the trailing view will contain the text "banned". 

`CometChatBannedMembers` sets up the following functionality internally:

- fetching list of users banned from the group
- ability to unban banned users

## Components

CometChatBannedMembers is composed of the [CometChatListBase](https://www.cometchat.com/docs/v3/android-v4-uikit/list-base) and [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item).

| Component | Description | 
| ---- | ---- | 
| **CometChatListBase** | `CometChatListBase` is a reusable container component having title, search box, customizable background and a List View | 
| **CometChatListItem** | is a component that renders data obtained from a Group Member object on a Tile having a title, subtitle, leading and trailing view | 


## How to integrate CometChatBannedMembers ?

Since `CometChatBannedMembers` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.bannedmembers.CometChatBannedMembers
        android:id="@+id_banned_members"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setGroup** | Group | the group for which the banned members will be listed. a required parameter. | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | BannedMembersStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the banned member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a banned member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button widget | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching banned members | 
| **hideSeparator** | boolean | used to hide the divider separating the banned member items | 
| **disableUsersPresence** | boolean | used to control visibility of banned member indicator shown if user is online | 
| **setListItemView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every banned member item | 
| **setListItemStyle** | [ListItemStyle](/cometchat-documentation/v3/flutter-uikit-beta/list-item#listitemstyle) | used to set style to Tile which displays data obtained from a GroupMember object | 
| **setSubtitleView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every banned member item | 
| **setOptions** | Function3&lt;Context,GroupMember, Group, List&lt;CometChatOption&gt;&gt; | used to set options affecting the banned member item in some way, by default option to unban the banned member is available. These options will be visible on swiping any banned member item to the left | 
| **selectionMode** | SelectionMode | used to set the number of banned members that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected banned members to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping a banned member item | 
| **addOnBackPressListener** | OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching banned members | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the banned members are being fetched | 
| **emptyStateText** | String | used to set a custom text response when the fetched list of banned members is empty | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the banned members has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of banned members | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of banned members | 
| **bannedMemberProtocol** | BannedMemberBuilderProtocol | used to set custom banned members request builder protocol | 
| **bannedMemberRequestBuilder** | BannedGroupMembersRequestBuilder | used to set a custom banned members request builder | 


### BannedMembersStyle

allows you to set styling Methods for CometChatBannedMembers widget

| Method | Type | Description | 
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


```java
CometChatBannedMembers bannedMember = findViewById(R.id.banned_members);
BannedMembersStyle bannedMemberStyle = new BannedMembersStyle();
bannedMemberStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark))
bannedMemberStyle.setTitleColor(getResources().getColor(R.color.primary));
bannedMember.setStyle(bannedMemberStyle);
```



---

### BannedMemberRequestBuilder

BannedGroupMembersRequestBuilder acts like a filter for fetching banned members. It contains the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setLimit** | int | sets the number banned members that can be fetched in a single request, suitable for pagination | 
| **setSearchKeyword** | String | used for fetching  banned members  matching the passed string | 


```java
CometChatBannedMembers bannedMembers=findViewById(R.id.banned_members);

BannedGroupMembersRequest.BannedGroupMembersRequestBuilder bannedGroupMembersRequestBuilder= new BannedGroupMembersRequest.BannedGroupMembersRequestBuilder("id").setLimit(5);

bannedMembers.setBannedGroupMembersRequestBuilder(bannedGroupMembersRequestBuilder);
```

