# Background Removal

This script utilizes the `ApexPainter` class from the `apexify.js` library to remove background from an `image`.

## Usage

To remove background from an image, follow these steps:

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

3.**Call the `removeBackground` meathod**:

- Provide image url to remove its background

```typescript
const imageURL = 'https://example.com/image.jpg';
const Api_Key = ""
```

4.**Generate The background Removed Image**:

```javascript
const removingBg = await painter.removeBackground(imageURL, Api_Key);
console.log(removingBg); // Returns a buffer image.
```

### Background Removal Parameters:

| Name        | Type     | Required | Description                                           |
|-------------|----------|----------|-------------------------------------------------------|
| `imageURL` | `string` | True     | The image url to remove its background.        |
| `Api_Key` | `string` | True     | The Api Key to use background removal, use [background removal](https://www.remove.bg) to get the key.        |
