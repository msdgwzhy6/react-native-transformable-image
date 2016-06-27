# react-native-transformable-image

A transformable image component, as the known **PhotoView** or **ImageViewer**, supports gestures like pan, pinch, double tab and fling, is written in **pure JavaScript**, supports **both iOS and Android**.

![](Demo/demo.gif)

## Install

 `npm install --save react-native-transformable-image@latest`



## Usage

Quite same as the official **[Image](https://facebook.github.io/react-native/docs/image.html)**, as below shows:

```
import Image from 'react-native-transformable-image';
...
render() {
    return (
      ...
        <Image
          style={{width: width, height: height}}
          source={{uri: 'https://raw.githubusercontent.com/yoaicom/resources/master/images/game_of_thrones_1.jpg'}}
          //pixels={{width: 3607, height: 2400}}
        />
      ...
    );
  }
```

The **pixels** prop is used to align the edge of the image content with the view's boundry and to determine the max scale. This prop is **optional** if the image is remote (*like `source={{uri: 'http://remoteurl'}}`*) and you are using react-native 0.28 and above.(This component will use **Image.getSize** to get pixels info both on iOS and Android since release [v0.28-rc](https://github.com/facebook/react-native/releases/tag/v0.28.0-rc.0) when no pixels prop provided.

If your image is local (*like `source={require('...')}`*) or you are using react-native v0.27 and below, you should provide the **pixels** prop, wraping the image's width and height.(You can ask your API server to provide image pixels info)