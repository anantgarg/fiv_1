The `MessagesRequest` class as you must be familiar with helps you to fetch messages based on the various parameters provided to it. This document will help you understand better the various options that are available using the `MessagesRequest` class.

The `MessagesRequest` class is designed using the `Builder design pattern`. In order to obtain an object of the `MessagesRequest` class, you will have to make use of the `MessagesRequestBuilder` class in the `MessagesRequest` class.

The `MessagesRequestBuilder` class allows you to set various parameters to the `MessagesRequest` class based on which the messages are fetched.

Steps to generate an object of the MessagesRequest class:

1. Create an object of the `MessagesRequestBuilder` class.
2. Set all the parameters you wish to set.
3. Call the `build()` method of the `MessagesRequestBuilder` class to get an object of the `MessagesRequest` class.

Once you have an object of the `MessagesRequest` class, you can call either the `fetchNext()` method or the `fetchPrevious()` method using the object.

1. fetchNext() - Calling this method will return the messages after the specified parameters.
2. fetchPrevious() - Calling this method will give you messages before the specified parameters.

Since messages are obtained in a paginated manner, a maximum of 100 messages can be pulled in a single iteration. Calling the `fetchPrevious()`/`fetchNext()` method on the same `MessagesRequest` object will get you the next set of messages.

Now that you are clear how to use the `MessagesRequest` class, below are the various options available:

## Number of messages fetched

_In other words, how do I set the number of messages fetched in a single iteration_

To achieve this, you can use the `setLimit()` method. This method takes an integer value as the input and informs the SDK to fetch the specified number of messages in one iteration. The maximum number of messages that can be fetched in one go is 100. If this method is not used and the limit is not set, the default value is 30 and thus 30 messages will be fetched in one iteration.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



## Messages for a user conversation

_In other words, how do I fetch messages between me and any user_

This can be achieved using the `setUID()` method. This method takes the UID of the user with whom the conversation is to be fetched. When a valid UID is passed, the SDK will return all the messages that are a part of the conversation between the logged-in user and the UID that has been specified.

```java
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setUID("superhero1")
  .setLimit(50)
  .build();
```

```kotlin
val messagesRequest = MessagesRequestBuilder()
    .setUID("superhero1")
    .setLimit(50)
    .build()
```



## Messages for a group conversation

_In other words, how do I fetch messages for any group conversation_

You can achieve this using the `setGUID()` method. This method takes the GUID of a group for which the conversations are to be fetched. Passing a valid GUID to this method will return all the messages that are a part of the group conversation. Please note that the logged-in user must be a member of the group to fetch the messages for that group.

```java
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setGUID("supergroup")
  .setLimit(50)
  .build();
```

```kotlin
val messagesRequest = MessagesRequestBuilder()
    .setGUID("supergroup")
    .setLimit(50)
    .build()
```



## Messages before/after a message

_In other words, how do I fetch messages before or after a particular message_

This can be achieved using the `setMessageId()` method. This method takes the message-id as input and provides messages only after/before the message-id based on if the fetchNext() or fetchPrevious() method is triggered.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setMessageId(100)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setMessageId(100)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setMessageId(100)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setMessageId(100)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



This method can be used along with `setUID()` or `setGUID()` methods to fetch messages after/before any specific message-id for a particular user/group conversation.

## Messages before/after a given time

_In other words, how do I fetch messages before or after a particular date or time_

You can easily achieve this using the `setTimestamp()` method. This method takes the Unix timestamp as input and provides messages only after/before the timestamp based on if fetchNext() or fetchPrevious() method is triggered.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setTimestamp(1512687363)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setTimestamp(1512687363)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setTimestamp(1512687363)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setTimestamp(1512687363)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



This method can be used along with `setUID()` or `setGUID()` methods to fetch messages after/before any specific date or time for a particular user/group conversation.

## Unread messages

_In other words, how do I fetch unread messages_

This can easily be achieved using setting the unread flag to true. For this, you need to use the `setUnread()` method. This method takes a boolean value as input. If the value is set to true, the SDK will return just the unread messages.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUnread(true)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUnread(true)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setUnread(true)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setUnread(true)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



This method along with `setGUID()` or `setUID()` can be used to fetch unread messages for a particular group or user conversation respectively.

## Exclude messages from blocked users

