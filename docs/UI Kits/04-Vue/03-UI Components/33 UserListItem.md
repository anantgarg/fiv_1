
`CometChatUserListItem` component renders an individual (CometChat SDK's) User object.

This component‘s view consists of id, thumbnail, status, title, and subtitle fields. These fields are then mapped to the CometChat SDK’s User object.


![Users](https://uploads.developerhub.io/prod/x9W8/6ubpaf5pxjj8z25cyiy36pzpz9b2q4f6jn0p46oyanwrff24v5gdu6oh6lrdmprx.png)


## Basic Usage


<iframe src="https://codesandbox.io/embed/stupefied-torvalds-itttsi?fontsize=14&hidenavigation=1&theme=dark"
     style={{ width: '100%', height: '500px', border: 0, borderRadius: '4px', overflow:'hidden' }}
     title="stupefied-torvalds-itttsi"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>


## Properties

### inputData

This comprises of the mapping of the component’s view with the SDK’s User class. If inputData is empty, nothing will be displayed. The view can be customised to show/hide particular fields by adding/removing key/value pairs in the inputData object.


| Type | Default | 
| ---- | ---- | 
| object | {\n\n\n\n\n\n\n\nid: "uid", \n\n\n\n\n\n\n\nthumbnail:"avatar",\n\n\n\n\n\n\n\nstatus:"status", \n\n\n\n\n\n\n\ntitle: "name"\n\n\n\n\n\n\n\nsubtitle: "orgname"\n\n\n\n} | 


### style

Object containing all the styling properties


| **Type** | **Default** | 
| ---- | ---- | 
| object | `{\n\n\n\nwidth: "100%",`\n\n\n\n\n\n\n\n`height: "100%",`\n\n\n\n\n\n\n\n`background: "white",`\n\n\n\n\n\n\n\n`border: "0 none",`\n\n\n\n\n\n\n\n`cornerRadius: "0",`\n\n\n\n\n\n\n\n`titleColor: "RGB(20, 20, 20)",`\n\n\n\n\n\n\n\n`titleFont: "600 15px Inter",`\n\n\n\n\n\n\n\n`subtitleColor: "RGBA(20, 20, 20, 0.58)",`\n\n\n\n\n`subtitleFont: "400 13px Inter"`\n\n\n\n\n\n\n\n`}` | 


### userObject

SDK’s user object


| **Type** | **Default** | 
| ---- | ---- | 
| object | null | 


### isActive

selected User


| **Type** | **Default** | 
| ---- | ---- | 
| boolean | false | 


