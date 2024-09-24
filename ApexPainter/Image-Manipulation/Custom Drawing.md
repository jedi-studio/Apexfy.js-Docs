# Custom Drawing

This script utilizes the `ApexPainter` class from the `apexify.js` library to draw customizable (`Lines` | `Shapes`)  on a canvas background.

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

1.Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

2.**Define Custom Options**: Create an array of custom options, each specifying the start and end coordinates of the line, as well as its style.

- You can use your custom background by converting it into a buffer and use it in `createCustom`.

[!ref How To Buffer An Image](../Image-Enhancement/Buffer.md)

     ```javascript
     const options = [
         {
             startCoordinates: { x: 100, y: 100 },
             endCoordinates: { x: 300, y: 100 },
             lineStyle: {
                 color: 'red',
                 width: 3,
                 lineRadius: 10,
                 stroke: {
                     color: 'blue',
                     width: 2
                 },
                 shadow: {
                     color: 'rgba(0, 0, 0, 0.5)',
                     offsetX: 2,
                     offsetY: 2,
                     blur: 5
                 }
             }
         },
         {
             startCoordinates: { x: 200, y: 200 },
             endCoordinates: { x: 400, y: 300 },
             lineStyle: {
                 color: 'green',
                 width: 2,
                 lineRadius: 12
             }
         }
     ];
     ```

3.**Custom Option Object**: Each object in the `options` array represents a custom line. It contains the following properties:

- `startCoordinates`: Object specifying the x and y coordinates of the starting point of the line.
- `endCoordinates`: Object specifying the x and y coordinates of the ending point of the line.
- `lineStyle`: Object specifying the style of the line, including color, width, line radius, stroke (optional), and shadow (optional).

4.**Drawing Custom Lines**: Once you've defined your custom options, you can use them to draw custom lines on a canvas.

5.Generate The Final Custom Canvas Made:

```javascript
const bufferCustom = await painter.createCustom(buffer, options);
console.log(bufferCustom); // Returns a buffer image.
```

### Custom Parameters:

| Option             | Type                      | Required   | Description                                                                               |
| ------------------ | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `startCoordinates`| `{ x: number, y: number }`| True       | Specifies the starting coordinates of the line.                                            |
| `endCoordinates`  | `{ x: number, y: number }`| True       | Specifies the ending coordinates of the line.                                              |
| `lineStyle`        | `LineStyleOptions`        | False       | Specifies the style of the line, including color, width, line radius, stroke, and shadow.|

### LineStyleOptions Explanation

| Option         | Type                      | Required   | Description                                                                               |
| -------------- | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `color`        | `string`                  | True       | Specifies the color of the line.                                                           |
| `width`        | `number`                  | True       | Specifies the width of the line.                                                           |
| `lineRadius`   | `number | "circular"`    | True       | Specifies the radius of curvature for the line. Can be a number or "circular".             |
| `stroke`       | `StrokeOptions`           | False      | Specifies the stroke configuration of the line.                                             |
| `shadow`       | `ShadowOptions`           | False      | Specifies the shadow configuration of the line.                                             |

#### StrokeOptions Explanation

| Option         | Type                      | Required   | Description                                                                               |
| -------------- | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `color`        | `string`                  | False      | Specifies the color of the stroke.                                                         |
| `width`        | `number`                  | False      | Specifies the width of the stroke.                                                         |
| `position`     | `number`                  | False      | Specifies the position of the stroke.                                                      |
| `borderRadius` | `number | "circular"`    | False      | Specifies the border radius of the stroke. Can be a number or "circular".                  |

#### ShadowOptions Explanation

| Option         | Type                      | Required   | Description                                                                               |
| -------------- | ------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| `color`        | `string`                  | False      | Specifies the color of the shadow.                                                         |
| `offsetX`      | `number`                  | False      | Specifies the horizontal offset of the shadow.                                             |
| `offsetY`      | `number`                  | False      | Specifies the vertical offset of the shadow.                                               |
| `blur`         | `number`                  | False      | Specifies the blur radius of the shadow.                                                   |
| `opacity`      | `number`                  | False      | Specifies the opacity of the shadow.                                                        |
| `borderRadius` | `number | "circular"`    | False      | Specifies the border radius of the shadow. Can be a number or "circular".                   |
