# Image Cropping

This script utilizes the `ApexPainter` class from the `apexify.js` library crop an `image` customizable with ease.

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

2.**Define Cropping Options**: Create an array of coordinates, each specifying the start and end coordinates of the line, as well as its tension.

- tension is referred to the line either to be loose or rigid.

```typescript
const options = {
  imageSource: './path/to/image.png',
  coordinates: [
    { from: { x: 100, y: 100 }, to: { x: 200, y: 200 }, tension: 0.5 },
    { from: { x: 200, y: 200 }, to: { x: 400, y: 400 }, tension: 0.5 },
    { from: { x: 400, y: 400 }, to: { x: 450, y: 600 }, tension: 0.5 },
    { from: { x: 450, y: 600 }, to: { x: 200, y: 120 }, tension: 0.5 },
    // Add more coordinates if needed
  ],
  crop: 'inner',
  radius: 20
};
```

!!!info Note
The coordinates represent points connected by lines. Depending on the chosen crop type, these lines define whether to remove the inner or outer area of the image.
!!!

4.**Generate The Cropped Image**:

```javascript
  const croppedImage = await painter.cropImage(options);
console.log(croppedImage); // Returns a buffer image.
```

### Image Cropping Parameters:

| Name            | Type                               | Required | Description                                                  |
|-----------------|------------------------------------|----------|--------------------------------------------------------------|
| `imageSource`   | `string`                           | True     | The path to the image to be cropped. It can be either URL or Local image.                         |
| `coordinates`   | `CropCoordinate[]`                 | True     | An array of coordinates defining the area to be cropped.     |
| `crop`          | `'inner' | 'outer'`               | True     | Specifies whether to perform an inner or outer crop.         |
| `radius`        | `number | 'circular' | null`     | False    | Specifies the radius for rounded corners in inner crop.     |
