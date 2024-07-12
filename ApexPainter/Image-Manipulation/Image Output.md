# Image Output

This guide will help you use the `ApexPainter` class from the `apexify.js` library to create and customize the output format of your drawings, including backgrounds, images, and text.

## Usage

### 1. Import the `ApexPainter` class

First, you need to import the `ApexPainter` class from the `apexify.js` library.

+++ JS

```javascript
const { ApexPainter } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexPainter } from 'apexify.js'; 
```

+++

### 2. Create an instance of the `ApexPainter` class

Next, create an instance of the `ApexPainter` class. This instance will be used to perform various drawing operations.

```javascript
const painter = new ApexPainter();
```

### 3. Draw your desired image

Now, you can start creating your desired image by drawing the background, adding images, and overlaying text. Finally, you can use the `paint.outPut()` method to get the result in your chosen format.

Here is a detailed example:

```javascript
async function run() {
    // Create an instance of ApexPainter with the desired output type
    const paint = new ApexPainter({ type: 'url' }); // You can choose from 'url', 'dataURL', 'buffer', 'blob', 'base64', 'arraybuffer'

    // Define the background configuration
    const background = {
        // Your background drawing properties
    };

    // Define the images you want to add
    const images = [
        {
            source: '' // Your image source
        }
    ];

    // Define the text you want to overlay
    const texts = [
        {
            text: '' // Your text content
        }
    ];

    // Create the background canvas
    const bg = await paint.createCanvas(background); // Creating Background

    // Add images on top of the background
    const image_Bg = await paint.createImage(images, bg); // Creating Image + Background

    // Add text on top of the image and background
    const finalResult = await paint.createText(texts, image_Bg); // Creating Image + Background + Text

    // Convert the final result into your desired format
    const output = paint.outPut(finalResult); // Converting final results into your desired format
    console.log(output); // This will return the output as an online hosted URL image (or another format you specified)
}

// Execute the function
run();
```
