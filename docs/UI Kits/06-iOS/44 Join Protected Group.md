## Overview

`CometChatJoinProtectedGroup` a independent component used to set up a screen that shows the functionality to join a password protected group. It's a container component that inherits from `CometChatListBase`  so it inherits all the properties and methods from the `CometChatListBase` class.

`CometChatJoinProtectedGroup` sets up the following functionality internally:

- User will be able to join single password protected group at a time.
- It includes all the business logic and options to customize the UI according to our default design system.

![](https://uploads.developerhub.io/prod/x9W8/llk1rnulr2g8iblxji9z7wk0mn0izydok7eiy303v3qs95a4t35lt53kbtv5qmf1.png)

---

## Components

`CometChatCreateGroup` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatListBase** | `CometChatListBase` is a container component having title (`navigationBar`), search (`search-bar`), `background`, and a container to embed a list view | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/list-base) | 


---

## Integration

Since `CometChatJoinProtectedGroup` is a custom view controller , it can be added directly launched via button click or any action performed by the user. It can also be embedded in the tab view controller.  `CometChatJoinProtectedGroup` includes various parameters and methods to customize its UI.

```swift
let cometChatJoinProtectedGroup = CometChatJoinProtectedGroup()
let naviVC = UINavigationController(rootViewController: cometChatJoinProtectedGroup)
self.present(naviVC, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

`CometChatJoinProtectedGroup` provides the following methods which will allow you to configure **`CometChatJoinProtectedGroup`**.

### Group

`CometChatJoinProtectedGroup` takes SDK's `Group` object and manipulates the other components in **`CometChatJoinProtectedGroup` .** This `Group` object is used to join the group for which the compoent is getting presented.

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | `CometChatJoinProtectedGroup` takes SDK's `Group` object and manipulates the other components in **`CometChatJoinProtectedGroup` .** This `Group` object is used to join the group for which the compoent is getting presented. | 


```swift
__syntax for set(group: Group)
cometChatJoinProtectedGroup.set(group: Group)
```



---

### Background

The background is a `UIView` which is present in the backdrop for **`CometChatJoinProtectedGroup`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for **`CometChatJoinProtectedGroup`**, it can take an array of multiple colors for the gradient background. | 


```swift
__syntax for set(background: [UIColor])
cometChatJoinProtectedGroup.set(background: [UIColor.systemBackground.cgColor])
```



---

### Title

The title is a `UILabel` which specifies a title for **`CometChatJoinProtectedGroup`**. You will be able to modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`CometChatJoinProtectedGroup`** | 
| `set(titleColor: UIColor)` | Sets the title color for **`CometChatJoinProtectedGroup`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`CometChatJoinProtectedGroup`** | 
| `set(largeTitleFont: UIFont)` | Sets the title font for **`CometChatJoinProtectedGroup`** | 


```swift
__syntax for set(title: String)
cometChatJoinProtectedGroup.set(title: "Join Group")

__syntax for set(titleColor: UIColor)
cometChatJoinProtectedGroup.set(titleColor: UIColor.black)

__syntax for set(titleFont: UIFont)
cometChatJoinProtectedGroup.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .regular))

__syntax for set(largeTitleFont: UIFont)
cometChatJoinProtectedGroup.set(largeTitleFont: UIFont.systemFont(ofSize: 34, weight: .bold))
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
cometChatJoinProtectedGroup.show(backButton: Bool)

__syntax for set(backButtonTint: UIColor)
cometChatJoinProtectedGroup.set(backButtonTint: UIColor.white)

__syntax for set(backButtonIcon: UIImage)
cometChatJoinProtectedGroup.set(backButtonIcon: UIImage("back.png"))
```



---

### Continue

The continue button is a `UIButton` which is used to join a group. This button can be modified using the below methods.

| Method | Description | 
| ---- | ---- | 
| `hide(continueButton: Bool)\n\n` | Hides / shows the continue button as per the boolean value | 
| `set(continueButtonTint: UIColor)` | Sets the tint color for the continue button | 


```swift
__syntax for hide(continueButton: Bool)
cometChatJoinProtectedGroup.hide(continueButton: false)

__syntax for set(continueButtonTint: UIColor)
cometChatJoinProtectedGroup.set(continueButtonTint: UIColor.white)
```



---

### Caption

The caption is a `UILabel` which is used to show the information about the group below the password textfield. This can be modified using the below methods.

| Method | Description | 
| ---- | ---- | 
| `set(caption: String)` | This sets the caption for the group in **`CometChatJoinProtectedGroup`** | 
| `set(captionFont: UIFont)` | This sets the caption font for the group in **`CometChatJoinProtectedGroup`** | 
| `set(captionColor: UIColor) ` | This sets the caption  color for the group in **`CometChatJoinProtectedGroup`** | 


```swift
__syntax for show(backButton: Bool)
cometChatJoinProtectedGroup.set(caption: "Your text here")

__syntax for set(captionFont: UIFont)
cometChatJoinProtectedGroup.set(captionFont: UIFont.systemFont(ofSize: 20)
                                
__syntax for set(captionColor: UIColor)
cometChatJoinProtectedGroup.set(captionColor: UIColor.white)
```

