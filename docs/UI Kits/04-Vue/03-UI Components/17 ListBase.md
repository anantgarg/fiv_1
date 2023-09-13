
**CometChatListBase** is a container component having title(navigationBar), search(search-bar), background, and a container to embed a list view such as `CometChatConversationList, CometChatGroupList, CometChatUserList,CometChatCallList.`


![](https://uploads.developerhub.io/prod/x9W8/9u1a7cgt9efnafd4lhjbnmnp97dlc3v8t9kxuquf2okrl9hv2vgchnrqs6owdxmp.png)


---

## Properties

## **Background**

The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method.


| Name | Description | 
| ---- | ---- | 
| `background` | The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/background) | 



**Title:** The title property specifies a title for  `CometChatListBase`. You can modify the properties of title in the below ways


| Name | Description | 
| ---- | ---- | 
| title | Sets the title for CometChatListBase | 
| titleColor | Sets the color for title text in CometChatListBase | 
| titleFont | Sets all the different properties of the title element's font. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | 


**Search:** Search is an text input responsible for displaying search keyword and handling search event. You will be able to modify the search bar using the below properties.


| Props | Description | 
| ---- | ---- | 
| `searchBackground` | Sets the background for seach bar in CometChatListBase | 
| `searchCornerRadius` | Sets the corner radius for the search bar in CometChatListBase | 
| `searchPlaceholder` | Sets the placeholder text for search bar in CometChatListBase | 
| `searchTextColor` | Sets the text color  for search bar in CometChatListBase | 
| `searchTextFont` | Sets the text font for search bar in CometChatListBase | 
| searchBorder | Sets the border for search bar in CometChatListBase | 
| hideSearch | Hide/unhide the search bar as per boolean value. | 


**Back:** The back button is the UIButton which the user can show if he wishes to. This button can be modified using the below method:


| Props | Description | 
| ---- | ---- | 
| showBackButton | Hide/show the back button as per the boolean value | 
| backIconTint | Sets the tint color for the back button | 
| backIcon | Sets the icon for the back button | 


---

## Uses


```javascript
import React from "react";
import { CometChatListBase } from "cometchat-react-ui-kit";

const App = props => {
  
	return (
    <CometChatListBase title="Recent Chats">
    	<CometChatConversationList conversationType="groups" _>
    <_CometChatListBase>
  ) 
}
```




---

##

