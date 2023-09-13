## Overview

`CometChatUsersWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any user shown in user list.

It has the Same behaviour as [CometChatUsers](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/users) does.

![](https://uploads.developerhub.io/prod/x9W8/30k0fxi9qt90c8rl8c088yr1u8k8gn2wg5qijztf9axvyu8pbm2c74lbuttyk643.jpg)

---

## Components

CometChatUsersWithMessages mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatUsers** | `CometChatUsers`is a independent component used to set up a screen that shows the list of users and gives them the ability to search for a specific user. It's a container component that inherits from `CometChatListBase` and acts as a wrapper for`CometChatUserList` component. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/users) | 
| 2 | **CometChatMessages** | `CometChatMessages` displays the chat window either for `User` or `Group` entities, and shows the list of messages where the loggedInUser has sent and received from either of the entities. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messages) | 


---

## Integration

Since `CometChatUsersWithMessages` is a view controller, it can be added directly  on a button click or any event. `CometChatUsersWithMessages` inherits all the customizable properties and methods of `CometChatUsers.`

```swift
let cometChatUsersWithMessages = CometChatUsersWithMessages()
let naviVC = UINavigationController(rootViewController: cometChatUsersWithMessages)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

`CometChatUsersWithMessages` provides the following methods which will allow you to configure CometChatUsersWithMessages.

### Background

The background is a `UIView` which is present in the backdrop for CometChatUsersWithMessages. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for `CometChatUsersWithMessages`, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatUsersWithMessages.set(background: [UIColor(hex:"FF606D").cgColor])
```



![](https://uploads.developerhub.io/prod/x9W8/q8u3sjhvgfh5x9uy6mred3mm2wogixeqyil5i1ht0l5hog71gy8okwccd0woozd7.jpg)

---

### Title

The title is a `UILabel` which specifies a title for `CometChatUsersWithMessages`. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatUsersWithMessages`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatUsersWithMessages`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatUsersWithMessages`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatUsersWithMessages`** | 


```swift
__syntax for set(title: String)
cometChatUsersWithMessages.set(title: "Contacts")

__syntax for set(titleColor: UIColor)
cometChatUsersWithMessages.set(titleColor: UIColor(hex:"FF606D"))

__syntax for set(titleFont: UIFont)
cometChatUsersWithMessages.set(titleFont:  UIFont(name: "AmericanTypewriter-Bold", size: 22))

__syntax for set(largeTitleFont: UIFont)
cometChatUsersWithMessages.set(largeTitleFont:  UIFont(name: "AmericanTypewriter-Bold", size: 34))
```



![](https://uploads.developerhub.io/prod/x9W8/m1h6f86337lwtuivg1s2iximxw2fi4km8vy6j7emdmt5a7djh8xuwmwp7k9jjt3f.jpg)

---

### Search

The search is a`UISearchController`, which is responsible for displaying and handling events for the search bar in CometChatUsersWithMessages. You can modify the search bar using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(searchBackground: UIColor)` | Sets the background color for search bar in `CometChatUsersWithMessages` | 
| `set(searchCornerRadius: CGFloat)` | Sets the corner radius for the search bar in `CometChatUsersWithMessages` | 
| `set(searchPlaceholder: String)` | Set the placeholder for search bar in `CometChatUsersWithMessages` | 
| `set(searchTextColor: UIColor)` | Set the text color  for search bar in **`CometChatUsersWithMessages`** | 
| `set(searchTextFont: UIFont)` | Set the font for search bar in **`CometChatUsersWithMessages`** | 
| `set(searchCancelButtonColor: UIColor)` | Set the cancel button color for the search bar in **`CometChatUsersWithMessages`** | 
| `set(searchBorderWidth: CGFloat)` | Set the border for search bar in **`CometChatUsersWithMessages`** | 
| `set(searchBorderColor: UIColor)` | Set the border color for the search bar in **`CometChatUsersWithMessages`** | 
| `hide(search: Bool)` | Hide / unhide the search bar as per boolean value. | 


```swift
__syntax for set(searchBackground: UIColor)
cometChatUsersWithMessages.set(searchBackground: UIColor(hex:"FF606D"))

__syntax for set(searchCornerRadius: CGFloat)
cometChatUsersWithMessages.set(searchCornerRadius: "20")

__syntax for set(searchPlaceholder: String)
cometChatUsersWithMessages.set(searchPlaceholder: "Search Users")

__syntax for set(searchTextColor: UIColor)
cometChatUsersWithMessages.set(searchTextColor: .white)

__syntax for set(searchTextFont: UIFont)
cometChatUsersWithMessages.set(searchTextFont: UIFont(name: "AmericanTypewriter-Regular", size: 16)))

__syntax for set(searchCancelButtonColor: UIColor)	
cometChatUsersWithMessages.set(searchCancelButtonColor: .tintColor)

__syntax for set(searchBorderWidth: CGFloat)
cometChatUsersWithMessages.set(searchBorderWidth: 1)

__syntax for set(searchBorderColor: UIColor)
cometChatUsersWithMessages.set(searchBorderColor: .systemFill)

__syntax for hide(search: Bool)
cometChatUsersWithMessages.hide(search: false)
```



![](https://uploads.developerhub.io/prod/x9W8/sg0jaajbi3h6jrgx5j0bbuy1opvhys144yhvhd3hkxilcgokdom5sxycmlp9mfa4.jpg)

---

### Back

The back button is a `UIButton` which the user can show if he wishes to. This button can be modified using the below methods, User can add event for backbutton using delegate function `onBack()`

| Method | Description | 
| ---- | ---- | 
| `show(backButton: Bool)` | Hides / shows the back button as per the boolean value | 
| `set(backButtonTint: UIColor)` | Sets the tint color for the back button | 
| `set(backButtonIcon: UIImage)` | Sets the icon for the back button | 


```swift
__syntax for show(backButton: Bool)
cometChatUsersWithMessages.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatUsersWithMessages.set(backButtonTint: UIColor(hex:"FF606D"))

__syntax for set(backButtonIcon: UIImage)
cometChatUsersWithMessages.set(backButtonIcon: UIImage("back.png"))
```



![](https://uploads.developerhub.io/prod/x9W8/g4xxolqysw7rjqezl6m6emykndrmr24otvmdu0r4axgpg4o2yfyahq8ghuqgwsuw.jpg)

### Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


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
                    
                    
__creating object of DataItemConfiguration
 var dataItemConfiguration = DataItemConfiguration()

__creating object of InputData to hide_Unhide and display properties in user list
 var inputData = InputData(title: true, thumbnail: true, status: true) { user in
                 return user.metadata?["address"] as? String ?? ""
                 }
 dataItemConfiguration.set(inputData: inputData)

__ Creating object of messageTemplates which you need to add support in Messages
 let text = CometChatMessageTemplate(type: .text)
 let image = CometChatMessageTemplate(type: .imageFromGallery)
 let file = CometChatMessageTemplate(type: .file)
 

__creating object of MessageListConfiguration
let messageListConfiguration = MessageListConfiguration()
messageListConfiguration.set(messageTypes: [ text, image, file])

__creating object of MessageComposerConfiguration
let messageComposerConfiguration = MessageComposerConfiguration()
messageComposerConfiguration.set(messageTypes: [ text, image, file])

                   
__Passing array of configurations to users with messages
cometChatUsersWithMessages.set(configurations: [userListConfiguration, dataItemConfiguration, messageListConfiguration, messageComposerConfiguration])
```

