# 🖼 **ApexImageReader: Extract Text from Images**

**ApexImageReader** is designed to extract text from images using Optical Character Recognition (OCR). Whether you have a URL pointing to an image or a local file path, **ApexImageReader** provides a straightforward way to convert image content into readable text.

---

## 🚀 **Installation**

To use **ApexImageReader**, import it from the `apexify.js` library:

### JavaScript

```javascript
const { ApexImageReader } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexImageReader } from 'apexify.js'; 
```

---

## 📸 **ApexImageReader: Image Text Extraction**

`ApexImageReader` leverages Tesseract.js to perform OCR and extract text from images. It works with both image URLs and local file paths, making it versatile for various applications.

### 📌 **Example Usage**

```javascript
const imageUrl = 'https://example.com/image.png'; // URL or local path to the image

const extractedText = await ApexImageReader(imageUrl);
console.log(extractedText); // Logs the extracted text from the image
```

---

## ⚙️ **Parameters**

Here are the key parameters you can use to customize **ApexImageReader**:

| Parameter    | Description                                           | Required | Default Value |
|--------------|-------------------------------------------------------|----------|---------------|
| `imageURL`   | URL or local path of the image to process.           | Yes      | None          |

---

## 🌟 **Key Features**

### 🏷 **Text Extraction**
Extracts text from images using OCR technology. Suitable for various image formats.

### 🌐 **URL and Local Path Support**
Handles both HTTP/HTTPS URLs and local file paths for images.

### 🔄 **Automatic OCR Handling**
Uses Tesseract.js to recognize and extract text from the image efficiently.

### 🚨 **Error Handling**
Provides clear error messages in case of issues during processing.

---

## 📚 **How It Works**

1. **Provide Image URL or Path**: Input the URL or local path of the image from which you want to extract text.
2. **Text Extraction**: **ApexImageReader** uses Tesseract.js to perform OCR and extract text.
3. **Handle Results**: Receives the extracted text or an error message if the text extraction fails.

---

## 🛠 **Advanced Usage Example**

```javascript
const imagePath = 'path/to/local/image.png'; // Local path to the image
const extractedText = await ApexImageReader(imagePath);
console.log(extractedText); // JSON representation of the image content
```

---

## 📂 **Customization Options**

- **Image Source**: Can be a URL or a local file path. Ensure local paths are relative to your project's root directory for correct handling.
- **Error Handling**: Provides descriptive error messages for troubleshooting.

---

## 💡 **Note**

- **File Path Handling**: The `imageURL` parameter can be a URL for online images or a local file path. If using a local path, ensure it's relative to the main project directory. The path is treated as `path.join(process.cwd(), imageURL)` in the code.

---

💬 **Pro Tip**: For optimal OCR results, ensure that the image is clear and the text is legible. Poor image quality may affect the accuracy of the text extraction.

---