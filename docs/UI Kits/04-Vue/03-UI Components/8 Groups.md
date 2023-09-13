
`CometChatGroups` is a independent component used to set up a screen that shows the list of users belonging to an app and gives them the ability to search for a specific user.

`CometChatGroups` sets up the following functionality internally:

- Header with customizable title.
- List of users with pagination.

This is a container component that wraps and formats the [ListBase](https://www.cometchat.com/docs/v3/react-chat-ui-kit/listbase) and [GroupList](https://www.cometchat.com/docs/v3/react-chat-ui-kit/grouplist) component, with no behavior of its own. It includes all the options to customize the UI according to our default design system.


![](https://uploads.developerhub.io/prod/x9W8/0t5tg0mmiz8jdyzo5phfszy8nfkkvvsyea5gn1e8v7pwlf2c7p842qwfyh0m4eef.png)


## Basic Usage

You will be able to launch `CometChatGroups` using below code snippet.


<iframe src="https://codesandbox.io/embed/fervent-northcutt-kcfye2?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="CometChatGroups"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>


## Properties

### title

Title of the component


| **Type** | **Default** | 
| ---- | ---- | 
| string | `Groups` | 


searchPlaceholder

Placeholder text of search input


| Type | Default | 
| ---- | ---- | 
| string | "" | 


### activeGroup

### style

Object containing all the styling properties


| Type | Default | 
| ---- | ---- | 
| object | {\n\n\n\n\n\n\n\n`width: "100%",`\n\n\n\n\n\n\n\n`height: "100%",`\n\n\n\n\n\n\n\n`background: "",`\n\n\n\n\n\n\n\n`border: "1px solid #808080",`\n\n\n\n\n\n\n\n`cornerRadius: "0",`\n\n\n\n\n\n\n\n`titleFont: "700 22px Inter, sans-serif",`\n\n\n\n\ntitleColor: "",\n\n\n\n\n\n\n\nbackIconTint: "#3399FF",\n\n\n\n\n\n\n\nsearchBorder: "1px solid #141414",\n\n\n\n\n\n\n\nsearchBackground: "",\n\n\n\n\n\n\n\nsearchTextFont: "",\n\n\n\n\n\n\n\nsearchTextColor: "",\n\n\n\n\n\n\n\nsearchIconTint: "",\n\n\n\n} | 


### backButtonIconURL

image URL for the back button


| Type | Default | 
| ---- | ---- | 
| string | backIcon.svg | 


### showBackButton

This prop when set to true, shows the back button


| Type | Default | 
| ---- | ---- | 
| bool | false | 


### searchIconURL

image URL for the search icon


| Type | Default | 
| ---- | ---- | 
| string | searchIcon.svg | 


### hideSearch

This prop when set to true, hides the search option


| Type | Default | 
| ---- | ---- | 
| bool | false | 


### createGroupIconURL

image URL for the create group icon


| Type | Default | 
| ---- | ---- | 
| string | createIcon.svg | 


### hideCreateGroup

This prop when set to true, hides the option to create groups.


| Type | Default | 
| ---- | ---- | 
| bool | false | 


## Events

`CometChatGroups` provides the following event listeners that allows you to provide callbacks with custom functionality.

To listen to those events provided by `CometChatGroups` user must use `CometChatGroupEvents`.


| Name | Description | 
| ---- | ---- | 
| onItemClick | When the user clicks on a particular user. | 
| onError | When an error is encountered | 


