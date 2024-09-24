# Resizing Images

This script utilizes the `ApexPainter` class from the `apexify.js` library to resize `images`.

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

1.Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

2.Define the options for the Resizing:

- Prepare an array of images to include in the GIF. Each image should be represented as an object with the following properties:

```javascript
const resizedOptions = {
   imagePath: './image.png',
   size: { width: 300, height: 500 }
}
```

3.Generate The Resized Image:

```javascript
const outputResized = await painter.resize(resizedOptions);
console.log(outputResized); // Returns a buffer image.
```

### Resize Image Parameter:

| Name       | Type     | Required | Description                                                      |
|------------|----------|----------|------------------------------------------------------------------|
| `imagePath`  | `string`   | True     | The path of the image to resize. Can be a local file path or a URL. |
| `size`      | `object`   | True     | An object specifying the new dimensions for resizing.            |
