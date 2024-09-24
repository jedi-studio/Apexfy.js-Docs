# Converting Image Extension

This script utilizes the `ApexPainter` class from the `apexify.js` library to convert image extensions into various formats such as PNG, JPEG, AVIF, WebP, SVG, and more.

## Usage

To convert an image extension using the `ApexPainter` class, follow these steps:

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

3. **Define the options for converting**:

- Provide the file path of the image.
- Provide the extension you want to convert to.

```javascript
const image = './image.png';
const newExtension = 'png';
```

4. **Generate The Converted Image**:

```javascript
const outputConvertedImage = await painter.imgConverter(image, newExtension);
console.log(outputConvertedImage); // Returns a buffer image.
```

### Convert Image Parameter:

| Name           | Type     | Required | Description                                                           |
|----------------|----------|----------|-----------------------------------------------------------------------|
| `image`        | `string` | True     | The path of the image to convert. Can be a local file path or a URL. |
| `newExtension` | `string` | True     | The new extension to convert the image to (e.g., 'png', 'jpeg', 'webp'). |
