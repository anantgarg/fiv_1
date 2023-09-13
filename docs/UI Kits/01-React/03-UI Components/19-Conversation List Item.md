The `CometChatConversationListItem` is a reusable component that is present in `CometChatConversationList`.  `CometChatConversationListItem` is tightly coupled with  SDK's Conversation object.

You can modify the various components using the methods as described below:

![](https://res.cloudinary.com/developerhub/image/upload/v1644843778/v2_5163/jvimylzegnkadvhb8dsv.png)

---

## Components

1. **Conversation**
2. **Background**
3. **Title**
4. **Subtitle**
5. **Avatar**
6. **Receipt**
7. **Time**
8. **UnreadCount**
9. **StatusIndicator**
10. **TypingIndicator**
11. **ThreadIndicator**

---

## Properties

**Conversation**

`ConversationListItem` takes SDK's Conversation object and manipulates the other components in ConversationListItem**.**

| Prop | Description | 
| ---- | ---- | 
| conversation | Sets the conversation object of CometChat SDK | 


**Background**

The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method. 

| Prop | Description | 
| ---- | ---- | 
| background | The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/background) | 


## **Title**

Title for each conversation. You can modify the title using the below properties:

| Name | Description | 
| ---- | ---- | 
| title | Sets the title for ConversationListItem. | 
| titleColor | Sets the color for title text in ConversationListItem | 
| titleFont | Sets all the different properties of the title element's font. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | 


**SubTitle**

Subtitle for each conversation. You can modify the subtitle using the below properties:

| Name | Description | 
| ---- | ---- | 
| `subTitle` | Sets the subtitle for ConversationListItem. | 
| `subTitleColor` | Sets the color for subtitle text in ConversationListItem | 
| `subTitleFont` | Sets all the different properties of the subtitle element's font. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | 


**Avatar**

Thumbnail URL for the avatar for each conversation. You can modify the avatar using the below properties:

| Name | Description | 
| ---- | ---- | 
| avatar | Sets the avatar for ConversationListItem. | 
| hideAvatar | Hide the avatar for ConversationListItem. | 


**Receipt**

Read receipt for the last message for each conversation. You can modify the receipt using the below properties:

| Name | Description | 
| ---- | ---- | 
| `receipt` | Sets the receipt image for ConversationListItem as per the message status. | 
| `hideReceipt` | Hide the receipt for ConversationListItem. | 


## **Time**

Timestamp of each conversation. You can modify the time using the below properties:

| Name | Description | 
| ---- | ---- | 
| `time` | Sets the time for ConversationListItem. | 
| `timeFont` | Sets all the different properties of the time element's font. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | 
| `timeColor` | Sets the color for time text in ConversationListItem | 


**UnreadCount**

Count of unread messages. You can modify the title using the below properties:

| Name | Description | 
| ---- | ---- | 
| `unreadCount` | Sets the count of unread messages for each conversation | 
| `hideUnreadCount` | Hides the count of unread messages | 


**StatusIndicator**

User presence of the user in the conversation. You can modify the title using the below properties:

| Name | Description | 
| ---- | ---- | 
| `statusIndicator` | Sets the presence of the user for each conversation | 
| `hideStatusIndicator` | Hides the user presence | 


## **TypingIndicator**

Typing indicators is an indicator to see and share when messages are being typed. You will be able to modify the title using the below properties:

| Name | Description | 
| ---- | ---- | 
| `typingIndicatorText` | Sets the typing text for ConversationListItem | 
| typingIndicatorTextFont | Sets the typing text font for ConversationListItem | 
| typingIndicatorTextColor | Sets the typing text color for ConversationListItem | 
| `showTypingIndicator` | Hide/show typing indicator  for ConversationListItem | 


**ThreadIndicator**

The thread indicator is an indicator to see when the last message is a reply to a thread conversation. You can modify the text or hide/show using the below properties:

| Name | Description | 
| ---- | ---- | 
| threadIndicatorText | Sets the thread indicator text for ConversationListItem | 
| threadIndicatorTextFont | Sets the thread indicator text font for ConversationListItem | 
| threadIndicatorTextColor | Sets the thread indicator text color for ConversationListItem | 
| `hideThreadIndicator` | Hide/show thread indicator  for ConversationListItem | 


**Deleted Messages**

This property will show/Hide deleted messages for ConversationListItem. When this prop is enabled, it shows the sub-title as empty text when the last message is deleted by the user.

| Prop | Description | 
| ---- | ---- | 
| hideDeletedMessages | Hide/show deleted messages for ConversationListItem | 


**Group Actions Messages**

This property will show/Hide group-related actions such as group member joined, left, etc for ConversationListItem. When this method is enabled it shows the sub-title as empty text.

| Prop | Description | 
| ---- | ---- | 
| hideGroupActionMessages | Show/Hide group action messages such as group member joined, left etc for ConversationListItem | 


**Delete Conversation**

This property will enable the delete option for each conversation

| Name | Description | 
| ---- | ---- | 
| showDeleteConversation | Hide/show the delete option for each conversation | 


## Uses

```javascript
import React from "react";
import { CometChatConversationListItem } from "cometchat-react-ui-kit";

const App = props => {
  const conversationObject = CometChat's conversation object;
	return (
    <CometChatConversationListItem conversation={conversationObject} _>
  ) 
}
```

