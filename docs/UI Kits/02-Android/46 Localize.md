Our UI Kit supports language localization to adapt to the language of a specific country or region.  **`CometChatLocalize`** allows you to detect the language of your users based on their browser or device settings and set the language accordingly.

`CometChatLocalize` is a class that includes methods related to locale. Developers can use these methods to change the language of UI Kit lIbrary.

Currently, we support 12 languages for localization. They are as follows:

- **English (en, en-US, en-GB)**
- **Chinese (zh, zh-TW)**
- **Spanish (es)**
- **Hindi (hi)**
- **Russian (ru)**
- **Portuguese (pt)**
- **Malay (ms)**
- **French (fr)**
- **German (de)**
- **Swedish (sv)**
- **Lithuanian (lt)**
- **Hungarian (hu)**

---

## Methods

| **Method** | **Description** | 
| ---- | ---- | 
| `setLocale(Activity activity, @Language.Code String language)` | This method is used for setting the language in for UI Kit. This will take the constant value from the Language and will set the value accordingly. | 
| `getLocale()` | This method is used to get the current language. By default, it will return current language from device/browser. | 


## Uses

```java
CometChatLocalize.setLocale(getActivity(), Language.Code.hi);

String currentLanguage = CometChatLocalize.getLocale();
```

