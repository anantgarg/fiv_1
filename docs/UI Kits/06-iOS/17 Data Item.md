## Overview

**`CometChatDataItem`** is a custom component’s view consists of **thumbnail**, **status**, **title**, and **subtitle** fields. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. This Component also have Tail (Placeholder to load any component in it )

![](https://uploads.developerhub.io/prod/x9W8/6ntdq1gi863huk2cg6il9xn26ppt7hzgoil4u11wpyd42wh6imxl2lw0pamjevl1.png)

CometChatDataItem is a reusable component which is used across multiple components with different variations as shown below. 

#### User List

![](https://uploads.developerhub.io/prod/x9W8/jo2v1bxlnngvvklc9fbssmhuq85zklf195sh1yzjlxkzkfb78l2vqwkvyy0tylc7.png)

#### Group List

![](https://uploads.developerhub.io/prod/x9W8/c2xar9bx4nqrm0rl5qr79kwrp2f4zwtxx2jwlkh56qynfx9f0ygayi5w9epnv7po.png)

#### Group Member List

![](https://uploads.developerhub.io/prod/x9W8/h7ds56yw5ufdwq9pyw1otdadzjfqf69hqdz5av9dq0uhz1bdofhao2iq0nddbejh.png)

#### Group Member List (with Scope Change)

![](https://uploads.developerhub.io/prod/x9W8/i5wlil5ij7dcfe3j4kgno7xe9rwytk8ljnz5q7zatwzsgidxeybdq1u8do1dha3a.png)

#### Banner Member List

![](https://uploads.developerhub.io/prod/x9W8/lcghqb4zormay569dck4lphnn6azc5y5frp0skluwrp2gy5rlicc5w59gya28na9.png)

#### Add Members

![](https://uploads.developerhub.io/prod/x9W8/ogk68b5n2gjruisgpng3ylcbpooi67tlycuzkje8786o4efx45roeaffrvi83ucs.png)

---

## Components

1. User
2. Group
3. GroupMember
4. Background
5. Title
6. Subtitle
7. Avatar
8. StatusIndicator
9. Tail

## Methods

### User

`CometChatDataItem` takes SDK's `User` object and manipulates the other components in `CometChatDataItem`**.**

| Method | Description | 
| ---- | ---- | 
| `set(user: User)` | Sets the User object used in the CometChatDataItem for all sub-components. | 


```swift
__ syntax for set(user: User)	
dataItem.set(user: user)	 __ The object which is going to be rendered in the data  item
```



---

### Group

`CometChatDataItem` takes SDK's Group object and manipulates the other components in `CometChatDataItem`**.**

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | Sets the Group object used in the `CometChatDataItem` for all sub-components. | 


```swift
__ syntax for set(group: Group)	
dataItem.set(group: group)	__ The object which is going to be rendered in the data item
```



---

### Group Member

`CometChatDataItem` takes SDK's Group object and manipulates the other components in `CometChatDataItem`**.**

| Method | Description | 
| ---- | ---- | 
| `set(groupMember: GroupMember)` | Sets the `GroupMember` object used in the `CometChatDataItem` for all sub-components. | 


```swift
__ syntax for set(groupMember: GroupMember)	
dataItem.set(groupMember: groupMember)	 __ The object which is going to be rendered in the  data item
```



---

### Background

The background is a UIView which is present in the backdrop for **`DataItem`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the background color for **`DataItem`** | 


```swift
__ syntax for set(background: [UIColor])
dataItem.set(background: [UIColor.green.cgColor])
```



![](https://uploads.developerhub.io/prod/x9W8/fdobm6cuzmslzp4ilzaeou77iasfdg0eoc25rrdxlnwqgz3xnk38vxnzg78jpqht.png)

---

### Title

The title is a `UILabel` which specifies a title for **`DataItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for **`DataItem`**. | 
| `set(titleWithAttributedText: NSAttributedString)` | Sets the title with attributed text for **`DataItem`**. | 
| `set(titleColor: UIColor)` | Sets the title color for **`DataItem`** | 
| `set(titleFont: UIFont)` | Sets the title font for **`DataItem`** | 
| `hide(title: Bool)` | hide/shows the title for **`DataItem`** | 


```swift
__ syntax for set(title: String)
dataItem.set(title: user.name)

__ syntax for set(titleColor: UIColor)
dataItem.set(titleColor: UIColor.red)

__ syntax for set(titleFont: UIFont)
dataItem.set(titleFont: UIFont(name: "AmericanTypewriter-Bold", size: 17))

__ syntax for hide(title: Bool)
dataItem.hide(title: false)
```



![](https://uploads.developerhub.io/prod/x9W8/tjk5nhfziqv9ne14watndde1ebtykez30zncpa2q0thbz9ljspdn65gmp81aef53.png)

---

### Subtitle

The subTitle is a `UILabel` which specifies a subTitle for **`DataItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(subTitle: String?)` | Sets the subTitle for **`DataItem`**. | 
| `set(subTitleWithAttributedText: NSAttributedString)` | Sets the subTitle with attributed text for **`DataItem`**. | 
| `set(subTitleColor: UIColor)` | Sets the subTitle color for **`DataItem`** | 
| `set(subTitleFont: UIFont)` | Sets the subTitle font for **`DataItem`** | 
| `hide(subTitle: Bool)` | hide/shows the subTitle for **`DataItem`** | 


```swift
__ syntax for set(subTitle: String?)
dataItem.set(subTitle: String(user?.metadata["address"] ?? ""))

__ syntax for set(subTitleColor: UIColor)
dataItem.set(subTitleColor: UIColor.red)

__ syntax for set(subTitleFont: UIFont)
dataItem.set(subTitleFont:  UIFont(name: "AmericanTypewriter-Regular", size: 15))

__ syntax for hide(subTitle: Bool)
dataItem.hide(subTitle: false)
```



![](https://uploads.developerhub.io/prod/x9W8/clm60ct96s9tu10hzqtw7xxwvt94wqr20efzi9e0i8la3k26sukt03qntivot5km.png)

---

### Avatar

The avatar is a `UIImageView` that specifies an avatar for **`DataItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(avatar: CometChatAvatar)` | Sets the avatar for **`DataItem`**. | 
| `hide(avatar: Bool)` | Hides the avatar for **`DataItem`**. | 


```swift
__ syntax for set(avatar: CometChatAvatar)
let avatar = CometChatAvatar().set(cornerRadius: 20)
dataItem.set(avatar: avatar)

__ syntax for hide(avatar: Bool)
dataItem.hide(avatar: false)
```



---

### StatusIndicator

The status indicator is a `CometChatStatusIndicator` that specifies a user status for a user for **`DataItem`**. You can modify the title using the below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(statusIndicator: CometChatPro.CometChat.UserStatus)` | Sets the status indicator for **`DataItem`** | 
| `hide(statusIndicator: Bool)` | hide/show the status indicator for **`DataItem`** | 


```swift
__ syntax for set(statusIndicator: CometChatPro.CometChat.UserStatus)
dataItem.set(statusIndicator: .online)

__ syntax for hide(statusIndicator: Bool)
dataItem.hide(statusIndicator: false)
```



---

### Set InputData

This method will set the data as per the params in the input data in **`DataItem`**

| Method | Description | 
| ---- | ---- | 
| `set(inputData: InputData)` | This method will set the data as per the params in the input data in **`DataItem`** | 


```swift
var inputData = InputData(title: true, thumbnail: true, status: true) { user in
                 return user.metadata?["address"] as? String ?? ""
                 }

__ syntax for set(inputData: InputData)
dataItem.set(inputData: inputData)
```



---

### Set TailView

This method is use to render any custom component/view in a tail part of the **`DataItem`**

| Method | Description | 
| ---- | ---- | 
| `set(tailView: UIView?)` | This method is use to render any custom component/view in a tail part of the **`DataItem`** | 


```swift
var customView = UIView() __ Create customView

__ syntax for set(tailView: UIView?)
dataItem.set(tailView: customView)
```



---

### Set Style

You can modify the **font, color, cornerRadius, borderWidth,** and other properties of CometChatDataItem using `set(style: Style)`. It is used to customise the inner components as per the requirements.

| Method | Description | 
| ---- | ---- | 
| `set(style: Style)` | You can modify the **font, color, cornerRadius, borderWidth,** and other properties of **`DataItem`** using `set(style: style)`. It is used to customise the inner components as per the requirements. | 


```swift
let style = Style(background: UIColor.black, border: 1, cornerRadius: 20, titleColor: UIColor.white, titleFont: UIFont.systemFont(ofSize: 22, weight: .medium), subTitleColor: UIColor.gray, subTitleFont: UIFont.systemFont(ofSize: 18, weight: .regular))
              

__ syntax for set(style: Style)
userListItem.set(style: style)
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
let userListItemConfiguration =  UserListItemConfiguration().set(inputData: inputData)
                                 .set(background: [UIColor.black.cgColor])
                                 .set(set(avatarConfiguration: avatarConfiguration))


userListItem.set(configurations: [userListItemConfiguration, avatarConfiguration])
```



---

## Usage

```swift
if let dataItem = tableView.dequeueReusableCell(withIdentifier: 
"CometChatDataItem", for: indexPath) as? CometChatDataItem {

  dataItem.set(user: currentUser)
					.set(background: [UIColor.clear.cgColor])
					.set(titleColor: .black)
            
   return  dataItem
  }
```

