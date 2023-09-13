
The `CometChatAvatar` component displays an image OR users avatar with fallback to the first two letter of the username OR groups icon with fallback to the first two letter of the group name.


![](https://uploads.developerhub.io/prod/x9W8/vewrw7z79gltgc8lanqdugocgmlgfnox5bvxi2dvr204nlu8p16ykd4q6zl16nw2.png)


---

## Methods / Props


| Methods | Description | 
| ---- | ---- | 
| width | Sets the width of the avatar | 
| height | Sets the height of the avatar | 
| `cornerRadius` | Sets the `borderRadius` | 
| `border` | Sets  border; It sets the values of `border-width`, `border-style`, and `border-color`. [Example link](https://developer.mozilla.org/en-US/docs/Web/CSS/border) | 
| backgroundColor | Sets the `backgroundColor` | 
| backgroundSize | Sets the size of the background image | 
| image | Sets the `avatarUrl` | 
| name | Sets the name of the image | 
| nameTextColor | Sets the text color of the name | 
| nameTextFont | Sets the different properties of font of name | 
| `outerView` | Sets the outer border | 
| outerViewSpacing | Sets the spacing between the inner and outer border | 



## Uses


```javascript
import React from "react";
import { CometChatAvatar } from "cometchat-react-ui-kit";

const App = props => {
  
  const user = {
    uid: "superhero1", 
    avatar:"https:__d2gg9evh47fn9z.cloudfront.net_800px_COLOURBOX36758858.jpg"
  };
  
	return (
    <CometChatAvatar width="36px" height="36px" user={user} _>
  ) 
}
```




---

