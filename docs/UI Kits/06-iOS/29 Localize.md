With language localization, our UI Kit adapts to the language of a specific country or region.  `CometChatLocalize` allows you to detect the language of your users based on their browser or device settings and set the language accordingly.

`CometChatLocalize` is a class that includes methods related to locale. Developers can use these methods to change the language of UI Kit lIbrary.

Currently, we support  the following languages for localization:

- **English (en, en-US, en-GB)**
- **Chinese (zh, zh-TW)**
- **Spanish (es)**
- **Hindi (hi)**
- **Russian (ru)**
- **Arabic (ar)**
- **Portuguese (pt)**
- **Malay (ms)**
- **French (fr)**
- **German (de)**
- **Swedish (sv)**
- **Lithuanian (lt)**
- **Hungarian (hu)**

---

## Methods

**Set Language**

This method is used for setting the language in for UI Kit.

| Method | Description | 
| ---- | ---- | 
| `set(locale: Language)` | Used for setting the language in for UI Kit. It takes the enum value from Language enum and will sets the value accordingly. | 


## **Get Language**

This method is used to get the current language for **`CometChatLocalize`**. By default, it will be a current language from the device/browser.

---

## Uses

```swift
__ Set Language
CometChatLocalize().set(locale: .french)

__ Get Language
CometChatLocalize().getLocale()
```



---

## Replace Text

To replace or change the **particular text, word,** or **phrase in UI Kit.**

1. Please visit the **`Localizable.strings`** file.
2. Search for the Text or a phrase and replace it in the localization file.

---

## Add New Language

1. To add a new language, add a new file **`Localizable.strings`** file with the language extension.
2. Copy-paste the English localization file and add localization for the keywords particular language.

---