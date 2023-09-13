You can modify the [CometChatUsers](https://www.cometchat.com/docs/v3/android-v4-uikit/users) component's properties using the `UsersConfiguration` object. To use a configuration, you simply need to pass it to respective parameter.

The `UsersConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title in the app bar | 
| **setStyle** | UsersStyle | used to set styling properties | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an User object | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the user | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setSearchPlaceholderText** | String | used to set placeholder text for the search field | 
| **setBackButtonIcon** | @DrawableRes int | used to set back button located in the app bar | 
| **showBackButton** | boolean | used to toggle visibility for back button | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setSearchBoxIcon** | @DrawableRes int | used to set search Icon in the search field | 
| **hideSearch** | boolean | used to toggle visibility for search box | 
| **hideSeparator** | boolean | used to hide the divider separating the user items | 
| **disableUsersPresence** | boolean | used to control visibility of status indicator shown if user is online | 
| **setSubtitle** | Function2&lt;Context, User, View&gt; | used to set a custom subtitle for every user item | 
| **setListItemView** | Function2&lt;Context, User, View&gt; | used to set a custom row item for every user item | 
| **setSelectionIcon** | @DrawableRes\n\nint | used to override the default selection complete icon | 
| **setOptions** | Function2&lt;Context, User, List&lt;CometChatOption&gt;&gt; | used to set options affecting the user item in some way, for example- blocking the user, unblocking the user etc. These options will be visible on swiping any user item to the left | 
| **setSelectionMode** | UIKitConstants.SelectionMode | used to set the number of users that can be selected if activateSelection is not null. SelectionMode can be single, multiple or none. | 
| **setOnSelection** | CometChatUsers.OnSelection | used to set a custom callback that would utilize the selected users to execute some task | 
| **setOnItemClickListener** | OnItemClickListener&lt;User&gt; | used to set a callback that would be triggered on tapping a user item | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching users | 
| **setLoadingStateView** | @LayoutRes\n\nint | used to set a custom UI response when the users are being fetched | 
| **setEmptyStateText** | String | used to set a custom text response when fetching the users has returned an empty list | 
| **setEmptyStateView** | @LayoutRes\n\nint | used to set a custom UI response when fetching the users has returned an empty list | 
| **setErrorStateText** | String | used to set a custom text response when some error occurs on fetching the list of users | 
| **setErrorStateView** | @LayoutRes\n\nint | used to set a custom UI response when some error occurs on fetching the list of users | 
| **setUsersSearchRequestBuilder** | UsersRequestBuilder | used to set a custom users request builder | 
| **setUsersRequestBuilder** | UsersRequestBuilder | used to set a custom users request builder to fetch list of users | 


## How to create Users Configuration Object and use it ?

please refer the below code snippet to create the object of UsersListConfiguration and configure it

```java
UsersConfiguration configuration=new UsersConfiguration().setSearchPlaceholderText("type here")
                .disableUsersPresence(true)
                .hideSearch(false);
```



#### Usage

UsersConfiguration can be use in a module where UsersConfiguration is present as an child component. we can easily set `UsersConfiguration` object to the respective parameter.

```java
usersWithMessages.setUsersConfiguration(configuration);
```

