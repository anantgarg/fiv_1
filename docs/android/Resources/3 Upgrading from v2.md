Upgrading from v2.x to v3 is fairly simple. Below are the major changes that are released as a part of CometChat Pro v3:

Please follow the [setup](https://www.cometchat.com/docs/v3/android-chat-sdk/setup) instructions to upgrade to the latest V3 version.

> v3 apps are compatible only with v3.x SDKs and will not function with v2.x SDKs. In case you want to migrate an existing v2 app to v3, you can achieve this from the [CometChat Dashboard](https://app.cometchat.com/).

## Delivery Receipts

In v2.x, the messages were being marked as delivered internally by the SDKs. Starting v3, we have stopped marking the messages as delivered internally and it will have to be managed via the SDK.

You can read more about the `markAsDelivered()` method [here](https://www.cometchat.com/docs/v3/android-chat-sdk/messaging-receipts#mark-messages-as-delivered).

## Read Receipts

Starting v3.0, the method signature has been changed. Now the `markAsRead()` takes 4 parameters: `messageId`,`receiverId`, `receiverType` & `senderId` as input. This method will mark all the messages before the provided messageId for the conversation with the specified `receiverId` as read. Also, we have added one more signature of `markAsRead()` which takes only 1 parameter: `message`

You can read more about the `markAsRead()` method [here](https://www.cometchat.com/docs/v3/android-chat-sdk/messaging-receipts#mark-messages-as-read).

```java
__v2.x

CometChat.markAsRead(messageId, receiverId, receiverType);

__v3.x

CometChat.markAsRead(messageId, receiverId, receiverType, senderId);
__ OR
CometChat.markAsRead(message);
```



## User/Group Tags in Conversation

In v2.x, the user/group tags were by default fetched in a `Conversation` Object while fetching the `Conversation List`.

Starting v3, we have added a method `withUserAndGroupTags()` to the ConversationsRequestBuilder class to fetch the user/group tags in a `Conversation` Object while fetching the `Conversation List`.

```java
ConversationsReqquest conversationsRequest = new ConversationsRequest.ConversationsRequestBuilder()
  .setLimit(10)
  .withUserAndGroupTags()
  .build();
```

