## Overview

`CometChatCreateGroup` a independent component used to set up a screen that shows the functionality to create a specific type of group. It's a container component that inherits from `CometChatListBase`  so it inherits all the properties and methods from the `CometChatListBase` class.

`CometChatCreateGroup` sets up the following functionality internally:

- User will be able to create single group at a time.
- User can create multiple types of groups such as:  

1. **Public Group**
2. **Private Group**
3. **Password Protected Group**

- It includes all the business logic and options to customize the UI according to our default design system.

![](https://uploads.developerhub.io/prod/x9W8/l7giy20eq3fh0m4315wbrykgtd36ra4rax87wjvdmwjczfndjkryoxd8hr33scr7.png)

---

## Components

`CometChatCreateGroup` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatListBase** | `CometChatListBase` is a container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed a list view | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/list-base) | 


---

## Integration

Since `CometChatCreateGroup` is a custom view controller , it can be added directly launched via button click or any action performed by the user. It can also be embedded in the tab view controller.  `CometChatCreateGroup` includes various parameters and methods to customize its UI.

```swift
let cometChatCreateGroup = CometChatCreateGroup()
let naviVC = UINavigationController(rootViewController: cometChatCreateGroup)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

`CometChatCreateGroup` provides the following methods which will allow you to configure **`CometChatCreateGroup`**.

### Background

The background is a `UIView` which is present in the backdrop for **`CometChatCreateGroup`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for **`CometChatCreateGroup`**, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatCreateGroup.set(background: [UIColor.systemBackground.cgColor])
```



---

### Title

The title is a `UILabel` which specifies a title for **`CometChatCreateGroup`**. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatCreateGroup`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatCreateGroup`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatCreateGroup`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatCreateGroup`** | 


```swift
__syntax for set(title: String)
cometChatCreateGroup.set(title: "Contacts")

__syntax for set(titleColor: UIColor)
cometChatCreateGroup.set(titleColor: UIColor.black)

__syntax for set(titleFont: UIFont)
cometChatCreateGroup.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .regular))

__syntax for set(largeTitleFont: UIFont)
cometChatCreateGroup.set(largeTitleFont: UIFont.systemFont(ofSize: 34, weight: .bold))
```



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
cometChatCreateGroup.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatCreateGroup.set(backButtonTint: UIColor.white)

__syntax for set(backButtonIcon: UIImage)
cometChatCreateGroup.set(backButtonIcon: UIImage("back.png"))
```



---

### Create

The create button is a `UIButton` which is used to create a group. This button can be modified using the below methods.

| Method | Description | 
| ---- | ---- | 
| `hide(create: Bool)` | Hides / shows the back button as per the boolean value | 
| `set(createButtonTint: UIColor)` | Sets the tint color for the create button | 


```swift
__syntax for show(backButton: Bool)
cometChatCreateGroup.hide(create: false)

__syntax for set(backButtonTint: UIColor)
cometChatCreateGroup.set(createButtonTint: UIColor.white)
```



---