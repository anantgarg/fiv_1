CometChatTransferOwnership is a component that displays all members of a group, a member can be selected to be made owner of the group. By default when the owner of a group taps on the leave group option in [CometChatDetails](https://www.cometchat.com/docs/v3/android-v4-uikit/group-details) widget they will redirected to CometChatTransferOwnership widget, and for each group member that will be listed, the name of member will be displayed in the title of every list item, the leading view will contain the avatars of the member and status indicator will indicate if that member is online and the trailing view will contain the scope of that member in the group.

`CometChatTransferOwnership` sets up the following functionality internally:

- Search input that can be shown or hidden and allows users to search for specific group member by name or guid.
- fetching list of group members.
- transferring ownership of the group from logged in user to the selected group member

## Components

CometChatTransferOwnership is composed of the [CometChatGroupMembers](https://www.cometchat.com/docs/v3/android-v4-uikit/group-members).

| Component | Description | 
| ---- | ---- | 
| **CometChatGroupMembers** | `CometChatGroupMembers` is a reusable component which lists all the members of a group | 


## How to integrate CometChatTransferOwnership ?

Since `CometChatTransferOwnership` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.transferownership.CometChatTransferOwnership
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_transfer_ownership"
        _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setGroup** | Group | the group for which the group members will be listed. A required parameter. | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | TransferOwnershipStyle | used to set styling properties | 
| **avatarStyle** | AvatarStyle | used to customise the Avatar of the group member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button widget | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideSeparator** | boolean | used to hide the divider separating the group member items | 
| **disableUsersPresence** | boolean | used to control visibility of group member indicator shown if group member is online | 
| **setListItemStyle** | ListItemStyle | used to set style to Tile which displays data obtained from a GroupMember object | 
| **setSubtitleView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom subtitle for every group member item | 
| **setListItemView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to set a custom view for every group member item | 
| **setTailView** | Function3&lt;Context, GroupMember, Group, View&gt; | used to generate a custom trailing view for the group member item, by default it shows the scope of the member in the group | 
| **setSelectionIcon** | @DrawableRes int res | used to override the of the default item selection icon | 
| **setSubmitIcon** | @DrawableRes int res | used to override the default selection complete icon | 
| **onTransferOwnership** | Function(GroupMember, Group) | used to set a custom callback that would override the default functionality of passing ownership to selected group member | 
| **addOnBackPressListener** | OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching group members | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the group members are being fetched | 
| **emptyStateText** | String | used to set a custom text response when the fetched list of group members is empty | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the group members has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of group members | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of group members | 
| **setGroupMembersRequestBuilder** | GroupMembersRequestBuilder | used to set custom group members request builder protocol | 
| **setSearchRequestBuilder** | GroupMembersRequestBuilder | used to set a custom group members request builder | 


## TransferOwnershipStyle

allows you to set styling properties for CometChatTransferOwnership widget

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


```java
CometChatTransferOwnership transferOwnership=findViewById(R.id.transfer_ownership);
TransferOwnershipStyle transferOwnershipStyle=new TransferOwnershipStyle();
transferOwnershipStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark))
transferOwnershipStyle.setTitleColor(getResources().getColor(R.color.primary));
transferOwnership.setStyle(transferOwnershipStyle);
```



---