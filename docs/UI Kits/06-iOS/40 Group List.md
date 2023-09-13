## Overview

`CometChatGroupList` component renders a scrollable list of groups that has been created in a CometChat app. By default, `CometChatGroupList` loads the 30 groups. The state of the component is communicated via 3 states i.e **empty**, **loading** and **error.**

The UI for each Group is rendered using `CometChatDataItem` component.

It uses `GroupsRequestBuilder` class of the CometChat SDK.

![](https://uploads.developerhub.io/prod/x9W8/o78mn7fzoqdqm6h731girag9t7yl4gt1zhx1qphx5pslio1zp29mvtjxr48x8oz3.png)

---

## Components

`CometChatGroupList` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatDataItem** | This component’s view consists of **avatar**, **status indicator**,  **title**, and **subtitle**. The fields are then mapped with the SDK’s `user`, `group` or `groupMember` class. This Component also have Tail (Placeholder to load any component in it ) | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/data-item) | 


---

## Methods

### Background

The background is a `UIView` which is present in the backdrop for **`GroupList.`** You will be able to modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | This method will set the background color for `GroupList`, it can take an array of multiple colors for the gradient background. | 


```swift
__ syntax for set(background: [UIColor])
groupList.set(background: [UIColor.systemBackground.cgColor])
```



---

### Controller

This method will set the instance of the view controller from which the **`GroupList`** is presented. This method is mandatory to call when the user list is presented.

| Method | Description | 
| ---- | ---- | 
| `set(controller: UIViewController)` | This method will set the instance of the view controller from which the GroupList is presented. This method is mandatory to call when the user list is presented. | 


```swift
__ syntax for set(controller: UIViewController)
groupList.set(controller: self)
```



---

### Set Limit

This method will specify the option to set the limit to fetch groups in **`GroupList` .**

| Method | Description | 
| ---- | ---- | 
| set(limit: Int) | This method will specify the option to set the limit to fetch groups in **`GroupList` .** | 


```swift
__ syntax for set(limit: Int)
groupList.set(limit: 30)
```



---

### Set Search Keyword

This method will specify the option to set the keyword to fetch users in **`UserList` .**

| Method | Description | 
| ---- | ---- | 
| set(searchKeyword: String) | This method will specify the option to set the keyword to fetch groups in **`GroupList` .** | 


```swift
__ syntax for set(searchKeyword: String)
groupList.set(searchKeyword: "searched text")
```



---

### Set List

This method will allow the user to set the list of groups  in **`GroupList` .**

| Method | Description | 
| ---- | ---- | 
| `set(groupList: [Group])` | This method will allow the user to set the  list of groups  in **`GroupList` .** | 


```swift
__ syntax for set(groupList: [Group])
let groups = [group1, group2, group3] __ Array of predefined sets of 'Group' Object
groupList.set(groupList: groups)
```



---

### Set Tags

This method will set the tags for groups in **`GroupList` .**

| Method | Description | 
| ---- | ---- | 
| `set(tags:[String])` | This method will set the tags for groups  in **`GroupList` .** | 


```swift
__ syntax for set(tags:[String])
groupList.set(tags:["economy", "premium"])
```



---

### Set JoinedOnly

This method will enable the joined only mode for groups in **`GroupList` .**

| Method | Description | 
| ---- | ---- | 
| `set(joinedOnly: Bool)` | This method will enable the joined only mode for groups in **`GroupList` .** | 


```swift
__ syntax for set(joinedOnly: Bool)
groupList.set(joinedOnly: true)
```



---

### Add Group

This method specifies the option to add group object locally in **`GroupList`**.

| Method | Description | 
| ---- | ---- | 
| `add(group: Group)` | This method specifies the option to add group object locally in **`GroupList`**. | 
| `insert(group: Group, at: Int?)` | This method specifies the option to insert group object locally at any index position in **`GroupList`**. | 


```swift
__ syntax for add(group: Group)
groupList.add(group: group)

__ syntax for insert(group: Group, at: Int?)
groupList.insert(group: group, at: 0)
```



---

### Update Group

This method specifies the option to update group object locally in **`GroupList`**.

| Method | Description | 
| ---- | ---- | 
| `update(group: Group)` | This method specifies the option to update group object locally in **`GroupList`**. | 


```swift
__ syntax for update(group: Group)
groupList.update(group: group)
```



---

### Remove Group

