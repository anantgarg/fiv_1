You can modify the `UserList` component's properties using the `UserListConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `UserListConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| hide(sectionHeader: Bool) | If set to false, visibility of the header will be gone from the `CometChatUserList` | 
| set(friendsOnly: Bool) | If set to true, it will only fetch users who are friends with the loggedin user into `CometChatUserList` | 
| hide(blockedUsers: Bool) | If set to true, It will exclude all the block user while fetching the user List | 
| hide(error: Bool) | If set to true, it will hide error Ui from the screen | 
| set(searchKeyword: String) | This method is used to fetch user List in to `CometChatUserList` based on keyword provided | 
| set(status: CometChat.UserStatus) | This method is used to fetch userList based on the status provided in to `CometChatUserList` | 
| set(limit: Int) | This will set the number of users to be fetched in one go. | 
| set(tags: [String]) | This will fetch filtered list in to CometChatUserList based on given array of String | 
| set(roles: [String]) | This will fetch filtered list in to CometChatUserList based on given array of String | 
| set(uids: [String]) | This will fetch filtered list in to CometChatUserList based on given array of String | 
| set(emptyView: UIView?) | This will load the view when the user List is empty | 
| set(errorText: String?) | This will load the user defined text , when any error occurs. | 
| set(emptyText: String?) | This will load the user defined text , when list is empty. | 


## How to create UsersListConfiguration Object and use it ?

#### Please refer the below code snippet to create the object of UsersListConfiguration and configure it

```swift
__creating object of UsersListConfiguration
let userListConfiguration = UserListConfiguration()

var roles:[String] = [String]()  __ Array of roles which user wants to display in list of users
var tags:[String] = [String]()   __ Array of tags which user wants to display in list of users
var uids:[String] = [String]()   __ Array of uids which user wants to display in list of users

__setting all the configuration value to the object
   userListConfiguration.set(searchKeyword: "Searched Text")
                        .hide(sectionHeader: false)
                        .set(limit: 30)
                        .set(roles: roles)
                        .set(tags: tags)
                        .set(uids: uids)
                        .set(friendsOnly: false)
                        .hide(blockedUsers: false)
                        .set(emptyView: nil)
                        .set(errorText: "Something went wrong!")
                        .set(emptyText: "empty list")
```



## Usage

UsersListConfiguration can be use in a module where CometChatUsersList is present as an child component. we can easily set `UsersListConfiguration` object to the parent component by calling setConfiguration method.

```swift
set(configurations: [userListConfiguration])
```