_In other words, how do I fetch messages excluding the messages from the users I have blocked_

This can be easily achieved using the`hideMessagesFromBlockedUsers()` method. This method accepts a boolean value which determines if the messages from users blocked by the logged-in user need to be a part if the fetched messages. If the value is set to true, the messages will be hidden and won't be a part of the messages fetched. The default value is false i.e if this method is not used, the messages from blocked users will be included in the fetched messages.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.hideMessagesFromBlockedUsers(true)
  .setUID(UID)
  .setLimit(50)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.hideMessagesFromBlockedUsers(true)
  .setGUID(GUID)
  .setLimit(50)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .hideMessagesFromBlockedUsers(true)
    .setUID(UID)
    .setLimit(50)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .hideMessagesFromBlockedUsers(true)
    .setGUID(GUID)
    .setLimit(50)
    .build()
```



This method can be used to hide the messages by users blocked by logged in user in groups that both the members are a part of.

## Updated and received messages

_In other words, how do I fetch messages that have been received or updated after a particular date or time_

This method accepts a Unix timestamp value and will return all the messages that have been updated and the ones that have been sent/received after the specified time. The messages updated could mean the messages that have been marked as read/delivered or if the messages are edited or deleted.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUpdatedAfter(1514321321)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUpdatedAfter(1514321321)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setUpdatedAfter(1514321321)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setUpdatedAfter(1514321321)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



This can be useful in finding the messages that have been received or updated after a certain time. Can prove very useful if you are saving the messages locally and would like to know the messages that have been updated or received after the last message available in your local databases.

## Updated messages only

_In other words, how do I fetch messages that have been updated after a particular date or time_

This can be achieved easily by setting the updatesOnly parameter to true. To do so, you can use the updatesOnly() method. This method takes a boolean input and can be used with the `setUpdatedAfter()` method to get jus the updated messages and not the messages sent/received after the specified time. This method cannot be used independently and always needs to be used with the `setUpdatedAfter()` method.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUpdatedAfter(1514321321)
  .updatesOnly(true)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setUpdatedAfter(1514321321)
  .updatesOnly(true)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
    .setUpdatedAfter(1514321321)
    .updatesOnly(true)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setUpdatedAfter(1514321321)
    .updatesOnly(true)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



## Messages for multiple categories

_In other words, how do I fetch messages belonging to multiple categories_

We recommend before trying this, you refer to the [Message structure and hierarchy guide](https://www.cometchat.com/docs/v3/more/overview-message-structure-and-hierarchy) to get familiar with the various categories of messages.

For this, you will have to use the `setCategories()` method. This method accepts a list of categories. This tells the SDK to fetch messages only belonging to these categories.

```java
String GUID = "supergroup";
List<String> categories = new ArrayList<>();
categories.add("message");
categories.add("custom");
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setCategories(categories)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```java
String GUID = "supergroup";
List<String> categories = new ArrayList<>();
categories.add("message");
categories.add("custom");
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setCategories(categories)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"
val categories: MutableList<String> = ArrayList()
categories.add("message")
categories.add("custom")
val messagesRequest = MessagesRequestBuilder()
    .setCategories(categories)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"
val categories: MutableList<String> = ArrayList()
categories.add("message")
categories.add("custom")
val messagesRequest = MessagesRequestBuilder()
    .setCategories(categories)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



The above snippet will help you get only the messages belonging to the `message` and `custom` category. This can also be used to disable certain categories of messages like `call` and `action`. This along with `setGUID()` and `setUID()` can help display only the messages you wish to display avoiding the other category of messages.

## Messages for multiple types

_In other words, how do I fetch messages belonging to multiple types_

We recommend before trying this, you refer to the [Message structure and hierarchy guide](https://www.cometchat.com/docs/v3/more/overview-message-structure-and-hierarchy) to get familiar with the various types of messages.

This can be easily achieved using the `setTypes()` method. This method accepts a list of types. This tells the SDK to fetch messages only belonging to these types.

```java
String UID = "superhero1";
List<String> categories = new ArrayList<>();
categories.add("message");
List<String> types = new ArrayList<>();
types.add("image");
types.add("video");
types.add("audio");
types.add("file");
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setCategories(categories)
  .setTypes(types)
  .setLimit(50)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";
