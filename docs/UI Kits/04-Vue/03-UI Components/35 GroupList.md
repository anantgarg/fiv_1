
This component renders a scrollable list of groups that has been created in a  CometChat app. By default, CometChatGroupList loads the 30 groups. The state of the component is communicated via 3 states i.e **empty**, **loading** and **error.**

The UI for each individual group is rendered using [GroupListItem](https://www.cometchat.com/docs/v3/react-chat-ui-kit/grouplistitem) component.

It uses **GroupsRequestBuilder** class of the CometChat SDK.


![](https://uploads.developerhub.io/prod/x9W8/i7ahs0bnumwweuiuwtemn1nd21qg3t6ya4t2ymtb3szbah752h7dtz6qygc8hioa.png)


## Basic Usage


<iframe src="https://codesandbox.io/embed/musing-jasper-hg43wr?fontsize=14&hidenavigation=1&theme=dark"
     style={{ width: '100%', height: '500px', border: 0, borderRadius: '4px', overflow:'hidden' }}
     title="musing-jasper-hg43wr"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>


## Properties

### limit

This prop sets the limit i.e. the number of groups that should be fetched in a single iteration.


| Type | Default | 
| ---- | ---- | 
| number | 30 | 


### searchKeyword

This prop sets the search string based on which the users are to be fetched.


| Type | Default | 
| ---- | ---- | 
| string | "" | 


### joinedOnly

This prop when set to true, will ask the SDK to only return the groups that the user has joined or is a part of.


| Type | Defaulr | 
| ---- | ---- | 
| bool | false | 


### tags

This prop accepts a list of tags based on which the list of groups is to be fetched. The list fetched will only contain the groups that have been tagged with the specified tags.


| Type | Default | 
| ---- | ---- | 
| array | [] | 


### style

Object containing all the styling properties


| **Type** | **Default** | 
| ---- | ---- | 
| object | `{ `\n\n\n\n\n\n\n\n`width: "100%",`\n\n\n\n\n\n\n\n`height: "100%",`\n\n\n\n\n\n\n\n`background: "white",`\n\n\n\n\n\n\n\n`border: "0 none",`\n\n\n\n\n\n\n\n`cornerRadius: "0",`\n\n\n\n\n\n\n\n`loadingIconTint: "",`\n\n\n\n\n\n\n\n`emptyTextFont: "",`\n\n\n\n\n\n\n\n`emptyTextColor: "",`\n\n\n\n\n\n\n\n`errorTextFont: "",`\n\n\n\n\n\n\n\nerrorTextColor: ""\n\n\n\n\n\n\n\n`}` | 


loadingIconURL

Image URL of the loading icon


| Type | Default | 
| ---- | ---- | 
| string | spinner.svg | 


### customView

Object containing all custom component view for all 3 states of the component i.e. empty, loading and error.


| Type | Default | 
| ---- | ---- | 
| object | {\n\n\n\n\n\n\n\nloading: "",\n\n\n\n\n\n\n\nempty: "",\n\n\n\n\n\n\n\nerror: "",\n\n\n\n} | 


### emptyText

Text to be displayed during the empty state of the component


| Type | Default | 
| ---- | ---- | 
| string | "No groups" | 
|  |  | 


### errorText

Text to be displayed when the component encounters an error.


| Type | Default | 
| ---- | ---- | 
| string | "Something went wrong" | 


### hideError

This prop when set to true, hides the error from being displayed in the UI.


| Type | Default | 
| ---- | ---- | 
| bool | false | 


### onErrorCallback

The method invoked when the component encounters an error.


| Type | Default | 
| ---- | ---- | 
| function | () =&gt; {} | 


### activeGroup

Selected group's SDK object


| Type | Default | 
| ---- | ---- | 
| object | null | 


