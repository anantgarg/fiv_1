
`CometChatUsers` is a independent component used to set up a screen that shows the list of users belonging to an app and gives them the ability to search for a specific user.

`CometChatUsers` sets up the following functionality internally:

- Header with customizable title.
- List of users with pagination.

This is a container component that wraps and formats the [ListBase](https://www.cometchat.com/docs/v3/react-chat-ui-kit/listbase) and [UserList](https://www.cometchat.com/docs/v3/react-chat-ui-kit/userlist) component, with no behavior of its own. It includes all the options to customize the UI according to our default design system.


![Users](https://uploads.developerhub.io/prod/x9W8/n3ep3yvw19d0a744ja5eypch2x52xazl9onlgwozonmn3tttz3wsa0ecl64khpuo.png)


`CometChatUsers` is a container component that wraps and formats the `CometChatListBase` and `CometChatUserList` component with no behaviour of its own.

---

## Basic Usage

You will be able to launch `CometChatUsers` using below code snippet.


<iframe src="https://codesandbox.io/embed/cometchatusers-e5vmqr?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="CometChatUsers"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>


---

## Properties

### **title**

Title of the component


| **Type** | **Default** | 
| ---- | ---- | 
| string | `Users` | 


### **searchPlaceholder**

Placeholder text of search input


| **Type** | **Default** | 
| ---- | ---- | 
| string | `Search` | 


### **style**

Object containing all the styling properties


| **Type** | **Default** | 
| ---- | ---- | 
| object | `{ `\n\n\n\n\n\n\n\n`width: "100%",`\n\n\n\n\n\n\n\n`height: "100%",`\n\n\n\n\n\n\n\n`background: "",`\n\n\n\n\n\n\n\n`border: "1px solid #808080",`\n\n\n\n\n\n\n\n`cornerRadius: "0",`\n\n\n\n\n\n\n\n`titleFont: "700 22px Inter, sans-serif",`\n\n\n\n\ntitleColor: "",\n\n\n\n\n\n\n\nbackIconTint: "#3399FF",\n\n\n\n\n\n\n\nsearchBorder: "1px solid #141414",\n\n\n\n\n\n\n\nsearchBackground: "",\n\n\n\n\n\n\n\n        searchTextFont: "",\n\n\n\n\n\n\n\n        searchTextColor: "",\n\n\n\n\n\n\n\n        searchIconTint: "",\n\n\n\n\n\n\n\n`}` | 


### **backButtonIconURL**

image URL for the back button


| **Type** | **Default** | 
| ---- | ---- | 
| string | backIcon.svg | 


### **showBackButton**

If true, show the back button


| **Type** | **Default** | 
| ---- | ---- | 
| boolean | false | 


### **searchIconURL**

image URL for the search icon


| **Type** | **Default** | 
| ---- | ---- | 
| string | searchIcon.svg | 


### **hideSearch**

This prop when set to true, hides the search option


| **Type** | **Default** | 
| ---- | ---- | 
| boolean | false | 


### **activeUser**

Selected user's SDK object


| **Type** | **Default** | 
| ---- | ---- | 
| object | null | 


## Events

`CometChatUsers` provides the following event listeners that allows you to provide callbacks with custom functionality.

To listen to those events provided by `CometChatUsers` user must use CometChatUserEvents.


| Name | Description | 
| ---- | ---- | 
| onItemClick | When the user clicks on a particular user. | 
| onError | When an error is encountered | 


