Customize the UI Kit with your theme. You can change the colors, the typography much more.

Themes let you apply a consistent tone to your app. It allows you to **customize all design aspects** of your app in order to meet the specific needs of your business or brand.

To promote greater consistency between apps, light and dark theme types are available to choose from. By default, components use the light theme type.

## withCometChatTheme 

If you wish to customize the theme, you need to use the `withCometChatTheme` HOC component in order to inject a theme into your application. However, this is optional; the components come with a default theme.

`withCometChatTheme` relies on the [higher-order component feature of React](https://reactjs.org/docs/higher-order-components.html) to pass the theme down to the components.

## Theme configuration variables

Changing the theme configuration variables is the most effective way to match UI kit to your needs. The following sections cover the most important theme variables:

1. Palette
2. Typography

### Palette

The palette enables you to modify the color of the components to suit your brand.

#### Palette colors

The theme exposes the following palette colors:

- _primary_ - used to represent primary interface elements for a user. It's the color displayed most frequently across your app's screens and components.
- _accent_ - used to represent secondary interface elements for a user. It provides more ways to accent and distinguish your product. 
- _error_ - used to represent interface elements that the user should be made aware of.

#### Default values

#### Customization

You may override the default palette values by including a palette object as part of your theme. If any of the:

- `primary`
- `accent`
- `error`

palette color objects are provided, they will replace the default ones.

If you wish to provide more customized colors, you can either create your own palette color, or directly supply colors to some or all of the `theme.palette` keys:

```javascript
const theme = {
  palette: {
    primary: "#39f",
    accent: "#!41414",
    error: "#FF3B30"
  }
}
```



### Dark mode

CometChatTheme comes with two palette modes: light (the default) and dark.

You can make the theme dark by setting `mode: 'dark'`.

```javascript
const theme = {
  mode: "dark"
}
```



### Typography

The theme provides a set of type sizes that work well together, and also with the layout grid.

#### Font family

You can change the font family with the `theme.typography.fontFamily` property.

For instance, this example uses the system font instead of the default Inter font:

```javascript
const theme = {
  typography: {
    fontFamily: [
      '-apple-system',
      'BlinkMacSystemFont',
      '"Segoe UI"',
      'Roboto',
      '"Helvetica Neue"',
      'Arial',
      'sans-serif',
      '"Apple Color Emoji"',
      '"Segoe UI Emoji"',
      '"Segoe UI Symbol"',
    ].join(','),
  },
}
```

