# Image Effects

This script utilizes the `ApexPainter` class from the `apexify.js` library to apply multiple different filters to the provided `image`.

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

3.Call the `processImage` method with the image path and the array of filters:

```javascript
const imagePath = 'path/to/your/image.jpg';
const filters = [
  { type: 'flip', horizontal: true, vertical: false },
  { type: 'mirror', horizontal: true, vertical: false },
  { type: 'rotate', deg: 90, mode: 'clamp' },
  { type: 'brightness', value: 0.5 },
  { type: 'contrast', value: 0.5 },
  { type: 'dither565' },
  { type: 'greyscale' },
  { type: 'invert' },
  { type: 'normalize' },
  { type: 'autocrop', tolerance: 0 },
  { type: 'crop', x: 100, y: 100, w: 200, h: 200 },
  { type: 'fade', factor: 0.5 },
  { type: 'opacity', factor: 0.5 },
  { type: 'opaque' },
  { type: 'gaussian', radius: 5 },
  { type: 'blur', radius: 5 },
  { type: 'posterize', levels: 5 },
  { type: 'sepia' },
  { type: 'pixelate', size: 10, x: 100, y: 100, w: 200, h: 200 },
];

try {
  const processedImageBuffer = await painter.processImage(imagePath, filters);
} catch (error) {
  console.error('Error processing image:', error.message);
}
```

### Image Effects Parameters:

| Parameter    | Type      | Required | Description                                                                           |
|--------------|-----------|----------|---------------------------------------------------------------------------------------|
| `imagePath`       | `string`  | True      | Specifies the image path. It can be either a local or URL image.                                                |
| `filters` | `array` | True       | An array containing objects of filters and their types.                          |

### Filters Parameters:

| Parameter    | Type      | Required | Description                                                                           |
|--------------|-----------|----------|---------------------------------------------------------------------------------------|
| `type`       | `string`  | True      | Specifies the type of filter to apply.                                                |
| `horizontal` | `boolean` | False       | Determines whether to flip or mirror the image horizontally.                          |
| `vertical`   | `boolean` | False       | Determines whether to flip or mirror the image vertically.                            |
| `deg`        | `number`  | False       | Specifies the degree of rotation for the `rotate` filter.                              |
| `mode`       | `string`  | False       | Specifies the mode of rotation for the `rotate` filter (`clamp`, `wrap`, or `mix`).    |
| `value`      | `number`  | False       | Specifies the value of brightness or contrast adjustment.                               |
| `tolerance`  | `number`  | False       | Specifies the tolerance for autocropping the image.                                    |
| `x`, `y`     | `number`  | False       | Specifies the coordinates of the top-left corner of the cropped region for the `crop` filter. |
| `w`, `h`     | `number`  | False       | Specifies the width and height of the cropped region for the `crop` filter.             |
| `factor`     | `number`  | False       | Specifies the factor for the `fade` and `opacity` filters.                              |
| `radius`     | `number`  | False       | Specifies the radius of blur for the `gaussian` and `blur` filters.                     |
| `levels`     | `number`  | False       | Specifies the number of levels for the `posterize` filter.                              |
| `size`       | `number`  | False       | Specifies the size of pixels for the `pixelate` filter.                                 |
