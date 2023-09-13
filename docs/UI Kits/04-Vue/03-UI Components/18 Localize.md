
With language localization, our UI Kit adapts to the language of a specific country or region.  `CometChatLocalize` allows you to detect the language of your users based on their browser or device settings and set the language accordingly.

Currently, we support  12 languages for localization, they are as follows:

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

This method is used for setting the current language in for UI Kit.


| Method | Description | 
| ---- | ---- | 
| `setLocale` | Used for setting the current language in for UI Kit. It takes the enum value from Language enum and sets the value accordingly. | 



## **Get Language**

This method is used to get the current language for **`CometChatLocalize`**. By default, it will be a current language from the device/browser.

---

## Uses


```javascript
__ Set Language
CometChatLocalize.setLocale("fr")

__ Get Language
CometChatLocalize.getLocale()
```




---

## Replace Text

To replace or change the **particular text, word,** or **phrase in UI Kit.**

## Add New Language

Add new language support


```javascript
let resources = {
        en: {
            "PARAGRAPH": "Cometchat is a powerful internationalization framework ",
            "CHATS": "Recent Chats",
        },
        es: {
            "PARAGRAPH": "Cometchat es un poderoso marco de internacionalización",
            "CHATS": "chats recientes"
        },
};

CometChatLocalize.init({
    lang: "es",
    resources: resources
});
```




