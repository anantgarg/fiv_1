
`CometChatStatusIndicator` component shows the user presence as dots with colored background and group type  as dots with background images.


![](https://uploads.developerhub.io/prod/x9W8/b5ezhlxxvmqzlr4ewsbpkcmw77oijrjt286kku3brw6pxuxbm6150sn3ujm3cgbm.png)


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

