## Overview

**`CometChatUserList`** retrieves the list of users. By default, it fetches 30 users. It uses `UsersRequestBuilder` class of the CometChat SDK to retrieve the list of users.The state of the component is communicated in 3 ways i.e. **empty**, **loading** and **error**.

![](https://uploads.developerhub.io/prod/x9W8/ztbbtc1mn7yce7rcxonckrgbgwjsvz6syguvn2y63bcj9s9bneods2rro6bgs71q.jpg)

---

## Components

CometChatUserList mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatDataItem** | This component’s view consists of **avatar**, **status indicator** , **title**, and **subtitle**. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. This Component also have Tail (Placeholder to load any component in it ) | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/data-item) | 


---

## Methods

### Background

The background is a `UIView` which is present in the backdrop for **`UserList.`** You will be able to modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| set(background: [UIColor]) | This method will set the background color for `UserList`, it can take an array of multiple colors for the gradient background. | 


```swift
__ syntax for set(background: [UIColor])
userList.set(background: [UIColor(hex:"FF606D").cgColor])
```



![](https://uploads.developerhub.io/prod/x9W8/02ocjddmxlt0712kxzbtkeolyck0q5vsx4d3irwg4zak5p2uatmo0p8ge43vm1lf.png)

---

### Controller

This method will set the instance of the view controller from which the **`UserList`** is presented. 

| Method | Description | 
| ---- | ---- | 
| `set(controller: UIViewController)` | This method will set the instance of the view controller from which the UserList is presented. | 


```swift
__ syntax for set(controller: UIViewController)
userList.set(controller: self)
```



> To present the another view controller/popup or presentation controller from user list, user must have to call this method which will take the instance of the view controller to launch respective view.

---

### Section Header

Section header is a header which segregates the user list and displays a letter in alphabetical order. User can modify the header properties using below methods.

|  |  | 
| ---- | ---- | 
| set(sectionHeaderBackground: UIColor) | This method will set the background color for section of the header. | 
| set(sectionHeaderTextColor: UIColor) | This method will set the text color for section of the header. | 
| set(sectionHeaderTextFont: UIFont) | This method will set the text font for section of the header. | 
| hide(sectionHeader:Bool) | This method will hide section of the header. | 


```swift
__ syntax for set(sectionHeaderBackground: UIColor)
userList.set(sectionHeaderBackground: UIColor(hex:"FF606D"))

__ syntax for set(sectionHeaderTextColor: UIColor)	
userList.set(sectionHeaderTextColor: .white)

__ syntax for set(sectionHeaderTextFont: UIFont)
userList.set(sectionHeaderTextFont: UIFont(name: "AmericanTypewriter-Bold", size: 13))

__ syntax for hide(sectionHeader:Bool)
userList.hide(sectionHeader:false)
```



![](https://uploads.developerhub.io/prod/x9W8/736t8p4mffg6tvcxi2es2b3sdh00zx506lxjfq54dw8qta1d8ti8sl61lf04yfg3.png)

---

### Set Limit

This method will specify the option to set the limit to fetch users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(limit: Int) | This method will specify the option to set the limit to fetch users in **`UserList` .** | 


```swift
__ syntax for set(limit: Int)
userList.set(limit: 30)
```



---

### Set Search Keyword

This method will specify the option to set the keyword to fetch users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(searchKeyword: String) | This method will specify the option to set the keyword to fetch users in **`UserList` .** | 


```swift
__ syntax for set(searchKeyword: String)
userList.set(searchKeyword: "searched text")
```



---

### Set List

This method will allow the user to set the list of users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(userList: [Users]) | This method will allow the user to set the  list of users  in **`UserList` .** | 


```swift
__ syntax for set(userList: [Users])
let users = [user1, user2, user3] __ Array of predefined sets of 'User' Object
userList.set(userList: [users])
```



---

### Set Tags

This method will allow the user to filter the users using tags in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| `set(tags:[String])` | This method will set the tags for users  in **`UserList` .** | 


```swift
__ syntax for set(tags:[String])
userList.set(tags:["economy", "premium"])
```



---

### Set FriendsOnly

This method will enable the friends only mode for users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(friendsOnly:Bool) | This method will enable the friends only mode for users in **`UserList` .** | 


```swift
__ syntax for set(friendsOnly:Bool)
userList.set(friendsOnly:true)
```



---

### Hide Blocked Users

This method will hide the blocked users from users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(hideBlockedUsers:Bool) | This method will hide the blocked users from users in **`UserList` .** | 


```swift
__ syntax for set(hideBlockedUsers:Bool)	
userList.set(hideBlockedUsers:true)
```



---

### Set Roles

This method will set the roles for users  in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| `set(roles:[String])` | This method will set the roles for users  in **`UserList` .** | 


```swift
__ syntax for set(roles:[String])
userList.set(roles:["customer"])
```



---

### Set UIDs

This method will set the UIDs for users in **`ConversationList`.**

| Method | Description | 
| ---- | ---- | 
| `set(uids:[String])` | This method will set the UIDs for users in **`UserList` .** | 


```swift
__ syntax for set(uids:[String])
userList.set(uids:["superhero1", "superhero2"])
```



---

### Empty State

This method will specify the option to modify the behaviour when the user list is empty due to any reason.

| Method | Description | 
| ---- | ---- | 
| `set(emptyStateMessage: String)` | This method will add the message to be displayed on the UI when the users are empty | 
| `set(emptyStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when the users are empty | 
| `set(emptyStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when the users are empty | 
| `set(emptyView: UIView?)` | This method will add the custom view passed by the user to on the UI when users are empty | 


```swift
__ syntax for set(emptyStateMessage: String)
userList.set(emptyStateMessage: "No Users")

__ syntax for set(emptyStateTextFont: UIFont)
userList.set(emptyStateTextFont: UIFont(name: "AmericanTypewriter-Regular", size: 30))

__ syntax for set(emptyStateTextColor: UIColor)
userList.set(emptyStateTextColor: UIColor.red)

__ or 

__ syntax for set(emptyView: UIView?)
let emptyView = UIView() __ with custom images_strings etc.
userList.set(emptyView: emptyView)
```



![](https://uploads.developerhub.io/prod/x9W8/mru2uj88d0xpdnc3m2lzbngsizxd9jrmavty80qffz9vrv7mxh7k9klbmzed63t8.png)

---

### Error State

This method will specify the option to modify the behaviour when the user list is empty due to any interruption.

| Method | Description | 
| ---- | ---- | 
| `set(errorMessage: String)` | This method will add the message to be displayed on the UI when user faces any interruption  while fetching users | 
| `hide(errorMessage: Bool)` | This method will hide the error message popup when the interruption happens | 
| `set(errorStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when user faces any interruption  while fetching users | 
| `set(errorStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when user faces any interruption while fetching users | 


```swift
__ syntax for set(errorMessage: String)
userList.set(errorMessage: "Unable to fetch Users at this moment")

__ syntax for set(errorStateTextFont: UIFont)
userList.set(errorStateTextFont: UIFont(name: "AmericanTypewriter-Regular", size: 16))

__ syntax for set(errorStateTextColor: UIColor)
userList.set(errorStateTextColor: UIColor.red)

__ syntax for hide(errorMessage: true)
userList.hide(errorMessage: false)
```



![](https://uploads.developerhub.io/prod/x9W8/o0y9bafgsp0x9cvmjfepno18affjzc131ecx8mbrr2j8xayim6attnu29w3tx4pw.png)

---

### Add User

This method specifies the option to add user object locally in **`UserList`**.

| Method | Description | 
| ---- | ---- | 
| `add(user: User)` | This method specifies the option to add user object locally in **`UserList`**. | 


```swift
__ syntax for add(user: User)
userList.add(user: user)
```



---

### Update User

This method specifies the option to update user object locally in **`UserList`**.

| Method | Description | 
| ---- | ---- | 
| `update(user: User)` | This method specifies the option to update user object locally in **`UserList`**. | 


```swift
__ syntax for update(user: User)
userList.update(user: user) __ Existing 'User' object from the list
```



---

### Remove User

This method specifies the option to remove user object locally from the **`UserList`**.

| Method | Description | 
| ---- | ---- | 
| `remove(user: User)` | This method specifies the option to remove user object locally from the **`UserList`**. | 


```swift
__ syntax for remove(user: User)	
userList.remove(user: user) __ Existing 'User' object from the list
```



---

### Clear List

This method will clear the users locally in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| `clearList()` | This method will clear the users locally in **`UserList` .** | 


```swift
__ syntax for clearList()
userList.clearList()
```



---

### Get Size

This method specifies the count of users displayed in **`UserList`**.

| Method | Description | 
| ---- | ---- | 
| size() | This method specifies the count of users displayed  in **`UserList`**. | 


```swift
__ syntax for size()
userList.size()
```



---

### Set Style

This method will set the styling for **`UserList`.**

| Method | Description | 
| ---- | ---- | 
| set(style: Style) | This method will set the styling for **`UserList`.** | 


```swift
__ syntax for set(style: Style)
let style = Style(background: UIColor.black, border: nil, cornerRadius: nil, titleColor: nil, titleFont: nil, subTitleColor: nil, subTitleFont: nil, loadingIconTint: nil, emptyStateTextFont: UIFont.systemFont(ofSize: 26, weight: .bold), emptyStateTextColor: UIColor.white, errorStateTextFont: UIFont.systemFont(ofSize: 18, weight: .semiBold) , errorStateTextColor: UIColor.white)
        
userList.set(style: style)
```



---

### Set Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


#### InputData

InputData is a class use to configure the CometChatDataItem

| Parameters | Description | 
| ---- | ---- | 
| thumbnail | This is the Boolean value used to control the visibility of the CometChatAvatar . If set to `false`**,** the view will be hidden | 
| status | This is the Boolean value used to control the visibility of the CometChatStatusIndicator . If set to `false`**,** the view will be hidden | 
| title | This is the Boolean value used to control the visibility of the Title . If set to `false`**,** the view will be hidden | 
| subTitle | This is either the String/ function value used to populate the data in the subTitle**.** | 


```swift
__creating object of AvatarConfiguration
let avatarConfiguration = AvatarConfiguration().set(cornerRadius: 10)
__creating object of DataItemConfiguration
var dataItemConfiguration = DataItemConfiguration()

__creating object of InputData to hide_Unhide and display properties in user list
var inputData = InputData(title: true, thumbnail: true, status: true) { user in
                 return user.metadata?["address"] as? String ?? ""
                 }
dataItemConfiguration.set(inputData: inputData)
         
__Passing array of configurations to userlist
userList.set(configurations: [dataItemConfiguration, avatarConfiguration]))
```



> Similarly user can create the object for `AvatarConfiguration` and `StatusIndicatorConfiguration` and pass it to configuration , if he/she wants to configure those component as well.

---