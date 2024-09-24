# Colors Filter

This script utilizes the `ApexPainter` class from the `apexify.js` library to Apply color filter on image.

## Usage

To use the `colorsFilter` function, follow these steps:

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
2. Create an instance of the `ApexPainter` class:

```javascript
const painter = new ApexPainter();
```

3.**Call the Method**: Call the `colorsFilter` method with the following parameters:

```javascript
    const imagePath = './image.jpg';
    const filterColor = '#ff0000';

    const outputBuffer = await painter.colorsFilter(imagePath, filterColor);
```

4.**Use the Output**: The `outputBuffer` variable contains the modified image data in the form of a Buffer.

### Color Filters Parameters: 

| Name         | Type        | Required | Description                                                                                                                                                     |
|--------------|-------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `imagePath`  | `string`    | True      | A string representing the path to the image file. It can be a local file path or a URL.                                                                       |
| `filterColor`| `string`    | True      | A string representing the color to apply as a filter. Only hexadecimal color codes are supported.                                                              |
| `baseDir`    | `string`    | False       | The base directory path if `imagePath` is a relative path. This is required if `imagePath` is not an absolute path.                                           |
