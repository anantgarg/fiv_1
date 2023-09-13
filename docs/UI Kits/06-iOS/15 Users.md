## Overview

`CometChatUsers`is a independent component used to set up a screen that shows the list of users and gives them the ability to search for a specific user. It's a container component that inherits from `CometChatListBase` and acts as a wrapper for`CometChatUserList` component. It inherits all the properties and methods from the `CometChatListBase` class.

`CometChatUsers` sets up the following functionality internally:

- List of users in alphabetical manner with pagination.
- Search input allows end-users to search for specific user by name, UID (for users). It can be customised to either be shown or hidden in the UI. 
- Header with customizable title.

It includes all the business logic and options to customize the UI according to our default design system.

![](https://uploads.developerhub.io/prod/x9W8/76rdz8swh0btkv93je2ue7s4ktkqi4g78uc7mxkn65o8ql64mzx0pwlyvg80oksa.png)

---

## Components

CometChatUsers mainly contains below components in it. 

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatListBase** | `CometChatListBase` is a container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed a list view | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/list-base) | 
| 2 | **CometChatUserList** | This component retrieves the list of users. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/user-list) | 


![](https://uploads.developerhub.io/prod/x9W8/xkvup2luo65yl8w0jex1nntpn488kqqvmf9sfbvak9fnpy2icfcmqzjzwqg2g6qr.jpg)

---

## Integration

Since `CometChatUsers` is a custom view controller , it can be added directly launched via button click or any action performed by the user. It can also be embedded in the tab view controller.  `CometChatUsers` includes various parameters and methods to customize its UI.

```swift
let cometChatUsers = CometChatUsers()
let naviVC = UINavigationController(rootViewController: cometChatUsers)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

`CometChatUsers` provides the following methods which will allow you to configure `CometChatUsers`.

### Background

The background is a `UIView` which is present in the backdrop for **`CometChatUsers`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for **`CometChatUsers`**, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatUsers.set(background: [UIColor(hex:"FF606D").cgColor])
```



![](https://uploads.developerhub.io/prod/x9W8/m96u8u7brz22g8pyjticfke7gu87441unllvwkuh2be8aq7rexn7rx9xk9eyhrf4.jpg)

---

### Title

The title is a `UILabel` which specifies a title for **`CometChatUsers`**. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatUsers`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatUsers`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatUsers`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatUsers`** | 


```swift
__syntax for set(title: String)
cometChatUsers.set(title: "Contacts")

__syntax for set(titleColor: UIColor)
cometChatUsers.set(titleColor: UIColor(hex:"FF606D"))

__syntax for set(titleFont: UIFont)
cometChatUsers.set(titleFont:  UIFont(name: "AmericanTypewriter-Bold", size: 22))

__syntax for set(largeTitleFont: UIFont)
cometChatUsers.set(largeTitleFont:  UIFont(name: "AmericanTypewriter-Bold", size: 34))
```



![](https://uploads.developerhub.io/prod/x9W8/xttcv488zqz1u5s8g9o8cf67fwghnfmw1pvnhzogdf2ecxhmqlol15dhcyyebkf6.jpg)

---

### Search

The search is a`UISearchController`, which is responsible for displaying and handling events for the search bar in **`CometChatUsers`**. You can modify the search bar using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(searchBackground: UIColor)` | Sets the background color for search bar in **`CometChatUsers`** | 
| `set(searchCornerRadius: CGFloat)` | Sets the corner radius for the search bar in **`CometChatUsers`** | 
| `set(searchPlaceholder: String)` | Set the placeholder for search bar in **`CometChatUsers`** | 
| `set(searchTextColor: UIColor)` | Set the text color  for search bar in **`CometChatUsers`** | 
| `set(searchTextFont: UIFont)` | Set the font for search bar in **`CometChatUsers`** | 
| `set(searchCancelButtonColor: UIColor)` | Set the cancel button color for the search bar in **`CometChatUsers`** | 
| `set(searchBorderWidth: CGFloat)` | Set the border for search bar in **`CometChatUsers`** | 
| `set(searchBorderColor: UIColor)` | Set the border color for the search bar in **`CometChatUsers`** | 
| `hide(search: Bool)` | Hide / unhide the search bar as per boolean value. | 


```swift
__syntax for set(searchBackground: UIColor)
cometChatUsers.set(searchBackground: UIColor(hex:"FF606D"))

__syntax for set(searchCornerRadius: CGFloat)
cometChatUsers.set(searchCornerRadius: "20")

__syntax for set(searchPlaceholder: String)
cometChatUsers.set(searchPlaceholder: "Search Users")

__syntax for set(searchTextColor: UIColor)
cometChatUsers.set(searchTextColor: .white)

__syntax for set(searchTextFont: UIFont)
cometChatUsers.set(searchTextFont: UIFont(name: "AmericanTypewriter-Regular", size: 16))

__syntax for set(searchCancelButtonColor: UIColor)	
cometChatUsers.set(searchCancelButtonColor: .tintColor)

__syntax for set(searchBorderWidth: CGFloat)
cometChatUsers.set(searchBorderWidth: 1)

__syntax for set(searchBorderColor: UIColor)
cometChatUsers.set(searchBorderColor: .systemFill)

__syntax for hide(search: Bool)
cometChatUsers.hide(search: false)
```



![](https://uploads.developerhub.io/prod/x9W8/ic9dg7bn4e0jdzzp1ep9qtnopvz2afp4m34m3qo5wiu11l1lerc56yjgev2foc7i.jpg)

---

### Back

The back button is a `UIButton` which the user can show if he wishes to. This button can be modified using the below methods, User can add event for backbutton using delegate funtion `onBack()`

| Method | Description | 
| ---- | ---- | 
| `show(backButton: Bool)` | Hides / shows the back button as per the boolean value | 
| `set(backButtonTint: UIColor)` | Sets the tint color for the back button | 
| `set(backButtonIcon: UIImage)` | Sets the icon for the back button | 


```swift
__syntax for show(backButton: Bool)
cometChatUsers.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatUsers.set(backButtonTint: UIColor(hex:"FF606D"))

__syntax for set(backButtonIcon: UIImage)
cometChatUsers.set(backButtonIcon: UIImage("back.png"))
```



![](https://uploads.developerhub.io/prod/x9W8/3tfn0yto3g2j4h490va5hvwzce1cgkukx0kv8i3v7iu93465coz61p4tz5sqq40e.jpg)

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
                 return (user as? User)?.metadata?["address"] as? String ?? ""
                 }
 dataItemConfiguration.set(inputData: inputData)
                   
__Passing array of configurations to users
cometChatUsers.set(configurations: [userListConfiguration, dataItemConfiguration])
```



> User can pass multiple configurations for the components underneath of **`CometChatUsers`  or the components which are launching from the events triggered from `CometChatUsers`**

---

## Events

To handle events supported by `CometChatUsers` user must have to add corresponding listeners in the parent `View controller` or `Class`:

| Event | Description | 
| ---- | ---- | 
| `onItemClick(user: User, index: IndexPath?)` | Triggers whenever a user clicks on a particular user. | 
| `onItemLongClick(user: User, index: IndexPath?)` | Triggers whenever a user long presses on a particular user. | 
| `onUserBlock(user: User)` | Triggers whenever loggedIn user blocks another user | 
| `onUserUnblock(user: User)` | Triggers whenever loggedIn user unblocks another user | 
| `onError(user: User?, error: CometChatException)` | Triggers whenever error occurs while performing any actions | 


```swift
__ View controller from your project where you want to listen events.
public class ViewController: UIViewController {
    
   public override func viewDidLoad() {
        super.viewDidLoad()
     
       __ Subscribing for the listener to listen events from user module
         CometChatUserEvents.addListener("UNIQUE_ID", self as CometChatUserEventListener)
    }
  
    public override func viewWillDisappear(_ animated: Bool) {
       __ Uncubscribing for the listener to listen events from user module
        CometChatUserEvents.removeListner("UNIQUE_ID")
    }
  
  
}

 __ Listener events from user module
extension  ViewController: CometChatUserEventListener {
  
     func onItemClick(user: User, index: IndexPath?) {
        __ Do Stuff
    }
    
    func onItemLongClick(user: User, index: IndexPath?) {
        __ Do Stuff
    }
    
    func onUserBlock(user: User) {
        __ Do Stuff
    }
    
    func onUserUnblock(user: User) {
        __ Do Stuff
    }
    
    func onError(user: User?, error: CometChatException) {
        __ Do Stuff
    }
    
}
```



---