The `CometChatGroupListItem` is a reusable component that is present in `CometChatGroupList`. It is tightly coupled with SDK's Conversation object.

You can modify the various component using the methods as described below:

![](https://uploads.developerhub.io/prod/x9W8/k3rn3o29adhliqhtbiggo02t0rev0xa73lt25k74rx60btherkloxcb1fub9429e.png)

## Components

1. **User**
2. **Background**
3. **Title**
4. **Subtitle**
5. **Avatar**
6. **Status Indicator**

## Methods

## Group

`GroupListItem` takes SDK's Group object and manipulates the other components in `GroupListItem`**.**

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | Sets the Group object used in the `GroupListItem` for all sub-components. | 


## Background

The background is a UIView which is present in the backdrop for **`GroupListItem`**. You can modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | Sets the title font for `GroupListItem` | 


## Title

The title is a `UILabel` which specifies a title for **`GroupListItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title for `GroupListItem`. | 
| `set(titleWithAttributedText: NSAttributedString)` | Sets the title with attributed text for `GroupListItem`. | 
| `set(titleColor: UIColor)` | Sets the title color for `GroupListItem` | 
| `set(titleFont: UIFont)` | Sets the title font for `GroupListItem` | 


## Subtitle

The subtitle is a `UILabel` which specifies a title for **`GroupListItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(subTitle: String)` | Sets the title for `GroupListItem`. | 
| `set(subTitleWithAttributedText: NSAttributedString)` | Sets the title with attributed text for `GroupListItem`. | 
| `set(subTitleColor: UIColor)` | Sets the title color for `GroupListItem` | 
| `set(subTitleFont: UIFont)` | Sets the title font for `GroupListItem` | 


## Avatar

The avatar is a `UIImageView` that specifies an avatar for **`GroupListItem`**. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(avatar: CometChatAvatar)` | Sets the avatar for `UserListItem`. | 
| `hide(avatar: Bool)` | Hides the avatar for `UserListItem`. | 


## StatusIndicator

The status indicator is a `CometChatStatusIndicator` that specifies a user status for a user for **`GroupListItem`**. You can modify the title using the below methods:

| Methods | Description | 
| ---- | ---- | 
| statusIndicator.set(icon: UIImage) | Sets the  icon for status indicator | 
| statusIndicator.set(backgroundColor: UIColor) | Sets the  background color for status indicator | 
| statusIndicator.set(borderWidth: CGFloat) | Sets the border width for status indicator | 
| `hide(statusIndicator: Bool)` | hide/show the status indicator for `GroupListItem` | 


---

## Set InputData

This method will set the data as per the params in the input data in GroupListItem

| Method | Description | 
| ---- | ---- | 
| `set(data: InputData)` | This method will set the data as per the params in the input data in GroupListItem | 


## Set Style

This method will set the style for `GroupListItem`

| Method | Description | 
| ---- | ---- | 
| set(style: Style) | This method will set the style for `GroupListItem` | 


## Set Configurations

This method will take the array of configurations and then internally it will process configurations for the required components

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


---

## Uses

```swift
if let groupListItem = tableView.dequeueReusableCell(withIdentifier: 
"CometChatGroupListItem", for: indexPath) as? CometChatGroupListItem {

  groupListItem.set(group: currentGroup)
							.set(background: [UIColor.clear.cgColor])

            
   return  groupListItem
  }
```

