## Overview

`CometChatGroups`is a independent component used to set up a screen that shows the list of groups and gives them the ability to search for a specific group. `CometChatGroups` is a container component that wraps and formats the `CometChatListBase` and `CometChatGroupList` component with no behaviour of its own.

`CometChatGroups` sets up the following functionality internally:

- List of groups in alphabetical manner with pagination.
- Search input that can be shown or hidden and allows users to search for specific groups by name, guid (for groups).
- customizable header title 

It includes all the business logic and options to customize the UI according to our default design system.

![](https://uploads.developerhub.io/prod/x9W8/4f15bley71xqfw7g876dcorsmo90ouw3x89o4iehirn9mj7lxvzwfl3eepzsj5n2.png)

---

## Components

`CometChatGroups` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatListBase** | `CometChatListBase` is a container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed a list view | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/list-base) | 
| 2 | **CometChatGroupList** | This component retrieves the list of groups. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/group-list) | 


![](https://uploads.developerhub.io/prod/x9W8/ybd99o26koso3f46tfvwjbat86qoe7m543c93c9jcyto3b1mqgukzeqnrluf0i90.jpg)

---

## Integration

Since `CometChatGroups` is a custom view controller , it can be added directly launched via button click or any action performed by the user. It can also be embedded in the tab view controller. `CometChatGroups` includes various parameters and methods to customize its UI.

```swift
let groups = CometChatGroups()
let naviVC = UINavigationController(rootViewController: groups)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller

---

## Methods

`CometChatGroups` provides the following methods which will allow you to configure **`CometChatGroups`**.

### Background

The background is a `UIView` which is present in the backdrop for **`CometChatGroups`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for **`CometChatGroups`**, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatGroups.set(background: [UIColor.systemBackground.cgColor])
```



---

### Title

The title is a `UILabel` which specifies a title for **`CometChatGroups`**. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatGroups`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatGroups`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatGroups`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatGroups`** | 


```swift
__syntax for set(title: String)
cometChatGroups.set(title: "Contacts")

__syntax for set(titleColor: UIColor)
cometChatGroups.set(titleColor: UIColor.black)

__syntax for set(titleFont: UIFont)
cometChatGroups.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .regular))

__syntax for set(largeTitleFont: UIFont)
cometChatGroups.set(largeTitleFont: UIFont.systemFont(ofSize: 34, weight: .bold))
```



---

### Search

The search is a`UISearchController`, which is responsible for displaying and handling events for the search bar in **`CometChatGroups`**. You can modify the search bar using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(searchBackground: UIColor)` | Sets the background color for search bar in **`CometChatGroups`** | 
| `set(searchCornerRadius: CGFloat)` | Sets the corner radius for the search bar in **`CometChatGroups`** | 
| `set(searchPlaceholder: String)` | Set the placeholder for search bar in **`CometChatGroups`** | 
| `set(searchTextColor: UIColor)` | Set the text color  for search bar in **`CometChatGroups`** | 
| `set(searchTextFont: UIFont)` | Set the font for search bar in **`CometChatGroups`** | 
| `set(searchCancelButtonColor: UIColor)` | Set the cancel button color for the search bar in **`CometChatGroups`** | 
| `set(searchBorderWidth: CGFloat)` | Set the border for search bar in **`CometChatGroups`** | 
| `set(searchBorderColor: UIColor)` | Set the border color for the search bar in **`CometChatGroups`** | 
| `hide(search: Bool)` | Hide / unhide the search bar as per boolean value. | 


```swift
__syntax for set(searchBackground: UIColor)
cometChatGroups.set(searchBackground: .systemFill)

__syntax for set(searchCornerRadius: CGFloat)
cometChatGroups.set(searchCornerRadius: "20")

__syntax for set(searchPlaceholder: String)
cometChatGroups.set(searchPlaceholder: "Search Groups")

__syntax for set(searchTextColor: UIColor)
cometChatGroups.set(searchTextColor: .black)

__syntax for set(searchTextFont: UIFont)
cometChatGroups.set(searchTextFont: UIFont.systemFont(ofSize: 16, weight: .regular))

__syntax for set(searchCancelButtonColor: UIColor)	
cometChatGroups.set(searchCancelButtonColor: .tintColor)

__syntax for set(searchBorderWidth: CGFloat)
cometChatGroups.set(searchBorderWidth: 1)

__syntax for set(searchBorderColor: UIColor)
cometChatGroups.set(searchBorderColor: .systemFill)

__syntax for hide(search: Bool)
cometChatGroups.hide(search: false)
```



---

### Back

The back button is a `UIButton` which the user can show if he wishes to. This button can be modified using the below methods, User can add event for backbutton using delegate funtion `onBack()`

```swift
__syntax for show(backButton: Bool)
cometChatGroups.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatGroups.set(backButtonTint: UIColor.white)

__syntax for set(backButtonIcon: UIImage)
cometChatGroups.set(backButtonIcon: UIImage("back.png"))
```



| Method | Description | 
| ---- | ---- | 
| `show(backButton: Bool)` | Hides / shows the back button as per the boolean value | 
| `set(backButtonTint: UIColor)` | Sets the tint color for the back button | 
| `set(backButtonIcon: UIImage)` | Sets the icon for the back button | 


---

### Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


```swift
__creating object of GroupListConfiguration
var groupListConfiguration = GroupListConfiguration()
                    
var tags:[String] = [String]()   __ Array of tags which user wants to display in list of users

__setting all the configuration value to the object
     groupListConfiguration.set(searchKeyword: "Searched Text")
                        .set(limit: 30)
                        .set(tags: tags)
                        .set(joinedOnly: true)
                        .hide(createGroup: false)
                        .set(emptyView: nil)
                        .hide(error: false)
                        .set(errorText: "Something went wrong!")
                        .set(emptyText: "Empty List")
                    
                    
__creating object of DataItemConfiguration
 var dataItemConfiguration = DataItemConfiguration()

__creating object of InputData to hide_Unhide and display properties in user list
 var inputData = InputData(title: true, thumbnail: true, status: true) { group in
                 return (group as? Group)?.description as? String ?? ""
                 }
 dataItemConfiguration.set(inputData: inputData)
                   
__Passing array of configurations to groups
cometChatGroups.set(configurations: [groupListConfiguration, dataItemConfiguration])
```



> User can pass multiple configurations for the components underneath of **`CometChatGroups`**or the components which are launching from the events triggered from **`CometChatGroups`**

## Events

To handle events supported by `CometChatGroups` user must have to add corresponding listeners in the parent `View controller` or `Class`:

| Event | Description | 
| ---- | ---- | 
| `onItemClick(group: Group, index: IndexPath?)` | Triggered whenever a user clicks on a particular group. | 
| `onItemLongClick(group: Group, index: IndexPath?)` | Triggered whenever a user  long presses on a particular group. | 
| `onGroupMemberAdd(group: Group, members: [GroupMember])` | Triggered whenever a group member is added | 
| `onCreateGroupClick()` | When the user creates a group | 
| `onGroupCreate(group: Group)` | When the user deletes the group | 
| `onGroupDelete(group: Group)` | Triggered whenever a group is deleted by logged-in user | 
| `onGroupMemberLeave(leftUser: User, leftGroup:  Group)` | Triggered whenever a logged-in user leaves a group | 
| `onGroupMemberJoin(joinedUser: User, joinedGroup:  Group)` | Triggered whenever any user joins the group | 
| `onGroupMemberBan(bannedUser: User, bannedGroup:  Group)` | Triggered whenever any group member is banned | 
| `onGroupMemberUnban(unbannedUserUser: User, unbannedUserGroup:  Group)` | Triggered whenever a group member is unbanned from group | 
| `onGroupMemberKick(kickedUser: User, kickedGroup:  Group)` | Triggered whenever a group member is kicked from group | 
| `onGroupMemberChangeScope(updatedBy: User , updatedUser: User , scopeChangedTo: CometChat.MemberScope , scopeChangedFrom: CometChat.MemberScope, group: Group)` | Triggered whenever a scope of any group member is changed. | 
| onOwnershipChange(group: Group, member: GroupMember) | Triggered whenever an owner of the group is changed. | 
| `onError(group: Group?, error: CometChatException)` | Triggered whenever a CometChatGroups is unable to load a list and throws an error | 


```swift
__ View controller from your project where you want to listen events.
public class ViewController: UIViewController {
    
   public override func viewDidLoad() {
        super.viewDidLoad()
     
       __ Subscribing for the listener to listen events from user module
         CometChatGroupEvents.addListener("UNIQUE_ID", self as CometChatGroupEventListner)
    }
  
    public override func viewWillDisappear(_ animated: Bool) {
       __ Uncubscribing for the listener to listen events from user module
        CometChatGroupEvents.removeListner("UNIQUE_ID")
    }
  
  
}

 __ Listener events from groups module
extension  ViewController: CometChatGroupEventListner {
  
    public func onItemClick(group: Group, index: IndexPath?) {
       __ Do Stuff
    }
  
    public func onItemLongClick(group: Group, index: IndexPath?) {
        __ Do Stuff
    }
    
    public func onGroupMemberAdd(group: Group, members: [GroupMember]) {
        __ Do Stuff
    }
    
    public func onCreateGroupClick() {
         __ Do Stuff
    }
    
    public func onGroupCreate(group: Group) {
        __ Do Stuff
    }
  
    public func onGroupDelete(group: Group) {
        __ Do Stuff
    }
    
    public func onGroupMemberJoin(joinedUser: User, joinedGroup: Group) {
        __ Do Stuff
    }
    
    public func onGroupMemberLeave(leftUser: User, leftGroup: Group) {
        __ Do Stuff
    }
    
    public func onGroupMemberBan(bannedUser: User, bannedGroup: Group) {
         __ Do Stuff
    }
    
    public func onGroupMemberUnban(unbannedUserUser: User, unbannedUserGroup: Group) {
         __ Do Stuff
    }
    
    public func onGroupMemberKick(kickedUser: User, kickedGroup: Group) {
         __ Do Stuff
    }
    
    public func onGroupMemberChangeScope(updatedBy: User, updatedUser: User, scopeChangedTo: CometChat.MemberScope, scopeChangedFrom: CometChat.MemberScope, group: Group) {
          __ Do Stuff
    }
  
    public func onOwnershipChange(group: Group?, member: GroupMember?) {
        __ Do Stuff
    }
    
    public func onError(group: Group?, error: CometChatException) {
          __ Do Stuff
    }
    
}
```

