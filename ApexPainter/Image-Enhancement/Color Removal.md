# Color Removal

This markdown guide explains how to utilize the `ApexPainter` class from the `apexify.js` library to remove specific RGBA colors from images.

## Usage

To remove colors from an image using the `ApexPainter` class, follow these steps:

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

3.**Define the options for color removal**:

- Provide the file path of the image.
- Specify the RGBA color.

```javascript
const image = './image.png';
const RGB_COLOR = {
 red: 20,
 green: 225,
 blue: 40
};
```

4.**Generate the converted image**:

```javascript
const outputColorRemoval = await painter.colorsRemover(image, RGB_COLOR);
console.log(outputColorRemoval); // Returns a buffer image.
```

### Color Removal Parameter:

| Name           | Type     | Required | Description                                                           |
|----------------|----------|----------|-----------------------------------------------------------------------|
| `image`        | `string` | True     | The path of the image to convert. Can be a local file path or a URL. |
| `RGB_COLOR` | `object` | True     | The RGB color to be removed from the image. |
