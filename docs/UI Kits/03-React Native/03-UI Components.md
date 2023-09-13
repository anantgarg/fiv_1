
**UI Components** are building blocks of the UI Kit. **UI Components** are a set of custom classes specially designed to build a rich chat app. There are different UI Components available in the
UI Kit Library.

### CometChatUI

**CometChatUI** is an option to launch a fully functional chat application using the UI Kit. In **CometChatUI**  all the **UI Components** are interlinked and work together to launch a fully functional chat on your application.


![CometChatUI](https://res.cloudinary.com/developerhub/image/upload/v1631680500/v2_5163/cxiuyksuijhngtn6shf3.png)



```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatUI} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatUIView() {
  return (
    <View style={{flex: 1}}>
      <CometChatUI _>
    <_View>
  );
}
```




### CometChatUserListWithMessages

The `CometChatUserListWithMessages` is a component with a list of users. The component has all the necessary listeners and methods required to display the user's list and shows the set of the messages/chats of the selected user


![CometChatUserListWithMessages](https://res.cloudinary.com/developerhub/image/upload/v1631680503/v2_5163/bishb0pb1ejkrel8radj.jpg)



```javascript
import { CometChatUserListWithMessages } from '.._cometchat-pro-react-native-ui-kit';

function StackNavigator(props) {
  const Stack = createStackNavigator();

  return (
    <NavigationContainer>
      <Stack.Navigator
        headerMode="none"
        initialRouteName={"UserListWithMessages"}>
          <Stack.Screen name="UserListWithMessages" component={CometChatUserListWithMessages} _>
      <_Stack.Navigator>
    <_NavigationContainer>
  );
}
```




If you want to use this as a child component, then use the below code.


```javascript
import React from 'react';
import {View} from 'react-native';
import {CometChatUserListWithMessages} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatUserListWithMessagesView({navigation}) {
  return (
    <View style={{flex: 1}}>
      <CometChatUserListWithMessages navigation={navigation}_>
    <_View>
  );
}
```




### CometChatGroupListWithMessages

The `CometChatGroupWithMessages` is a component with a list of groups. The component has all the necessary listeners and methods required to display the group's list and shows the set of the messages/chats of the selected group


![CometChatGroupListWithMessages](https://res.cloudinary.com/developerhub/image/upload/v1631680505/v2_5163/izn87ygukdjncmcot3wf.jpg)



```javascript
import { CometChatGroupListWithMessages } from '.._cometchat-pro-react-native-ui-kit';

function StackNavigator(props) {
  const Stack = createStackNavigator();

  return (
    <NavigationContainer>
      <Stack.Navigator
        headerMode="none"
        initialRouteName={"GroupListWithMessages"}>
          <Stack.Screen name="GroupListWithMessages" component={CometChatGroupListWithMessages} _>
      <_Stack.Navigator>
    <_NavigationContainer>
  );
}
```




If you want to use this as a child component, then use the below code.


```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatGroupListWithMessages} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatGroupListWithMessagesView({navigation}) {
  return (
    <View style={{flex: 1}}>
      <CometChatGroupListWithMessages navigation={navigation} _>
    <_View>
  );
}
```




### CometChatMessages

The `CometChatMessages` is a component with a list of messages/chats and shows the message component header and message composer.


![CometChatMessages](https://res.cloudinary.com/developerhub/image/upload/v1631680507/v2_5163/jkdh9mvnfso5tp73hgko.jpg)



```javascript
import React, {useEffect, useState} from 'react';
import {View} from 'react-native';
import {CometChat} from '@cometchat-pro_react-native-chat';
import {CometChatMessages} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatMessagesView({navigation}) {
  const [localUser, setLocalUser] = useState(null);
  useEffect(() => {
    var user = CometChat.getLoggedinUser().then(
      (user) => {
        console.log('user details:', {user});
        setLocalUser(user);
      },
      (error) => {
        console.log('error getting details:', {error});
      },
    );
  }, []);
  return (
    <View style={{flex: 1}}>
      {localUser ? (
        <CometChatMessages
          type={'user'}
          item={userOrGroupObject}__The object will be of user or group depending on type
          loggedInUser={localUser}
          actionGenerated={(actionType) => {
            console.log(actionType);
          }}
        _>
      ) : null}
    <_View>
  );
}
```





| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| type | Value should be _string_.\n\n\n\ndefines the type of chat. Its value can be _user_ or "group". | Optional | 
| item | Value should be _Object_.\n\n\n\nThe object will be of user or group depending on type.\n\n\n\nThis is an example object for user\n\n\n\n{\n\n\n\n            hasBlockedMe: false,\n\n\n\n            blockedByMe: false,\n\n\n\n            uid: 'superhero3',\n\n\n\n            name: 'Spiderman',\n\n\n\n            avatar:\n\n\n\n              '[https://data-us.cometchat.io/assets/images/avatars/spiderman.png'](https://data-us.cometchat.io/assets/images/avatars/spiderman.png'),\n            lastActiveAt: 1614597611,\n\n\n\n            role: 'default',\n\n\n\n            status: 'offline',\n\n\n\n} | Required | 
| loggedInUser | Value should be _Object_.\n\n\n\nThis props takes  the details of current logged in user, | Required | 
| actionGenerated | Value should be _function_.\n\n\n\nTis is a callback function called when user perform certain actions on screen. \n\n\n\nList of actionType are as follow:\n\n\n\n\n\n\n\n1)groupDeleted: This is called when user deletes the group.\n\n\n\n\n\n\n\n2) membersUpdated: This is called when members of group are updated.\n\n\n\n3)messageRead : This is called when last message is read.\n\n\n\n\n\n\n\n4)messageComposed:  is called when new message is composed.\n\n\n\n5)messageDeleted: This is called when message is been deleted.\n\n\n\n6)viewActualImage: This is called when user clicks on Image.\n\n\n\n\n\n\n\n7)menuClicked: This is called when the menu in header has been clicked.\n\n\n\n8)threadMessageComposed: This is called when new thread message has been composed\n\n\n\n\n\n\n\n9)blockUser: This is called when user is blocked\n\n\n\n\n\n\n\n10)updateThreadMessage: This is called when thread message is updated.\n\n\n\n11)messageEdited: This is called when a message is edited.\n\n\n\n\n\n\n\n12)groupUpdated: This is called when a group property has been updated. | Required | 