List<String> categories = new ArrayList<>();
categories.add("message");
List<String> types = new ArrayList<>();
types.add("image");
types.add("video");
types.add("audio");
types.add("file");
MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
	.setCategories(categories)
  .setTypes(types)
  .setLimit(50)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"
val categories: MutableList<String> = ArrayList()
categories.add("message")
val types: MutableList<String> = ArrayList()
types.add("image")
types.add("video")
types.add("audio")
types.add("file")
val messagesRequest = MessagesRequestBuilder()
    .setCategories(categories)
    .setTypes(types)
    .setLimit(50)
    .setUID(UID)
    .build()
```

```kotlin
val GUID = "supergroup"
val categories: MutableList<String> = ArrayList()
categories.add("message")
val types: MutableList<String> = ArrayList()
types.add("image")
types.add("video")
types.add("audio")
types.add("file")
val messagesRequest = MessagesRequestBuilder()
    .setCategories(categories)
    .setTypes(types)
    .setLimit(50)
    .setGUID(GUID)
    .build()
```



Using the above code snippet, you can fetch all the media messages. This along with setUID() or setGUID() can be used to fetch media messages for any particular conversation. This can be useful in many other scenarios as well.

## Messages for a specific thread

_In other words, how do I fetch messages that are a part of a thread and not directly a user/group conversations_

This can be done using the `setParentMessageId()` method. This method needs to be used when you have implemented threaded conversations in your app. This method will return the messages only belonging to the thread with the specified parent Id.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .setParentMessageId(100)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setGUID(GUID)
  .setParentMessageId(100)
  .build();
```

```kotlin
val UID = "superhero1"
val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .setParentMessageId(100)
  .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .setGUID(GUID)
  .setParentMessageId(100)
  .build()
```



The above code snippet returns the messages that belong to the thread with parent id 100.

## Hide threaded messages in user/group conversations

_In other words, how do I exclude threaded messages from the normal user/group conversations_

In order to do this, you can use the `hideReplies()` method. This method is also related to threaded conversations. This method takes boolean as input. This boolean when set to true will make sure that the messages that belong to threads are not fetched. If set to false, which is also the default value, the messages belong to the threads will also be fetched along with other messages.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
	.hideReplies(true)
  .setUID(UID)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
	.hideReplies(true)
  .setGUID(GUID)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .hideReplies(true)
  .setUID(UID)
  .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .hideReplies(true)
  .setGUID(GUID)
  .build()
```



## Hide deleted messages in user/group conversations

_In other words, how do I exclude deleted messages a user/group conversations_

In order to do this, you can use the hideDeletedMessages() method. This method takes boolean as input. This boolean when set to true will make sure that the deleted messages are not fetched. If set to false, which is also the default value, the deleted messages will also be fetched along with other messages.

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
	.hideDeletedMessages(true)
  .build();
```

```java
String GUID = "supergroup";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setGUID(GUID)
	.hideDeletedMessages(true)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .hideDeletedMessages(true)
  .build()
```

```kotlin
val GUID = "supergroup"

val messagesRequest = MessagesRequestBuilder()
    .setLimit(50)
    .setGUID(GUID)
    .hideDeletedMessages(true)
    .build()
```



## Messages by tags

_In other words, how do I fetch messages belonging to specific tags_

In order to do this, you can use the `setTags()` method. This method accepts a list of tags. This tells the SDK to fetch messages only belonging to these tags.

```java
String UID = "superhero1";
List<String> tags = new ArrayList<>();
tags.add("pinned");

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
	.setTags(tags)
  .build();
```

```kotlin
val UID = "superhero1"
val tags: MutableList<String> = ArrayList()
tags.add("pinned")

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .setTags(tags)
  .build()
```



## Messages with tags

_In other words, how do I fetch messages with the tags information_

In order to do this, you can use the `withTags()` method. This method accepts boolean as input. When set to `true` , the SDK will fetch messages along with the tags information. When set to `false` , the SDK will not fetch tags information associated with messages. The default value for this parameter is `false` .

```java
String UID = "superhero1";

MessagesRequest messagesRequest = new MessagesRequest.MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
	.withTags(true)
  .build();
```

```kotlin
val UID = "superhero1"

val messagesRequest = MessagesRequestBuilder()
  .setLimit(50)
  .setUID(UID)
  .withTags(true)
  .build()
```

