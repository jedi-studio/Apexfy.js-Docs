# 📂 **ApexFileReader: Versatile File Reading**

**ApexFileReader** provides a unified approach to read and process various file types including PDFs, CSVs, and plain text. Whether you're dealing with local files or URLs, **ApexFileReader** offers a seamless way to handle file inputs and extract meaningful content.

---

## 🚀 **Installation**

To use **ApexFileReader**, import it from the `apexify.js` library:

### JavaScript

```javascript
const { ApexFileReader } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexFileReader } from 'apexify.js'; 
```

---

## 📂 **ApexFileReader: File Reading**

`ApexFileReader` is designed to handle various file formats and sources, including local files and URLs. It supports PDF and CSV file parsing and can be extended to handle additional formats if needed.

### 📌 **Example Usage**

```javascript
const filePathOrUrl = 'path/to/your/file.pdf'; // Could be a URL or local path
const fileType = 'pdf'; // Optional: Specify file type ('pdf', 'csv', etc.)

const fileContent = await ApexFileReader(filePathOrUrl, fileType);
console.log(fileContent); // Logs the content of the file
```

---

## ⚙️ **Parameters**

Here are the key parameters you can use to customize **ApexFileReader**:

| Parameter    | Description                                                                                       | Required | Default Value |
|--------------|---------------------------------------------------------------------------------------------------|----------|---------------|
| `pathOrUrl`  | Path or URL of the file to read.                                                                  | Yes      | None          |
| `type`       | Type of the file (e.g., `'pdf'`, `'csv'`). If not provided, the type will be inferred from the file extension. | No       | Automatically inferred |

---

## 🌟 **Key Features**

### 📄 **PDF Parsing**
Extracts text from PDF files. If direct parsing fails, it will attempt OCR (Optical Character Recognition) using Tesseract.js.

### 📊 **CSV Parsing**
Converts CSV content into a JSON format, making it easy to work with structured data.

### 🌐 **URL Support**
Supports loading files from URLs as well as local file paths.

### 🛠 **File Type Detection**
Automatically detects the file type based on the file extension if not explicitly specified.

---

## 📚 **How It Works**

1. **Specify File Path or URL**: Provide the path to the file or a URL where the file is hosted.
2. **Optional File Type**: You can specify the file type or let **ApexFileReader** determine it based on the file extension.
3. **Reading and Parsing**: Depending on the file type, **ApexFileReader** will parse the content accordingly. For PDFs, it will handle OCR if needed. For CSVs, it will convert the data to JSON.

---

## 🛠 **Advanced Usage Example**

```javascript
const fileUrl = 'https://example.com/sample.csv'; // URL of the file
const fileContent = await ApexFileReader(fileUrl, 'csv');
console.log(fileContent); // JSON representation of the CSV content
```

---

## 📂 **Customization Options**

- **File Type**: Specify the file type if known. If not provided, it will be inferred from the file extension.
- **OCR for PDFs**: Automatically performs OCR on PDFs if the standard parsing fails.
- **URL Handling**: Supports both HTTP/HTTPS URLs and local file paths.

---

## 💡 **Note**

- **File Path Handling**: The `pathOrUrl` parameter can be a URL for online files or a local file path. If using a local path, ensure it's relative to the main project directory. The path is treated as `path.join(process.cwd(), pathOrUrl)` in the code.

---

💬 **Pro Tip**: For better file handling, make sure that your local file paths are correctly specified relative to your project's root directory.