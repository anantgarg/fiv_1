`CometChatAddMembers` is a component that displays all users available in the app to add them to a group. By default, names are shown for all listed users, along with their avatar if available and a status indicator to show if a user is online or offline.

`CometChatAddMembers` sets up the following functionality internally:

- Search box that can be shown or hidden and allows users to search for specific user by name or guid.
- fetching list of users using CometChatUsers component.

## Components

CometChatAddMembers is composed of the [CometChatUsers](https://www.cometchat.com/docs/v3/android-v4-uikit/users).

| Component | Description | 
| ---- | ---- | 
| **CometChatUsers** | `CometChatUsers` is component that displays a list of Users | 


## How to integrate CometChatAddMembers ?

Since `CometChatAddMembers` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

#### Usage

```xml
<com.cometchat.chatuikit.addmembers.CometChatAddMembers
        android:id="@+id_add_members"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



## Properties

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setGroup** | Group | the group to which the users selected will be added. A required parameter. | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | AddMembersStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the group member | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a group member is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button icon | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching users and failing to add selected users to the group. | 
| **hideSeparator** | boolean | used to hide the divider separating the user items | 
| **hideSectionSeparator** | boolean | used to hide the text separating grouped user items | 
| **disableUsersPresence** | boolean | used to control visibility of user indicator shown if user is online | 
| **setListItemView** | Function2&lt;Context, User, View&gt; | used to set a custom view for every user item | 
| **setSubtitleView** | Function2&lt;Context, User, View&gt; | used to set a custom subtitle for every user item | 
| **setTailView** | Function2&lt;Context, User, View&gt; | used to generate a custom trailing view for the user item | 
| **setSelectionIcon** | @DrawableRes int res | used to override the default selection complete icon | 
| **setSubmitIcon** | @DrawableRes int res | used to override the default selection complete icon | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | Function2&lt;Context, User, List&lt;CometChatOption&gt;&gt; | used to set options affecting the user item in some way, for example- blocking the user, unblocking the user etc. These options will be visible on swiping any user item to the left | 
| **setSelectionMode** | SelectionMode | used to set the number of users that can be selected. By default it is `SelectionMode.multiple`. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected users to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping or long press on a user item | 
| **addOnBackPressListener** | VoidCallback | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching users or failing to add selected members | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the users are being fetched | 
| **emptyStateText** | String | used to set a custom text response when fetching the users has returned an empty list | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the users has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of users | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of users | 
| **setUsersRequestBuilder** | UsersRequest.UsersRequestBuilder | used to set custom users request builder | 
| **setSearchRequestBuilder** | UsersRequest.UsersRequestBuilder | used to set a custom users request builder | 


## addMembersStyle

allows you to set styling Methods for CometChatAddMembers widget

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
| **setSectionHeaderTextAppearance** | @StyleRes int | Used to customise the appearance of the section header text. | 
| **setSectionHeaderTextColor** | @ColorInt int | Used to set the color of the section header text. | 


```java
CometChatAddMembers addMembers=findViewById(R.id.add_members);

AddMembersStyle addMembersStyle = new AddMembersStyle();
addMembersStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark))
addMembersStyle.setTitleColor(getResources().getColor(R.color.primary));

addMembers.setStyle(addMembersStyle);
```



---