# Canvas Background

This script uses the `ApexPainter` class from the `apexify.js` library to generate customizable canvas backgrounds.

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

3.Define options for the canvas background:

```javascript
const canvasBg = {
    width: 800,
    height: 600,
    x: 100,
    y: 50,
    customBg: 'https://example.com/image.jpg | ./image.png',
    colorBg: 'blue',
    gradientBg: {
        type: 'linear',
        startX: 0,
        startY: 0,
        startRadius: 0,
        endRadius: 0,
        endX: 800,
        endY: 600,
        colors: [
            { stop: 0, color: 'red' },
            { stop: 0.5, color: 'green' },
            { stop: 1, color: 'blue' }
        ]
    },
    stroke: {
        color: 'black',
        width: 2,
        position: 0.5,
        borderRadius: 10 | 'circular'
    },
    shadow: {
        color: 'rgba(0, 0, 0, 0.5)',
        offsetX: 2,
        offsetY: 2,
        blur: 5,
        opacity: 0.5
    },
    rotation: 45,
    borderRadius: 20 | 'circular'
};
```

!!!info Note
 The option `customBg` can be either `ImageURL` or `Local Image`
!!!

!!!info Note
 The option `borderRadius` can be either `number` or `circular`.
!!!

4.Generate the canvas background:

```javascript
const bufferBackground = await painter.createCanvas(canvasBg);
console.log(bufferBackground); // Returns a object.

{
buffer: .... // The Buffer of the bg
canvas: .... // Deatils used in the canvas
}
```

### Background Parameters:

| Name          | Type            | Required | Description                                                  |
| :---          | :---:            | :---:    | ---                                                          |
| `width`         | `number`              | False     | Specifies the width of the background canvas.               |
| `height`        | `number`              | False     | Specifies the height of the background canvas.              |
| `x`, `y`             | `number`              | False     | Specifies the position of the background canvas on the x-axis and y-axis. |
| `customBg`      | `string`    | False | Specifies the URL or local path to the custom background image.
| `colorBg`       | `string`           | False    | Specifies the background color if no custom background image is provided. |
| `gradientBg`    | `Object`           | False    | Specifies the gradient background configuration.            |
| `stroke`        | `Object`           | False    | Specifies the stroke configuration.                          |
| `shadow`        | `Object`           | False    | Specifies the shadow configuration.                          |
| `rotation`      | `number`               | False    | Specifies the rotation angle of the background.             |
| `borderRadius`  | `number | "circular"`  | False    | Specifies the border radius of the background.              |
