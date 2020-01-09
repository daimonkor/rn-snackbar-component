# React Native SnackBar (rn-snackbar)
A snackbar component for Android and iOS, customizable and simple.

![Snackbar demo](https://media.giphy.com/media/zChTSWog7TNmM/giphy.gif)
![With fab](https://media.giphy.com/media/6oCCk98unakbC/giphy.gif)

See [Google Material Design](https://material.io/guidelines/components/snackbars-toasts.html) for more info on Snackbars.

## Installation

```sh
npm install --save rn-snackbar
```

## Basic Usage

```javascript
import SnackBar from 'rn-snackbar'
```

## Code

### Simple

```html
    <SnackBar
      visible={true}
      message="Hello There!"
      actionHandler={() => {
        console.log("snackbar button clicked!")
      }}
      action="let's go"
    />
```

### Advanced
```html
    <SnackBar
      visible={true}
      message={(
         <View style={{ flex: 1, flexDirection: 'column'}}>
           <Text>{title}</Text>
           <TouchableOpacity activeOpacity={0.5} onPress={doSomething}>
             <Text>{subtitle}</Text>
           </TouchableOpacity>
         </View>
      )}
      actionHandler={() => {
        console.log("snackbar button clicked!")
      }}
      action={(
        <Icon name="close" size={20} />
      )}
      autoHidingTime={0}
    />
```

## Options
| Prop        | Type           | Effect  | Default Value |
| ------------- |-------------| -----| -----|
| visible | boolean | Show or hide the snackbar | none |
| message | string / element | The main message text / your custom component | none |
| actionHandler | function | Function to be called when button is pressed, if absent no action button is shown | none |
| action | string / element | The text of action button, will be uppercased automatically / your custom component | none |
| containerStyle | object | The styling of snackbar container | none |
| actionTextStyle | object | action button text style | { color: 'orange'} |
| actionContainerStyle | object | your custom component for action's style | none |
| messageStyle | object | The style of message text | { color: '#ffffff'} |
| distanceCallback | function | Function to be caled whenever snackbar moves in and out or changes layout, the function will be supplied a number indicating distance taken up by snackbar on bottom. | (distance) => {} |
| bottom | number | The starting bottom position of snackbar | 0 |
| top | number | The starting top position of snackbar | 0 |
| position | string | The position of the snackbar: top, bottom | bottom |
| autoHidingTime | number | How many milliseconds the snackbar will be hidden | 0 (Do not hide automatically) |

## Note

* When visible prop is changed, the snackbar will be animated in/out of screen
* When position is top/bottom, you can specify those properties, e.g.
  position="top" top={10} (or) position="bottom" bottom={10}
