## Overview

`CometChatGroupsWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any group shown in group list.

It has the Same behaviour as [CometChatGroups](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/groups) does.

![](https://uploads.developerhub.io/prod/x9W8/aaqn21nm3deqxejdppw3gtjb4ohwaa1a5cn1lhce728plprjum3qypilh4qohijf.jpg)

---

## Components

`CometChatGroupsWithMessages` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatGroups** | `CometChatGroups `is a independent component used to set up a screen that shows the list of users and gives them the ability to search for a specific user. It's a container component that inherits from `CometChatListBase` and acts as a wrapper for`CometChatUserList` component. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/groups) | 
| 2 | **CometChatMessages** | `CometChatMessages` displays the chat window either for `User` or `Group` entities, and shows the list of messages where the loggedInUser has sent and received from either of the entities. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/messages) | 


---

## Integration

Since `CometChatGroupsWithMessages` is a view controller, it can be added directly  on a button click or any event. `CometChatGroupsWithMessages` inherits all the customizable properties and methods of `CometChatGroups.`

```swift
let cometChatGroupsWithMessages = CometChatGroupsWithMessages()
let naviVC = UINavigationController(rootViewController: cometChatGroupsWithMessages)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

`CometChatGroupsWithMessages` provides the following methods which will allow you to configure CometChatGroupsWithMessages.

### Background

The background is a `UIView` which is present in the backdrop for CometChatGroupsWithMessages. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for CometChatGroupsWithMessages, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatGroupsWithMessages.set(background: [UIColor.systemBackground.cgColor])
```



---

### Title

The title is a `UILabel` which specifies a title for **`CometChatGroupsWithMessages`**. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatGroupsWithMessages`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatGroupsWithMessages`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatGroupsWithMessages`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatGroupsWithMessages`** | 


```swift
__syntax for set(title: String)
cometChatGroupsWithMessages.set(title: "Contacts")

__syntax for set(titleColor: UIColor)
cometChatGroupsWithMessages.set(titleColor: UIColor.black)

__syntax for set(titleFont: UIFont)
cometChatGroupsWithMessages.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .regular))

__syntax for set(largeTitleFont: UIFont)
cometChatGroupsWithMessages.set(largeTitleFont: UIFont.systemFont(ofSize: 34, weight: .bold))
```



---

### Search

The search is a`UISearchController`, which is responsible for displaying and handling events for the search bar in **`CometChatGroupsWithMessages`**. You can modify the search bar using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(searchBackground: UIColor)` | Sets the background color for search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchCornerRadius: CGFloat)` | Sets the corner radius for the search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchPlaceholder: String)` | Set the placeholder for search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchTextColor: UIColor)` | Set the text color  for search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchTextFont: UIFont)` | Set the font for search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchCancelButtonColor: UIColor)` | Set the cancel button color for the search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchBorderWidth: CGFloat)` | Set the border for search bar in **`CometChatGroupsWithMessages`** | 
| `set(searchBorderColor: UIColor)` | Set the border color for the search bar in **`CometChatGroupsWithMessages`** | 
| `hide(search: Bool)` | Hide / unhide the search bar as per boolean value. | 


```swift
__syntax for set(searchBackground: UIColor)
cometChatGroupsWithMessages.set(searchBackground: .systemFill)

__syntax for set(searchCornerRadius: CGFloat)
cometChatGroupsWithMessages.set(searchCornerRadius: "20")

__syntax for set(searchPlaceholder: String)
cometChatGroupsWithMessages.set(searchPlaceholder: "Search Users")

__syntax for set(searchTextColor: UIColor)
cometChatGroupsWithMessages.set(searchTextColor: .black)

__syntax for set(searchTextFont: UIFont)
cometChatGroupsWithMessages.set(searchTextFont: UIFont.systemFont(ofSize: 16, weight: .regular))

__syntax for set(searchCancelButtonColor: UIColor)	
cometChatGroupsWithMessages.set(searchCancelButtonColor: .tintColor)

__syntax for set(searchBorderWidth: CGFloat)
cometChatGroupsWithMessages.set(searchBorderWidth: 1)

__syntax for set(searchBorderColor: UIColor)
cometChatGroupsWithMessages.set(searchBorderColor: .systemFill)

__syntax for hide(search: Bool)
cometChatGroupsWithMessages.hide(search: false)
```



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
cometChatGroupsWithMessages.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatGroupsWithMessages.set(backButtonTint: UIColor.white)

__syntax for set(backButtonIcon: UIImage)
cometChatGroupsWithMessages.set(backButtonIcon: UIImage("back.png"))
```



---

### Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


```swift
__creating object of UsersListConfiguration
let groupListConfiguration = GroupListConfiguration()

var tags:[String] = [String]()   __ Array of tags which user wants to display in list of users

__setting all the configuration value to the object
   groupsListConfiguration.set(searchKeyword: "Searched Text")	
                .hide(error: false)
                .set(joinedOnly: false)
                .set(limit:30)
                .set(tags: tags)
                .set(emptyView: nil)
								.set(errorText: "Something went wrong!")
								.set(emptyText: "empty list")
                    
                    
__creating object of DataItemConfiguration
 var dataItemConfiguration = DataItemConfiguration()

__creating object of InputData to hide_Unhide and display properties in group list
 var inputData = InputData(title: true, thumbnail: true, status: true) { group in
                 return group.metadata?["popularity"] as? String ?? ""
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
cometChatGroupsWithMessages.set(configurations: [groupListConfiguration, dataItemConfiguration, messageListConfiguration, messageComposerConfiguration])
```

