`CometChatGroupListItem` component renders an individual (CometChat SDK's) Group object.

This component‘s view consists of id, thumbnail, status, title, and subtitle fields. These fields are mapped to the CometChat SDK’s Group object. 

![](https://uploads.developerhub.io/prod/x9W8/f6ou3nzf7ppc63kfnikrzk9o4a9x8m2ltyodkgez13xnbvl3ohccjgb764351yy3.png)

## Basic Usage

<iframe src="https://codesandbox.io/embed/frosty-hill-doq36f?fontsize=14&hidenavigation=1&theme=dark"
     style={{ width: '100%', height: '500px', border: '0', borderRadius: '4px', overflow: 'hidden' }}
     title="frosty-hill-doq36f"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

## Properties

### inputData

This comprises of the mapping of the component’s view with the SDK’s Group class. If inputData is empty, nothing will be displayed. The view can be customised to show/hide particular fields by adding/removing key/value pairs in the inputData object.

| Type | Default | 
| ---- | ---- | 
| object | {\n\n\n\nid: "guid",\n\n\n\nthumbnail:"icon",\n\n\n\nstatus:"groupType",\n\n\n\ntitle: "name"\n\n\n\nsubtitle: "membersCount"\n\n} | 


### style

Object containing all the styling properties

| Type | Default | 
| ---- | ---- | 
| object | `{`\n\n\n\n`width: "100%",`\n\n\n\n`height: "100%",`\n\n\n\n`background: "white",`\n\n\n\n`border: "0 none",`\n\n\n\n`cornerRadius: "0",`\n\n\n\n`titleColor: "RGB(20, 20, 20)",`\n\n\n\n`titleFont: "600 15px Inter",`\n\n\n\n`subtitleColor: "RGBA(20, 20, 20, 0.58)",`\n\n\n`subtitleFont: "400 13px Inter"`\n\n\n\n`}` | 


### groupObject

SDK’s group object

| Type | Default | 
| ---- | ---- | 
| object | null | 


### isActive

selected Group 

| Type | Default | 
| ---- | ---- | 
| boolean | false | 
