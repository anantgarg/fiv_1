The `CometChatBadgeCount` component displays the unread count of messages for one-to-one private and group chats.

![](https://res.cloudinary.com/developerhub/image/upload/v1644930377/v2_5163/tjaw9iblpnxh6ltqlv22.png)

---

## Properties

| Props | Description | 
| ---- | ---- | 
| width | Sets the width of the badge count | 
| height | Sets the height of the badge count | 
| cornerRadius | Sets the `borderRadius` | 
| border | Sets border; It sets the values of `border-width`, `border-style`, and `border-color`. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/border) | 
| background | The background property sets all the background style properties at once, such as color, image, origin, and size or repeat method. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/background) | 
| `textColor` | Sets the text color | 
| `textFont` | Sets all the different properties of the title element's font. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | 
| count | Sets the `count` | 


---

## Uses

```javascript
import React from "react";
import { CometChatBadgeCount } from "cometchat-react-ui-kit";

const App = props => {
  
	return (
    <CometChatBadgeCount count="100" background="#39f" textColor="#fff" _>
  ) 
}
```

