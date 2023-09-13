## Overview

`CometChatMessageHeader` displays the `User` or `Group` information using iOS SDK's `User` or `Group object.` It also shows the typing indicator when the user starts typing in `MessageComposer`.

![](https://res.cloudinary.com/developerhub/image/upload/v1644931305/v2_5163/mneroceltmqp0uahjjp4.png)

---

## Components

`CometChatMessageHeader` mainly contains below components: 

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | Avatar | The `CometChatAvatar` component displays user and group avatars. For users and groups , it displays either an image or the user's avatar and falls back to the first two letters of the username. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/avatar) | 
| 2 | Status Indicator | This component is of the class `UImageView`. It's customisable to display the status of the user's presence as online, offline using colour codes or can be used to display type of a group as password protected, public or private using a custom image. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/avatar-indicator) | 
| 3 | Title | The title is a `UILabel` which specifies a title for CometChatMessageHeader. |  | 
| 4 | Subtitle | The subtitle is a `UILabel` which specifies a title for CometChatMessageHeader. |  | 
| 5 | Background | The background is a UIView which is present in the backdrop for CometChatMessageHeader. |  | 
| 6 | Video Call | Using this button user will be able to perform video call with users or group |  | 
| 7 | Audio Call | Using this button user will be able to perform voice call with users or group |  | 
| 8 | Info | Using this button user will be able to open detailed page for users or groups |  | 


## Methods

### User

`CometChatMessageHeader` takes SDK's `User` object and manipulates the other components in `CometChatMessageHeader`**.**

| Method | Description | 
| ---- | ---- | 
| `set(user: User)` | Sets the User object used in the CometChatMessageHeader for all sub-components. | 


```swift
__ syntax for set(user: User)	
messageHeader.set(user: user)	 __ The object which is going to be rendered in the data  item
```



---

### Group

`CometChatMessageHeader` takes SDK's Group object and manipulates the other components in `CometChatMessageHeader`**.**

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | Sets the Group object used in the `CometChatMessageHeader` for all sub-components. | 


```swift
__ syntax for set(group: Group)	
messageHeader.set(group: group)	__ The object which is going to be rendered in the data item
```



---

### Background

The background is a UIView which is present in the backdrop for CometChatMessageHeader. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for CometChatMessageHeader | 


```swift
__ syntax for set(background: [UIColor])
messageHeader.set(background: [UIColor.black])
```



---

### Controller

This method will set the instance of the view controller from which the CometChatMessageHeader is presented.

| Method | Description | 
| ---- | ---- | 
| `set(controller: UIViewController)` | This method will set the instance of the view controller from which the CometChatMessageHeader is presented. | 


```swift
__ syntax for set(controller: UIViewController)
messageHeader.set(controller: self)
```



> To present the another view controller/popup or presentation controller from user list, user must have to call this method which will take the instance of the view controller to launch respective view.

---

### Title

The title is a `UILabel` which specifies a title for CometChatMessageHeader. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for CometChatMessageHeader. | 
| `set(titleWithAttributedText: NSAttributedString)` | Sets the title with attributed text for CometChatMessageHeader. | 
| `set(titleColor: UIColor)` | Sets the title color for CometChatMessageHeader | 
| `set(titleFont: UIFont)` | Sets the title font for CometChatMessageHeader | 
| `hide(title: Bool)` | hide/shows the title for CometChatMessageHeader | 


```swift
__ syntax for set(title: String)
messageHeader.set(title: user.name)

__ syntax for set(titleColor: UIColor)
messageHeader.set(titleColor: UIColor.white)

__ syntax for set(titleFont: UIFont)
messageHeader.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .medium))

__ syntax for hide(title: Bool)
messageHeader.hide(title: false)
```



---

### Subtitle

The title is a `UILabel` which specifies a subTitle for CometChatMessageHeader. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(subTitle: String?)` | Sets the subTitle for CometChatMessageHeader. | 
| `set(subTitleWithAttributedText: NSAttributedString)` | Sets the subTitle with attributed text for CometChatMessageHeader. | 
| `set(subTitleColor: UIColor)` | Sets the subTitle color for CometChatMessageHeader | 
| `set(subTitleFont: UIFont)` | Sets the subTitle font for CometChatMessageHeader | 
| `hide(subTitle: Bool)` | hide/shows the subTitle for CometChatMessageHeader | 


```swift
__ syntax for set(subTitle: String?)
messageHeader.set(subTitle: String(user.lastActiveAt))

__ syntax for set(subTitleColor: UIColor)
messageHeader.set(subTitleColor: UIColor.white)

__ syntax for set(subTitleFont: UIFont)
messageHeader.set(subTitleFont: UIFont.systemFont(ofSize: 16, weight: .regular))

__ syntax for hide(subTitle: Bool)
messageHeader.hide(subTitle: false)
```



---

### Avatar

The avatar is a `UIImageView` that specifies an avatar for CometChatMessageHeader. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(avatar: CometChatAvatar)` | Sets the avatar for CometChatMessageHeader. | 
| `hide(avatar: Bool)` | Hides the avatar for CometChatMessageHeader. | 


```swift
__ syntax for set(avatar: CometChatAvatar)
let avatar = CometChatAvatar().set(cornerRadius: 20)
messageHeader.set(avatar: avatar)

__ syntax for hide(avatar: Bool)
messageHeader.hide(avatar: false)
```



---

### StatusIndicator

