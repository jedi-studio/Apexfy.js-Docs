# Color Detection

This script utilizes the `ApexPainter` class from the `apexify.js` library to detect the dominant colors in an `image`.

## Usage

To detect dominant colors in an image, follow these steps:

1.**Import the `ApexPainter` class** from the `apexify.js` library:

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

2.**Create an instance of the `ApexPainter` class**:

```javascript
const painter = new ApexPainter();
```

3.**Call the `detectColors` meathod**:

- Provide the file path of the image.

```typescript
const imagePath = './path/to/image.png';
const dominantColors = await painter.colorAnalysis(imagePath);
console.log(dominantColors);
```

### Color Detection Parameters:

| Name        | Type     | Required | Description                                           |
|-------------|----------|----------|-------------------------------------------------------|
| `imagePath` | `string` | True     | The path of the image to detect colors from. This can be either a local file path or a URL to an image.        |

### Return Value

The `detectColors` function returns an array of objects, each containing the following properties:

- `color`: The detected color in the format `RGB`.
- `frequency`: The frequency of the detected color as a percentage of the total pixels in the image.

### Example Return Value

```json
[
  { "color": "255,255,255", "frequency": "30.50" },
  { "color": "0,0,0", "frequency": "25.20" },
  { "color": "255,0,0", "frequency": "12.80" }
]
```

In this example, the function detected three dominant colors in the image:

- The color `255,255,255` (white) with a frequency of 30.50%.
- The color `0,0,0` (black) with a frequency of 25.20%.
- The color `255,0,0` (red) with a frequency of 12.80%.
