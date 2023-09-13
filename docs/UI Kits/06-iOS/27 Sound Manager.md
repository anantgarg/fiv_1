`CometChatSoundManager` is responsible for playing different types of audio which is required for incoming & outgoing events in the UI Kit.  This class plays the audio for incoming & outgoing messages and calls.

---

## Methods

**Play Sound**

This method is used for playing the sound for a particular state as mentioned in the enum cases.

This method is also capable of playing custom sounds by using **`customSound`** parameter mentioned in the method. If this parameter is **`nil`** then it will play the default sound otherwise it will play the custom sound for which the URL is being provided.

| Method | Description | 
| ---- | ---- | 
| `play(sound: Sound, customSound: URL?)` | This method plays different types of sounds for incoming outgoing calls and messages. Additionally, it is capable of playing a custom sound for any particular URL provided while triggering it. | 


**Pause Sound**

This method can help you pause different types of sounds for incoming or outgoing calls and messages.

| Method | Description | 
| ---- | ---- | 
| `pause()` | This method pauses different types of sounds for incoming outgoing calls and messages | 


---

## Uses

```swift
__ Play sound:
CometChatSoundManager().play(sound: .incomingMessage)

__ Play sound with custom sound:
if let customSoundURL = Bundle.main.url(forResource: "customSound", withExtension: "wav") {
   CometChatSoundManager().play(sound: .incomingMessage, customSound: customSoundURL)
}

__Pause Sound:
CometChatSoundManager().pause()
```



---