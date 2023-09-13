
This component renders a scrollable list of users that has been created in an  CometChat app. By default, CometChatUserList loads 30 users.The state of the component is communicated via 3 states i.e **empty**, **loading** and **error.**

The UI for each individual user is rendered using [UserListItem](https://www.cometchat.com/docs/v3/react-chat-ui-kit/userlistitem) component.

It uses **UsersRequestBuilder** class of the CometChat SDK.


![Users - empty state](https://uploads.developerhub.io/prod/x9W8/brebh6y4yqmh286j5pvvc9f8ogoc4kpu93d9mf866vqjmv6aiqep4xuyfuis8yh4.png)



![Users](https://uploads.developerhub.io/prod/x9W8/47g7tn0pjg084lghewclkh6letg3i0akhmmzb8jajsqbx16ovurwm1g1x92tz1qz.png)



![Users - error state](https://uploads.developerhub.io/prod/x9W8/uwtkzb8h5mg2nj15q8fpd3ir250byiym9l4wqks2jlkcthb9mw830g4p2s5dqb60.png)


## Basic Usage


<iframe src="https://codesandbox.io/embed/vigilant-http-1r9smi?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="vigilant-http-1r9smi"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>


## Properties

### limit

This prop sets the limit i.e. the number of users that should be fetched in a single iteration.


| Type | Default | 
| ---- | ---- | 
| number | 30 | 


### searchKeyword

This prop sets the search string based on which the users are to be fetched.


| Type | Default | 
| ---- | ---- | 
| string | "" | 


### status

This prop allows you to status based on which the users are to be fetched. It can contain one of the below two values:

- CometChat.USER_STATUS.ONLINE - will return the list of only online users.
- CometChat.USER_STATUS.OFFLINE - will return the list of only offline users.

If this parameter is not set, will return all the available users.


| Type | Default | 
| ---- | ---- | 
| string | "" | 


### friendsOnly

This prop when set to true will return only the friends of the logged-in user.


| Type | Default | 
| ---- | ---- | 
| bool | false | 


### hideBlockedUsers

This prop allows you to determine if the blocked users should be returned as a part of the user list. If set to true, the user list will not contain the users blocked by the logged in user.


| Type | Default | 
| ---- | ---- | 
| bool | true | 


### roles

This prop allows you to fetch the users based on multiple roles.


| Type | Defaul | 
| ---- | ---- | 
| array | [] | 


### tags

This prop accepts a list of tags based on which the list of users is to be fetched. The list fetched will only contain the users that have been tagged with the specified tags.


| Type | Default | 
| ---- | ---- | 
| array | [] | 


### uids

This prop accepts a list of UIDs based on which the list of users is fetched.


| Type | Default | 
| ---- | ---- | 
| array | [] | 


### style

Object containing all the styling properties


| **Type** | **Default** | 
| ---- | ---- | 
| object | `{\n\n\n\n\n\n\n\nwidth: "100%",`\n\n\n\n\n\n\n\n`height: "100%",`\n\n\n\n\n\n\n\n`background: "white",`\n\n\n\n\n\n\n\n`border: "0 none",`\n\n\n\n\n\n\n\n`cornerRadius: "0",`\n\n\n\n\n\n\n\n`loadingIconTint: "",`\n\n\n\n\n\n\n\n`emptyTextFont: "",`\n\n\n\n\n\n\n\n`emptyTextColor: "",`\n\n\n\n\n\n\n\n`errorTextFont: "",`\n\n\n\n\n\n\n\nerrorTextColor: ""\n\n\n\n\n\n\n\n`}` | 


### loadingIconURL

Image URL of the loading icon


| Type | Default | 
| ---- | ---- | 
| string | spinner.svg | 


### customView

Object containing all custom component view for all 3 states of the component i.e. empty, loading and error.


| Type | Default | 
| ---- | ---- | 
| object | {\n\n\n\n\n\n\n\nloading: "",\n\n\n\n\n\n\n\n    empty: "",\n\n\n\n\n\n\n\n    error: "",\n\n\n\n} | 


### emptyText

Text to be displayed during the empty state of the component


| Type | Default | 
| ---- | ---- | 
| string | "No users" | 


### errorText

Text to be displayed when the component encounters an error.


| Type | Default | 
| ---- | ---- | 
| string | Something went wrong | 


### hideError

This prop allows you to show/hide error being displayed in the UI.


| Type | Default | 
| ---- | ---- | 
| bool | false | 


### onErrorCallback

The method invoked when the component encounters an error.


| Type | Default | 
| ---- | ---- | 
| function | () =&gt; {} | 


### activeUser

Selected user's SDK object


| Type | Default | 
| ---- | ---- | 
| object | null | 


