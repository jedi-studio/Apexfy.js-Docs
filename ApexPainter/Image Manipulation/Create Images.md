# Canvas Image Drawing

This script utilizes the `ApexPainter` class from the `apexify.js` library to draw customizable images on a canvas background.

## Usage

1.Import the `ApexPainter` class from the `apexify.js` library:

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

2.Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

3.Define an array of image objects with their respective options:

- You can add as many objects of images to draw inside the array as you like.

- You can use your custom background by converting it into buffer and use it in createImage.

[!ref How To Buffer An Image](/Apexify.js/canvas/Buffer.md)

```javascript
const images = [
  {
    source: 'https://example.com/image.jpg | ./image.png | square',
    width: 300,
    height: 200,
    x: 30,
    y: 50,
    isFilled: true,
    color: '#2e2e2e',
    gradient: {
      type: 'linear',
      startX: 0,
      startY: 0,
      endX: 800,
      endY: 600,
      colors: [
        { stop: 0, color: 'red' },
        { stop: 0.5, color: 'green' },
        { stop: 1, color: 'blue' }
      ]
    },
    rotation: 90,
    borderRadius: 50 | "circular",
    stroke: {
      color: 'green',
      width: 5,
      position: 7,
      borderRadius: 50 | "circular"
    },
    shadow: {
      color: 'rgb(255, 34, 89, 0.6)',
      offsetX: 10,
      offsetY: -10,
      blur: 10,
      opacity: 5,
      borderRadius: 50 | "circular"
    }
  },
  // Add other images with their options here.
];
```

!!!info Note
 The option `source` can be either `ImageURL` or `Local Image` or `Shape Name`.
!!!
!!!info Note
 The option `borderRadius` can be either `number` or `circular`.
!!!
4. Generate the canvas image:

```javascript
const bufferImage = await painter.createImage(images, bufferBackground);
console.log(bufferImage); // Returns a buffer image.
```

### Images Parameters:

| Option         | Type                      | Required   | Description                                                                               |
| -------------- | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `source`       | `string`                  | True        | Specifies the image source, either a URL, local image path, or shape name.                |
| `width`, `height` | `number`                 | False        | Specifies the dimensions of the image.                                                     |
| `x`, `y`       | `number`                  | False        | Specifies the position of the image on the canvas.                                          |
| `isFilled`     | `boolean`                 | False         | Specifies whether to fill the shape (applied if source is a shape name).                    |
| `color`        | `string`                  | False         | Specifies the color of the shape (applied if source is a shape name).                       |
| `gradient`     | `GradientOptions`         | False         | Specifies the gradient color of the shape (applied if source is a shape name).               |
| `rotation`     | `number`                  | False         | Specifies the rotation angle of the image.                                                  |
| `borderRadius` | `number | "circular"`    | False         | Specifies the border radius of the image.                                                    |
| `stroke`       | `StrokeOptions`           | False         | Specifies the stroke configuration of the image.                                             |
| `shadow`       | `ShadowOptions`           | False         | Specifies the shadow configuration of the image.                                             |
