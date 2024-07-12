# Canvas Text Drawing

This script utilizes the `ApexPainter` class from the `apexify.js` library to draw customizable text on a canvas background.

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

3.Define an array of text objects with their respective options:

- You can use your custom image by converting it into buffer and use it in createImage.

[!ref How To Buffer An Image](../Image-Enhancement/Buffer.md)

```javascript
const text = [
  {
    text: 'Hello World',
    x: 90,
    y: 20,
    fontPath: './fonts/customFont.ttf',
    fontName: 'fontName',
    fontSize: 30,
    isBold: true,
    color: '#00ff00',
    maxWidth: 30,
    lineHeight: 10,
    textAlign: 'center',
    textBaseline: 'alphabetic',
    oulined: false,
    opacity: 0.7,
    rotation: 360,
    gradient: {
      type: 'linear',
      startX: 0,
      endX: 300,
      startY: 0,
      endY: 0
    },
    shadow: {
      color: 'white',
      offsetX: 10,
      offsetY: -10,
      blur: 10,
      opacity: 5,
    },
    stroke: {
      color: 'black',
      width: 1,
    }
  },
  // Add other texts and their options here.
];
```

!!!info Note
 The option `fontPath` should point to the file containing your custom font.
!!!

4.Generate the final canvas image with text:

```javascript
const textBuffer = await painter.createText(text, bufferImage);
console.log(textBuffer); // Returns a buffer image.
```

### Text Parameters:

| Option         | Type                      | Required   | Description                                                                               |
| -------------- | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `text`         | `string`                  | False        | Specifies the text to add.                                                                 |
| `x`, `y`       | `number`                  | False        | Specifies the position of the text on the canvas.                                          |
| `fontPath`     | `string`                  | False         | Specifies the path to the custom font directory.                                           |
| `fontName`     | `string`                  | False         | Specifies the name of the custom font (default is 'Arial').                                 |
| `fontSize`     | `number`                  | False        | Specifies the size of the text on the image.                                                |
| `isBold`       | `boolean`                 | False         | Specifies whether to apply boldness to the text.                                            |
| `color`        | `string`                  | False        | Specifies the color of the text.                                                            |
| `maxWidth`     | `number`                  | False         | Specifies the maximum width of the text for wrapping.                                       |
| `lineHeight`   | `number`                  | False         | Specifies the line height for wrapped text.                                                 |
| `textAlign`    | `string` | False | Specifies the text alignment whether center, end, start, left, right, or justify.                                                              |
| `textBaseline` | `string`                  | False         | Specifies the baseline for letters whether to be alphabetic, bottom, hanging, ideographic, top, middle.                                                         |
| `outlined`       | `boolean`                 | False         | Specifies whether to make text outlined and non-filled.                                            |
| `opacity`       | `number`                 | False         | Specifies whether to apply opacity on the text its self.                                            |
| `rotation`       | `number`                 | False         | Specifies whether to apply rotation to the text.                                            |
| `gradient`       | `object`                 | False         | Specifies whether to apply gradient colours to the text instead of static colors.                                            |
| `shadow`       | `ShadowOptions`           | False         | Specifies the shadow configuration of the text.                                             |
| `stroke`       | `StrokeOptions`           | False         | Specifies the stroke configuration of the text.                                             |
