`CometChatStatusIndicator` component shows the user presence as dots with colored background and group type  as dots with background images.

![](https://res.cloudinary.com/developerhub/image/upload/v1644930425/v2_5163/zhljfarusv1huvfm32hy.png)

---

## Properties

| Props | Description | 
| ---- | ---- | 
| width | Sets the width of the indicator dot | 
| height | Sets the height of the indicator dot | 
| `cornerRadius` | Sets the `cornerRadius` | 
| `border` | Sets an element's border. It sets the values of [border-width](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width), [border-style](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style), and [border-color](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color). | 
| backgroundColor | Sets the backgroundcolor for the indicator dot | 
| backgroundImage | Sets the backgroundimage for the colored dot | 
| `style` | Custom style rules | 


---

## Uses

```javascript
import React from "react";
import { CometChatStatusIndicator } from "cometchat-react-ui-kit";

const App = props => {
  
	return (
    <CometChatStatusIndicator status="offline" offlineBackgroundColor="orange" _>
  ) 
}
```



---