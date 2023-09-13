The `CometChatAvatar` component can be used to display an image for users avatar. By default, the avatar component is configured to pick the first two letters of the user name or group name for representation of the avatar.

![](https://res.cloudinary.com/developerhub/image/upload/v1644930327/v2_5163/ufcg0qq7k3qeld27weal.png)

## Basic Implementation

The typical implementation for CometChatAvatar component would be to import and use in your custom components. 

Example 1 - Here's an example of using this 

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



![](https://uploads.developerhub.io/prod/x9W8/njfzv27l6pdialdfqitalsxocpjunn552muynkrpjarw9qayanwqhezv3ddyf923.gif)

Example 2 - Here's an example of creating custom avatars

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
### Have to edit this code snippet
```



![](https://uploads.developerhub.io/prod/x9W8/yic73bh81qb5cc946jaegnyozi2ojm8yjwqy9mcok8zo8en5zcmmh4qrgp9x6exf.gif)

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


## 

---