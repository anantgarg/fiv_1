`CometChatUsers` is a widget that shows the list of users available in your app and gives you the ability to search for a specific user. By default, names are shown for all listed users, along with their avatar if available and a status indicator to show if a user is online or offline.

`CometChatUsers` sets up the following functionality internally:

- Header with customisable title.
- Search box can be hidden and allows users to search for specific user by name or uid if enabled.
- List of users.

## Components

`CometChatUser` is composed with the following widgets:

| Components | Description | 
| ---- | ---- | 
| [CometChatListBase](https://www.cometchat.com/docs/v3/android-v4-uikit/list-base) | a reusable container component having title, search box, customisable background and a List View | 
| [CometChatListItem](https://www.cometchat.com/docs/v3/android-v4-uikit/list-item) | a component that renders data obtained from a User object on a Tile having a title, subtitle, leading and trailing view | 


---

## Usage

`CometChatUsers` can be used inside another widget or can be launched to a new screen.

```xml
<com.cometchat.chatuikit.users.CometChatUsers
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_users"
        _>
```



![](https://uploads.developerhub.io/prod/x9W8/mj0nn88kqhu3bxslc3uf81yz1z5z0t79pjku642hfs11kio8h9kj7g73l9q9op53.jpeg)

## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | AddMembersStyle | used to set styling properties | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the users | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setSearchPlaceholderText** | String | used to set search placeholder text | 
| **backIcon** | @DrawableRes int res | used to set back button icon | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setSearchBoxIcon** | @DrawableRes int res | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideError** | boolean | used to hide error on fetching users . | 
| **hideSeparator** | boolean | used to hide the divider separating the user items | 
| **hideSectionSeparator** | boolean | used to hide the text separating grouped user items | 
| **disableUsersPresence** | boolean | used to control visibility of user indicator shown if user is online | 
| **setListItemView** | Function2&lt;Context, User, View&gt; | used to set a custom view for every user item | 
| **setSubtitleView** | Function2&lt;Context, User, View&gt; | used to set a custom subtitle for every user item | 
| **setTailView** | Function2&lt;Context, User, View&gt; | used to generate a custom trailing view for the user item | 
| **setSelectionIcon** | @DrawableRes int res | used to override the default selection complete icon | 
| **setSubmitIcon** | @DrawableRes int res | used to override the default selection complete icon | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setOptions** | List&lt;CometChatOption&gt;? Function(User, CometChatUsersController) | used to set options affecting the user item in some way, for example- blocking the user, unblocking the user etc. These options will be visible on swiping any user item to the left | 
| **setSelectionMode** | SelectionMode | used to set the number of users that can be selected. By default it is `SelectionMode.multiple`. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | OnSelection | used to set a custom callback that would utilize the selected users to execute some task | 
| **setItemClickListener** | OnItemClickListener | used to set a callback that would be triggered on tapping or long press on a user item | 
| **addOnBackPressListener** | VoidCallback | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching users. | 
| **setLoadingStateView** | @LayoutRes int id | used to set a custom UI response when the users are being fetched | 
| **emptyStateText** | String | used to set a custom text response when fetching the users has returned an empty list | 
| **setEmptyStateView** | @LayoutRes int id | used to set a custom UI response when fetching the users has returned an empty list | 
| **errorStateText** | String | used to set a custom text response when some error occurs on fetching the list of users | 
| **setErrorStateView** | @LayoutRes int id | used to set a custom UI response when some error occurs on fetching the list of users | 
| **setUsersRequestBuilder** | UsersRequest.UsersRequestBuilder | used to set custom users request builder | 
| **setSearchRequestBuilder** | UsersRequest.UsersRequestBuilder | used to set a custom users request builder | 


## usersStyle

allows you to set styling properties for CometChatUsers widget

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
CometChatUsers cometChatUsers=findViewById(R.id.users);

 UsersStyle usersStyle=new UsersStyle();
 usersStyle.setBackground(getResources().getColor(android.R.color.holo_red_dark));
 usersStyle.setTitleColor(getResources().getColor(R.color.primary));

cometChatUsers.setStyle(usersStyle);
```



---

### UsersRequestBuilder

UsersRequestBuilder acts like a filter for fetching users. 

#### Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setLimit** | int | sets the number users that can be fetched in a single request, suitable for pagination | 
| **setSearchKeyword** | String | used for fetching users matching the passed string | 
| **hideBlockedUsers** | bool | used for fetching all those users who are not blocked by the logged in user | 
| **friendsOnly** | bool | used for fetching only those users in which logged in user is a member | 
| **setRoles** | List&lt;String&gt; | used for fetching users containing the passed tags | 
| **setTags** | List&lt;String&gt; | used for fetching users containing the passed tags | 
| **withTags** | bool | used for fetching users containing tags | 
| **setUserStatus** | String | used for fetching users by their status online or offline | 
| **setUIDs** | List&lt;String&gt; | used for fetching users containing the passed users | 


```java
UsersRequest.UsersRequestBuilder builder=new UsersRequest.UsersRequestBuilder()
                .friendsOnly(false)
                        .setLimit(10);
cometChatUsers.setUsersRequestBuilder(builder);
```



---

## Events

To handle events supported by `CometChatUsers` you have to add corresponding listeners by using `CometChatUserEvents`

| Events | Description | 
| ---- | ---- | 
| ccUserBlocked | This will get triggered when the logged in user blocks another user | 
| ccUserUnblocked | This will get triggered when the logged in user unblocks another user | 


```java
CometChatUserEvents.addUserListener("LISTENER_TAG", new CometChatUserEvents() {
            @Override
            public void ccUserBlocked(User user) {
                super.ccUserBlocked(user);
            }

            @Override
            public void ccUserUnblocked(User user) {
                super.ccUserUnblocked(user);
            }
        });
```

