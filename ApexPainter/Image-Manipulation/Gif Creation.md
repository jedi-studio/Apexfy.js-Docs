# GIF Creation Guide

This script utilizes the `ApexPainter` class from the `apexify.js` library to creat gif using multiple sets of `images`.

## Usage

To create a GIF using the `ApexPainter` class, follow these steps:

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

1. Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

2.Define the options for the GIF:

- Prepare an array of images to include in the GIF. Each image should be represented as an object with the following properties:

```typescript
const images = [
    { source: 'image1.png', isRemote: false },
    { source: 'image2.png', isRemote: false },
    { source: 'https://w7.pngwing.com/pngs/417/624/arrow.png', isRemote: true }
];

const options = {
    outputFile: 'output.gif',
    repeat: 0,
    quality: 10,
    delay: 3000,
    watermark: {
        enable: true,
        url: 'watermark.png'
    },
    textOverlay: {
        text: 'Sample Text',
        fontName: 'Arial',
        fontSize: 20,
        fontColor: 'white',
        x: 10,
        y: 30
    }
};

const outputGif = await painter.createGIF(images, options);
```

!!!info Note
 The option `outputFile` can be "buffer", "file", "attachment", or "base64".
!!!

### Gif Parameters:

| Name            | Type            | Required | Description                                                                                   |
|-----------------|-----------------|----------|-----------------------------------------------------------------------------------------------|
| `outputFile`      | string          | True     | The output file path for the generated GIF                                                    |
| `repeat`          | number          | False    | Number of times to repeat the GIF animation (0 for infinite loop)                             |
| `quality`         | number          | False    | GIF quality, ranging from 1 to 20                                                              |
| `delay`           | number          | False    | Delay between frames in milliseconds                                                          |
| `watermark`       | object          | False    | An object containing properties related to watermark                                           |
| `textOverlay`     | object          | False    | An object containing properties related to text overlay on each frame                          |
| `images`          | array of objects| True     | An array of objects representing each image to include in the GIF                              |

| Name            | Type    | Required | Description                                                                                   |
|-----------------|---------|----------|-----------------------------------------------------------------------------------------------|
| `source`          | string  | True     | URL or local file path of the image                                                           |
| `isRemote`        | boolean | True     | Indicates whether the image is hosted remotely (`true`) or locally (`false`)                   |