### CometChatConversationListWithMessages

The `CometChatConversationListWithMessages` is a component with a list of recent conversations. The component has all the necessary listeners and methods required to display the recent conversation list and shows the set of the messages/chats of the selected recent conversation


![CometChatConversationListWithMessages](https://res.cloudinary.com/developerhub/image/upload/v1631680508/v2_5163/qu7gsuuzthyemcd3v584.jpg)



```javascript
import { CometChatConversationListWithMessages } from '.._cometchat-pro-react-native-ui-kit';

function StackNavigator(props) {
  const Stack = createStackNavigator();

  return (
    <NavigationContainer>
      <Stack.Navigator
        headerMode="none"
        initialRouteName={"ConversationListWithMessages"}>
          <Stack.Screen name="ConversationListWithMessages" component={CometChatConversationListWithMessages} _>
      <_Stack.Navigator>
    <_NavigationContainer>
  );
}
```




If you want to use this as a child component, then use the below code.


```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatConversationListWithMessages} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatConversationListWithMessagesView({
  navigation,
}) {
  return (
    <View style={{flex: 1}}>
      <CometChatConversationListWithMessages navigation={navigation} _>
    <_View>
  );
}
```




### CometChatUserList

The `CometChatUserList` is a component that displays the list of users available to chat. You can use this component within your app if you wish to display the list of users.


![CometChatUserList](https://res.cloudinary.com/developerhub/image/upload/v1631680510/v2_5163/kab7mprge9xonsrhpi3l.jpg)



```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatUserList} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatUserListView({navigation}) {
  return (
    <View style={{flex: 1}}>
      <CometChatUserList
        friendsOnly={true}
        onItemClick={(item) => {
          console.log(item);
        }}
        navigation={navigation}
      _>
    <_View>
  );
}
```





| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| friendsOnly | Value could be _Object_  or _Number_\n\n\n\n\n\n\n\nThis property when set to true will return only the friends of the logged-in user\n\n\n\n\nDefault value is _false_ | Optional | 
| onItemClick | Value should be _function_\n\n\n\nThis is a callback called when a user is clicked on user list | Optional | 
| navigation | Value should be _Object_. \n\n\n\nPass the navigation object, if you want to refresh list on focus | Optional | 


### CometChatGroupList

The `CometChatGroupList` is a component that displays the list of groups available. You can use this component within your app if you wish to display the list of groups.


![CometChatGroupList](https://res.cloudinary.com/developerhub/image/upload/v1631680512/v2_5163/rivhieuq1tqf7ppjglxl.jpg)



```javascript
import { CometChatGroupList } from '.._cometchat-pro-react-native-ui-kit';

function StackNavigator(props) {
  const Stack = createStackNavigator();

  return (
    <NavigationContainer>
      <Stack.Navigator
        headerMode="none"
        initialRouteName={"GroupList"}>
          <Stack.Screen name="GroupList" component={CometChatGroupList} _>
      <_Stack.Navigator>
    <_NavigationContainer>
  );
}
```




If you want to use this as a child component, then use the below code.


```javascript
import React from 'react';
import {View} from 'react-native';
import {CometChatGroupList} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatGroupListView({navigation}) {
  return (
    <View style={{flex: 1}}>
      <CometChatGroupList navigation={navigation} _>
    <_View>
  );
}
```




### CometChatConversationList

You can use the `CometChatConversationList` component to display the list of recent conversations that the logged-in user was a part of.


![CometChatConversationList](https://res.cloudinary.com/developerhub/image/upload/v1631680513/v2_5163/qwwvvkmejmhlluzdlmr4.jpg)



```javascript
import { CometChatConversationList } from '.._cometchat-pro-react-native-ui-kit';

function StackNavigator(props) {
  const Stack = createStackNavigator();

  return (
    <NavigationContainer>
      <Stack.Navigator
        headerMode="none"
        initialRouteName={"ConversationList"}>
          <Stack.Screen name="ConversationList" component={CometChatConversationList} _>
      <_Stack.Navigator>
    <_NavigationContainer>
  );
}
```




If you want to use this as a child component, then use the below code.


```javascript
import React from 'react';
import {View} from 'react-native';
import {CometChatConversationList} from '.._cometchat-pro-react-native-ui-kit';

export default function CometChatConversationListView({navigation}) {
  return (
    <View style={{flex: 1}}>
      <CometChatConversationList navigation={navigation} _>
    <_View>
  );
}
```




### CometChatAvatar

This is an image view customize only to display Avatar.


![CometChatAvatar](https://res.cloudinary.com/developerhub/image/upload/v1631680515/v2_5163/r30dcpdz0hh8ege08nne.jpg)



```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatAvatar} from '.._cometchat-pro-react-native-ui-kit';
export default function AvatarView({user}) {
  return (
    <View style={{flex: 1, justifyContent: 'center'}}>
      <View
        style={{
          margin: '10%',
          elevation: 5,
          backgroundColor: '#fff',
          padding: '10%',
          alignItems: 'center',
          borderRadius: 5,
        }}>
        <Text style={{fontWeight: 'bold', fontSize: 26, marginBottom: '5%'}}>
          CometChatAvatar
        <_Text>
        <CometChatAvatar
          image={{uri: user.avatar}}
          borderWidth={5}
          cornerRadius={1000}
          borderColor={'#707070'}
          textColor={'#000'}
        _>
        <Text style={{marginTop: '5%', textAlign: 'center'}}>
          This is an image view customize only to display Avatar.
        <_Text>
      <_View>
    <_View>
  );
}
```





| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| image | Value could be _Object_  or _Number_\n\n\n\nThis property sets the source of avatar image. | Optional | 
| name | Value should be _String_ \n\n\n\nThis property sets the user name in avatar. | Optional | 
| borderWidth | Value should be _Number_.\n\n\n\nThis property sets the width of the component's four borders.\n\n\n\nDefault value is _1_ | Optional | 
| cornerRadius | Value should be _Number_. \n\n\n\nThis property sets border radius of the component.\n\n\n\nDefault value is _1000_. | Optional | 
| textColor | Value should be _Color_.\n\n\n\nThis property sets the text color of component.\n\n\n\nDefault value is *black * | Optional | 


### CometChatUserPresence

This component will be used to show the user's online or offline status. This component will show the color based on the user's status.


![CometChatUserPresence](https://res.cloudinary.com/developerhub/image/upload/v1631680516/v2_5163/tsipvkphdcq7fgd7ylam.gif)



```javascript
import React, {useState} from 'react';
import {View, Text, TouchableOpacity} from 'react-native';
import {CometChatUserPresence} from '.._cometchat-pro-react-native-ui-kit';
export default function CometChatUserPresenceView({user}) {
  const [status, setStatus] = useState(user.status);
  return (
    <View style={{flex: 1, justifyContent: 'center'}}>
      <View
        style={{
          margin: '10%',
          elevation: 5,
          backgroundColor: '#fff',
          padding: '5%',
          alignItems: 'center',
          borderRadius: 5,
        }}>
        <Text style={{fontWeight: 'bold', fontSize: 26, marginBottom: '5%'}}>
          CometChatUserPresence
        <_Text>

        <View
          style={{
            flexDirection: 'row',
            justifyContent: 'space-evenly',
            width: '100%',
          }}>
          <TouchableOpacity
            onPress={() => setStatus('online')}
            style={{
              justifyContent: 'center',
              alignItems: 'center',
              padding: 10,
              backgroundColor: 'lightgreen',
            }}>
            <Text>Online<_Text>
          <_TouchableOpacity>
          <TouchableOpacity
            onPress={() => setStatus('')}
            style={{
              justifyContent: 'center',
              alignItems: 'center',
              padding: 10,
              backgroundColor: '#707070',
            }}>
            <Text>Offline<_Text>
          <_TouchableOpacity>
        <_View>
        <View style={{position: 'relative'}}>
          <CometChatUserPresence
            status={status}
            borderWidth={0.5}
            borderColor={'red'}
            cornerRadius={0}
          _>
        <_View>
        <Text style={{marginTop: '15%', textAlign: 'center'}}>
          This view will be used to show the user status if the user is online
          or offline. This view will take user status and display the color
          accordingly
        <_Text>
      <_View>
    <_View>
  );
}
```





| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| borderWidth | Value should be _Number_ \n\n\n\nThis property sets the width of the component's four borders\n\n\n\nDefault value is _1_ | Optional | 
| borderColor | Value should be _Color_ \n\n\n\nThis property sets the border colour of the component.\n\n\n\nDefault value is *#AAA * | Optional | 
| cornerRadius | Value should be _Number_. \n\n\n\nThis property sets border radius of the component  Default value is _4.5_ | Optional | 
| status | Value should be _String_\n\n\n\nTakes the status of _user_ | Optional | 


### CometChatBadgeCount

The CometChatBadgeCount component can be used to show an unread count. You can use it in different scenarios according to their use case.


![CometChatBadgeCount](https://res.cloudinary.com/developerhub/image/upload/v1631680521/v2_5163/tanb4htqlrk68th2pb3g.jpg)



```javascript
import React from 'react';
import {View, Text} from 'react-native';
import {CometChatBadgeCount} from '.._cometchat-pro-react-native-ui-kit';
export default function CometChatBadgeCountView() {
  return (
    <View style={{flex: 1, justifyContent: 'center'}}>
      <View
        style={{
          margin: '5%',
          elevation: 5,
          backgroundColor: '#fff',
          padding: '10%',
          alignItems: 'center',
          borderRadius: 5,
        }}>
        <Text style={{fontWeight: 'bold', fontSize: 26, marginBottom: '5%'}}>
          CometChatBadgeCount
        <_Text>
        <View>
          <CometChatBadgeCount count={1} _>
        <_View>
        <Text style={{marginTop: '5%', textAlign: 'center'}}>
          The CometChatBadgeCount component can be used to show an unread count.
          You can use it in different scenarios according to their use case.
        <_Text>
      <_View>
    <_View>
  );
}
```





| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| count | Value should be _String_. \n\n\n\nThis property sets the count on the badge | Optional | 


