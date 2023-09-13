`CometChatSoundManager` class lets you play and pause notification sound for incoming/outgoing messages and calls. 

---

## Methods

**Play Sound**

This method is used for playing the sound for a particular state as mentioned in the enum cases.

This method is also capable of playing custom sounds by using **`customSound`** parameter. If this parameter is **`null`** then it will play the default sound.

| Method | Description | 
| ---- | ---- | 
| `play(sound: Sound, customSound: URL?)` | This method plays different types of sounds for incoming/outgoing calls and messages. Additionally, it is capable of playing a custom sound for any particular URL provided while triggering it. | 


**Pause Sound**

This method will pause currently playing sound.

| Method | Description | 
| ---- | ---- | 
| `pause()` | This method will pause currently playing sound. | 


---

## Uses

```javascript
__ Play sound:
CometChatSoundManager().play(CometChatSoundManager.Sound.incomingMessage)

__ Play sound with custom sound:
CometChatSoundManager().play(CometChatSoundManager.Sound.incomingMessage, customSoundURL)

__Pause Sound:
CometChatSoundManager().pause()
```



---