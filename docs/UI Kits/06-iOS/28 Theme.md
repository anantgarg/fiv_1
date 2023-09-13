Theme class provides endless number of customisations to improve or transform the look and feel of the UI Kit as per your application need. 

`CometChatTheme`  class is made up of two primary components such as: 

1. **Palette**
2. **Typography**

User can modify the properties of palette and typography which is going to transform the application.

> CometChatTheme class  should be initialized before launch any component from the UI Kit Workspace.

---

## Palette

`Palette` is nothing but the range of colours used by a UIKit workspace in a various places in a different shades of it.

Palette primarily takes four colors and then UI Kit uses different shades of those color to maintain integrity  and consistency across the components. 

| Color | Description | 
| ---- | ---- | 
| background | This color is used for the back drop in each component across UI Kit | 
| primary | This color is used for the primary components/actions in components across UI Kit | 
| error | This color is used for the destructive components/actions in components across UI Kit | 
| accent | This color is used for the secondary components/actions in components across UI Kit | 
| accent50 to accent900 | This color is used for the secondary components/actions with a shades of same color manages by the alpha varient(opacity of the color) in components across UI Kit | 


## Methods

User can modify the above colors from the palette using below methods.

| Method | Description | 
| ---- | ---- | 
| set(primary: UIColor) | This method will override the color used for primary color set | 
| set(background: UIColor) | This method will override the color used for background  color set | 
| set(error: UIColor) | This method will override the color used for error  color set | 
| set(accent: UIColor) | This method will override the color used for accent  color set | 


## Uses

To modify the palette user has to firstly create an instance of palette. 

```swift
var palette = Palette()
```



After creating a instance user can update the values of colors as shown below:

```swift
palette.set(primary: .white)
 palette.set(background: .darkGray)
 palette.set(accent: .white)
 palette.set(error: .red)
```



> By default, UI Kit will be support in both light and dark mode. > > If you wish to set the whole app always in the dark mode then you can set it in the application class such as AppDelegate or SceneDelegate using below code snippet.> > `window?.overrideUserInterfaceStyle = .dark`

---

## Typography

`Typography` mainly consist of different sets of fonts used in UI Kit across components.  By default, UI Kit uses system font. 

User can set custom font as well using `Typography` class.

| Font | Description | 
| ---- | ---- | 
| Heading | This font takes the size of **34** with a **bold** weight | 
| Name1 | This font takes the size of **20** with a **medium** weight | 
| Name2 | This font takes the size of **17** with a **medium** weight | 
| Title1 | This font takes the size of **22** with a **regular** weight | 
| Title2 | This font takes the size of **17** with a **semibold** weight | 
| Subtitle1 | This font takes the size of **15** with a **regular** weight | 
| Subtitle2 | This font takes the size of **13** with a **regular** weight | 
| Caption1 | This font takes the size of **13** with a **medium** weight | 
| Caption2 | This font takes the size of **11** with a **medium** weight | 


## Methods

User can modify the above fonts from the typography using below methods.

| Method | Description | 
| ---- | ---- | 
| setFont(heading: UIFont) | This method will override the font for heading | 
| setFont(name1: UIFont) | This method will override the font for name1 | 
| setFont(name2: UIFont) | This method will override the font for name2 | 
| setFont(title1: UIFont) | This method will override the font for title1 | 
| setFont(title2: UIFont) | This method will override the font for title2 | 
| setFont(subtitle1: UIFont) | This method will override the font for subtitle1 | 
| setFont(subtitle2: UIFont) | This method will override the font for subtitle2 | 
| setFont(caption1: UIFont) | This method will override the font for caption1 | 
| setFont(caption2: UIFont) | This method will override the font for caption2 | 
| overrideFont(family: CometChatFontFamily) | This method can override the system font with the other font family. | 


## Uses

To modify the palette user has to firstly create an instance of Typography. 

```swift
var typography = Typography()
```



After creating a instance user can update the values of fonts as shown below:

```swift
typography.setFont(heading: UIFont("Your font here", size: 40))
typography.setFont(name1: UIFont("Your font here", size: 22))
typography.setFont(caption1: UIFont("Your font here", size: 15))
```



User can also update the font family using below snippet. 

```swift
let family = CometChatFontFamily(regular: "Your font here with regular size", medium: "Your font here with medium size", bold: "Your font here with bold size")

typography.overrideFont(family: family)
```



---

After creation of both Palette and typography class, user can initialize the theme class. 

```swift
CometChatTheme.init(typography: typography, palatte: palette)
```



If user wish to set the default  appearance then you can use below method. 

```swift
CometChatTheme.defaultAppearance()
```



At the end your application class will look like this:

```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions:      [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
      
     __ Creating Palette
     var palette = Palette()
     palette.set(primary: .white)
     palette.set(background: .purple)
     palette.set(accent: .white)
   
   __ Creating Typography
    var typography = Typography()
    typography.setFont(heading: UIFont("CourierNewPSMT", size: 40))
    typography.setFont(name1: UIFont("CourierNewPSMT", size: 22))
    typography.setFont(caption1: UIFont("CourierNewPSMT", size: 15))
   
   __ If the user wants to override the whole font family
    let fontFamily = CometChatFontFamily(regular: "CourierNewPSMT", medium: "CourierNewPS-BoldMT", bold:    "CourierNewPS-BoldMT")
   typography.overrideFont(family: family)
   
   __ Initializing Theme
   CometChatTheme.init(typography: typography, palatte: palette)
   
    }
```

