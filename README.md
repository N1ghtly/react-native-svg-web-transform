# react-native-svg-web-transform

This library can be used as a drop-in replacement for react-native-svg when targeting the web. Inspiration for this library was [react-native-svg-web](https://github.com/bakerface/react-native-svg-web).
Sadly, it doesn't seem to be maintained anymore and *doesn't seem to actually work*. On top of that, this library will also convert group transforms to the correct web svg props. In example:

```JSX
<G translateX={25} translateY={100} scale={2} />
```

is transformed into

```JSX
<g transform="translate(25,100) scale(2)" />
```

There are two ways to drop this library in as replacement.

## How to change your webpack config

```javascript
module.exports = {
  ..., /* the existing configuration */

  resolve: {
    alias: {
      'react-native-svg': 'react-native-svg-web-transform'
    }
  }
};
```