This method specifies the option to remove group object locally from the **`GroupList`**.

| Method | Description | 
| ---- | ---- | 
| `remove(group: Group)` | This method specifies the option to remove group object locally from the **`GroupList`**. | 


```swift
__ syntax for remove(group: Group)
groupList.remove(group: group)
```



---

### Clear List

This method will clear the groups locally in **`GroupList`.**

| Method | Description | 
| ---- | ---- | 
| `clearList()` | This method will clear the groups locally in **`GroupList`.** | 


```swift
__ syntax for clearList()	
groupList.clearList()
```



---

### Get Size

This method specifies the count of group displayed in GroupList.

| Method | Description | 
| ---- | ---- | 
| size() | This method specifies the count of groups displayed  in **`GroupList`**. | 


```swift
__ syntax for size()
groupList.size()
```



---

### Empty State

This method will specify the option to modify the behaviour when the groups list is empty due to any reason.

| Method | Description | 
| ---- | ---- | 
| `set(emptyStateMessage: String)` | This method will add the message to be displayed on the UI when the groups are empty | 
| `set(emptyStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when the groups are empty | 
| `set(emptyStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when the groups are empty | 
| `set(emptyView: UIView?)` | This method will add the custom view passed by the user to on the UI when groups are empty | 


```swift
__ syntax for set(emptyStateMessage: String)
groupList.set(emptyStateMessage: "No Groups")

__ syntax for set(emptyStateTextFont: UIFont)
groupList.set(emptyStateTextFont: UIFont.systemFont(ofSize: 26, weight: .bold))

__ syntax for set(emptyStateTextColor: UIColor)
groupList.set(emptyStateTextColor: UIColor.white)

__ or 

__ syntax for set(emptyView: UIView?)
let emptyView = UIView() __ with custom images_strings etc.
groupList.set(emptyView: emptyView)
```



### Error State

This method will specify the option to modify the behaviour when the groups list is empty due to any interruption.

| Method | Description | 
| ---- | ---- | 
| `set(errorMessage: String)` | This method will add the message to be displayed on the UI when user faces any interruption  while fetching groups | 
| `set(errorView: UIView?)` | This method will add the custom view passed by the user to on the UI when user faces any interruption  while fetching groups | 
| `hide(errorMessage: Bool)` | This method will hide the error message popup when the interruption happens | 
| `set(errorStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when user faces any interruption  while fetching groups | 
| `set(errorStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when user faces any interruption while fetching groups | 


```swift
__ syntax for set(errorMessage: String)
groupList.set(errorMessage: "Unable to fetch Groups at this moment")

__ syntax for set(errorStateTextFont: UIFont)
groupList.set(emptyStateTextFont: UIFont.systemFont(ofSize: 18, weight: .semibold))

__ syntax for set(errorStateTextColor: UIColor)
groupList.set(emptyStateTextColor: UIColor.white)

__ syntax for hide(errorMessage: true)
groupList.hide(errorMessage: true)

__ or 

__ syntax for set(errorView: UIView?)
let errorView = UIView() __ with custom images_strings etc.
groupList.set(errorView: errorView)
```



---

### Set Style

This method will set the styling for **`GroupList.`**

| Method | Description | 
| ---- | ---- | 
| set(style: Style) | This method will set the styling for **`GroupList`.``** | 


```swift
__ syntax for set(style: Style)
let style = Style(background: UIColor.black, border: nil, cornerRadius: nil, titleColor: nil, titleFont: nil, subTitleColor: nil, subTitleFont: nil, loadingIconTint: nil, emptyStateTextFont: UIFont.systemFont(ofSize: 26, weight: .bold), emptyStateTextColor: UIColor.white, errorStateTextFont: UIFont.systemFont(ofSize: 18, weight: .semiBold) , errorStateTextColor: UIColor.white)
        
groupList.set(style: style)
```



---

### Set Configurations

This method will take the array of configurations and then internally it will process configurations for the required components

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


#### InputData

InputData is a class use to configure the CometChatDataItem

| Paramters | Description | 
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
var inputData = InputData(title: true, thumbnail: true, status: true) { grouop in
                 return (group as? Group)?.description as? String ?? ""
                 }
dataItemConfiguration.set(inputData: inputData)
         
__Passing array of configurations to groupList
groupList.set(configurations: [dataItemConfiguration, avatarConfiguration]))
```



---