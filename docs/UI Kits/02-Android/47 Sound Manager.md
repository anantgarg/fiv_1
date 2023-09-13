**`CometChatSoundManager`** is responsible for playing different types of audio which is required for incoming and outgoing events in UI Kit. It plays audio for incoming and outgoing messages as well as calls.

You need to initialize the `CometChatSoundManager` before you can use its object to call the following methods.

```java
CometChatSoundManager soundManager = new CometChatSoundManager(context)
```



## Methods

Play Sound

This method is used for playing the sound for a particular state as mentioned in the enum cases.

This method is also capable of playing in-built sounds or custom sounds by passing a raw file as parameter mentioned in the method. If this parameter is `0`, it will play the default sound. Otherwise it will play the custom sound from the provided raw file.

| **Method** | **Description** | 
| ---- | ---- | 
| **play(Sound sound)** | This method plays different types of sounds for incoming outgoing calls and messages. | 
| **play(Sound sound,int res)** | This method pauses different types of sounds for incoming outgoing calls and messages. This method capable of playing the custom sound for that particular raw file passed in this method. | 


Pause Sound

This method pauses different types of sounds for incoming outgoing calls and messages.

| **Method** | **Description** | 
| ---- | ---- | 
| **pause()** | This method pause different types of sounds for incoming outgoing calls and messages. | 


### Uses

```java
__ Initialize SoundManager
CometChatSoundManager soundManager = new CometChatSoundManager(context)

__ Play sound with default sound:
soundManager.play(Sound.incomingCall) __To play incoming call sound
soundManager.play(Sound.outgoingCall) __To play outgoing call sound
soundManager.play(Sound.incomingMessage) __To play incoming message sound
soundManager.play(Sound.outgoingMessage) __To play outgoing message sound

__Play sound with custom sound
soundManager.play(Sound.incomingCall,R.raw.incoming_call) __To play incoming call sound
soundManager.play(Sound.outgoingCall,R.raw.outgoing_call) __To play outgoing call sound
soundManager.play(Sound.incomingMessage,R.raw.incoming_message) __To play incoming message sound
soundManager.play(Sound.outgoingMessage,R.raw.outgoing_message) __To play outgoing message sound

__Pause Sound:
soundManager.pause()
```

