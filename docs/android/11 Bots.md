Bots are special users, in CometChat, who can send and receive messages autonomously. Users can text bots privately in one-on-one conversations as well as in groups. When a bot receives a message, either in a one-on-one conversation or in a group conversation, CometChat forwards the message to a Callback URL that you specify. Once you receive this message, you can send a reply using our API.

## The flow

### Create a user

CometChat requires you to connect every bot to a user. This has one major advantage- at any time, you can log in as that bot user and send out personalized replies. So before you create a bot, you must first create a new user.

### Create the bot

Once you've created a user, you can create a new bot. The actual implementation of the bot is entirely up to you. You simply need to specify a `Callback URL` and CometChat will automatically start forwarding all messages that fit the criteria to the URL.

### Bot Payload

The sample bot payload looks like:

```javascript
{
  "trigger": "after_message",
  "data": {
    "id": "712",
    "conversationId": "superhero1_user_superhero2",
    "sender": "superhero1",
    "receiverType": "user",
    "receiver": "superhero2",
    "category": "message",
    "type": "text",
    "data": {
      "text": "hi",
      "resource": "WEB-3_0_11-055bb47a-7b1f-417b-8385-9d31e606da2a-1680119041609",
      "entities": {
        "sender": {
          "entity": {
            "uid": "superhero1",
            "name": "Iron Man",
            "avatar": "https:__data-eu.cometchat.io_assets_images_avatars_ironman.png",
            "status": "available",
            "role": "default",
            "lastActiveAt": 1675773639
          },
          "entityType": "user"
        },
        "receiver": {
          "entity": {
            "uid": "superhero2",
            "name": "Captain America",
            "avatar": "https:__data-eu.cometchat.io_assets_images_avatars_captainamerica.png",
            "status": "offline",
            "role": "default",
            "lastActiveAt": 1680124695,
            "conversationId": "superhero1_user_superhero2"
          },
          "entityType": "user"
        }
      }
    },
    "sentAt": 1680125130,
    "updatedAt": 1680125130
  },
  "appId": "2248348660ad9bd4",
  "origin": {
    "platform": "web",
    "language": "reactjs",
    "resource": "chat-widget"
  },
  "chatAPIVersion": "3.0",
  "region": "eu",
  "bot": "demo_bot"
}
```



### Reply to a message

When you receive a message from CometChat, you can process it and provide a response using our [Send Bot Message](https://prodocs.cometchat.com/reference#send-bot-message) Rest API.