The status indicator is a `CometChatStatusIndicator` that specifies a user status for a user for CometChatMessageHeader. You can modify the title using the below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(statusIndicator: CometChatPro.CometChat.UserStatus)` | Sets the status indicator for CometChatMessageHeader | 
| `hide(statusIndicator: Bool)` | hide/show the status indicator for CometChatMessageHeader | 


```swift
__ syntax for set(statusIndicator: CometChatPro.CometChat.UserStatus)
messageHeader.set(statusIndicator: .online)

__ syntax for hide(statusIndicator: Bool)
messageHeader.hide(statusIndicator: false)
```



---

### Back

Back button is UIButton which is used to dismiss or pop the view controller from which the CometChatMessageHeader is getting presented. You can modify the back button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(backButtonIcon: UIImage)` | Sets the icon for the back button in  `CometChatMessageHeader` | 
| `set(backButtonIconTint: UIColor)` | Sets the tint color for the back button in  `CometChatMessageHeader` | 
| `hide(backButton: Bool)` | Hides the back button in `CometChatMessageHeader` | 


```swift
__ syntax for set(backButtonIcon: UIImage) 
messageHeader.set(backButtonIcon: UIImage(named: "back.png") 

__ syntax for set(backButtonIconTint: UIColor)
messageHeader.set(backButtonIconTint: .white)

__ syntax for hide(backButton: Bool)
messageHeader.hide(backButton: false)
```



---

### Audio Call

Audio call button is the UIButton which triggers audio call from CometChatMessageHeader. You can modify the properties of   button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(audioCallIcon: UIImage)` | Sets the icon for the audio button in  `CometChatMessageHeader` | 
| `set(audioCallIconTint: UIColor)` | Sets the tint color for the audio call button in `CometChatMessageHeader` | 
| `hide(voiceCallButton: Bool)` | Hides the audio call button in `CometChatMessageHeader` | 


```swift
__ syntax for set(audioCallIcon: UIImage) 
messageHeader.set(audioCallIcon: UIImage(named: "audio-call.png") 

__ syntax for set(audioCallIconTint: UIColor)
messageHeader.set(audioCallIconTint: .white)

__ syntax for hide(voiceCallButton: Bool)
messageHeader.hide(voiceCallButton: true)
```



---

### Video Call

Video call button is the UIButton which triggers video call from CometChatMessageHeader. You can modify the properties of   button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(videoCallIcon: UIImage)` | Sets the icon for the video button in `CometChatMessageHeader` | 
| `set(videoCallIconTint: UIColor)` | Sets the tint color for the video button in `CometChatMessageHeader` | 
| `hide(videoCallButton: Bool)` | Hides the video call button in `CometChatMessageHeader` | 


```swift
__ syntax for set(videoCallIcon: UIImage) 
messageHeader.set(videoCallIcon: UIImage(named: "video-call.png") 

__ syntax for set(videoCallIconTint: UIColor)
messageHeader.set(videoCallIconTint: .white)

__ syntax for hide(videoCallButton: Bool)
messageHeader.hide(videoCallButton: true)
```



---

### Info

Info button is the UIButton which triggers detail screen from CometChatMessageHeader. You can modify the properties of   button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(infoIcon: UIImage)` | Sets the icon for the info button in `CometChatMessageHeader` | 
| `set(infoIconTint: UIColor)` | Sets the tint color for the info button in `CometChatMessageHeader` | 
| `hide(infoButton: Bool)` | Hides the info button in `CometChatMessageHeader` | 


```swift
__ syntax for set(infoIcon: UIImage) 
messageHeader.set(infoIcon: UIImage(named: "info.png") 

__ syntax for set(infoIconTint: UIColor)
messageHeader.set(infoIconTint: .white)

__ syntax for hide(infoButton: Bool)
messageHeader.hide(infoButton: true)
```



---

### Set InputData

This method will set the data as per the params in the input data in CometChatMessageHeader

| Method | Description | 
| ---- | ---- | 
| `set(inputData: InputData)` | This method will set the data as per the params in the input data in CometChatMessageHeader | 


```swift
var inputData = InputData(title: true, thumbnail: true, status: true) { user in
                 return user.metadata?["address"] as? String ?? ""
                 }

__ syntax for set(inputData: InputData)
messageHeader.set(inputData: inputData)
```



---

### Set Style

You can modify the **font, color, cornerRadius, borderWidth,** and other properties of CometChatMessageHeader using `set(style: Style)`. It is used to customise the inner components as per the requirements.

| Method | Description | 
| ---- | ---- | 
| `set(style: Style)` | You can modify the **font, color, cornerRadius, borderWidth,** and other properties of **`DataItem`** using `set(style: style)`. It is used to customise the inner components as per the requirements. | 


```swift
__ syntax for set(style: Style)

let style = Style(background: UIColor.black, border: 1, cornerRadius: 20, titleColor: UIColor.white, titleFont: UIFont.systemFont(ofSize: 22, weight: .medium), subTitleColor: UIColor.gray, subTitleFont: UIFont.systemFont(ofSize: 18, weight: .regular))
                
messageHeader.set(style: style)
```



---

### Set Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


```swift
__ creating object of AvatarConfiguration
let avatarConfiguration = AvatarConfiguration().set(cornerRadius: 5).set(bordetWidth: 2)
 
__ creating object of Input Data
var inputData = InputData(title: true, thumbnail: true, status: true) { user in
                 return user.metadata?["address"] as? String ?? ""
                 }

__ creating object of UserListItemConfiguration
let messageHeaderConfiguration =  MessageHeaderConfiguration().set(inputData: inputData)
                                 .set(set(avatarConfiguration: avatarConfiguration))


messageHeader.set(configurations: [messageHeaderConfiguration])
```



---