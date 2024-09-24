# 🎨 **ApexImagine: AI-Driven Image Generation**

**ApexImagine** is your go-to tool for generating high-quality images using AI models. Customize your images by selecting the model, adjusting the size, and applying filters to create the perfect visual content for your needs.

---

## 🚀 **Installation**

First, import the `ApexImagine` function from the `apexify.js` library:

### JavaScript

```javascript
const { ApexImagine } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexImagine } from 'apexify.js'; 
```

---

## 🖼️ **ApexImagine: AI Image Generation**

`ApexImagine` lets you generate images from text prompts using a variety of AI models. You can customize image dimensions, select different AI models, and apply NSFW filters to ensure content safety.

### 📌 **Example Usage**

```javascript
const model = 'prodia'; // AI model (e.g., 'dalle', 'simurg', 'flux-pro', etc.)
const prompt = 'A futuristic cityscape at sunset'; // The image description
const imageOptions = {
  count: 2                // generates 2 images by default
  nsfw: false,            // Enable or disable NSFW content
  deepCheck = false,      // Enable deep check for nsfw
  nsfwWords = [],         // optional/custom nsfw badwords to check the image content for
  Api_key: 'your-optional-Api-key' // (Optional) Use your own API key

  // prodia models extra options
  negative_prompt = "",
  sampler = "DPM++ 2M Karras",
  height = 512,
  width = 512,
  cfg_scale = 9,
  steps = 20,
  seed = -1,
  image_style = "cinematic"
};

const imageResponse = await ApexImagine(model, prompt, imageOptions);
console.log(imageResponse); // Logs the AI-generated image URL
// results: 
[
'https://images.prodia.xyz/e04eb88e-b649-42ed-847c-9cad85969372.png'
] 
```

---

## ⚙️ **Parameters**

Here are the key parameters you can use to customize **ApexImagine**:

| Parameter     | Description                                                                       | Required | Default Value |
|---------------|-----------------------------------------------------------------------------------|----------|---------------|
| `model`       | Specifies the AI model (e.g., `'dall-e-3'`, `'lexica'`).                   | Yes      | None          |
| `prompt`      | The image description that the AI will generate.                                  | Yes      | None          |
| `width`       | Width of the generated image in pixels.                                           | No       | 1024          |
| `height`      | Height of the generated image in pixels.                                          | No       | 1024          |
| `nsfw`        | Enable or disable NSFW content in the generated image.                            | No       | `false`       |
| `Api_key`     | Optional API key if you want to use a different key for the current AI model.      | No       | None          |

---

## 🌟 **Key Features**

### 🖼️ **High-Quality Image Generation**
Generate visually stunning images by simply providing a text-based description. Select from a variety of AI models optimized for different artistic styles and formats.

### 📏 **Customizable Image Dimensions**
Adjust the width and height of the generated images to meet your specific size requirements. Perfect for social media, websites, or print.

### 🔞 **NSFW Filter**
Control whether the AI is allowed to generate NSFW content by toggling the `nsfw` parameter. This feature helps ensure that the generated content is safe and appropriate for your audience.

### 🔑 **API Key Flexibility**
Like other ApexAI modules, you can provide your own API key to use specific AI models. If no API key is provided, the default keys for the selected model will be used.

---

## 📚 **How It Works**

1. **Choose your AI model**: Available models include `'dall-e-3'`, `'midjourney-v6.1'`, and others.
2. **Provide a text prompt**: Describe the image you want to generate.
3. **Optional image size and NSFW settings**: Customize the dimensions and enable or disable NSFW content.
4. **Optional API Key**: Provide your own API key if you want to use a custom AI model or key.

---

## 🎨 **Advanced Usage Example**

```javascript
const model = 'prodia'; // Using the 'prodia' model
const prompt = 'A cyberpunk city at night with neon lights'; // Image description
const imageOptions = {
  count: 1
};

const imageResponse = await ApexImagine(model, prompt, imageOptions);
console.log(imageResponse); // Logs the AI-generated image URL
// results: 
[
'https://images.prodia.xyz/e04eb88e-b649-42ed-847c-9cad85969372.png'
]
```

---

## 📂 **Customization Options**

- **Image Size Control**: Modify the dimensions of the generated images by setting the `width` and `height` parameters to fit your needs.
- **NSFW Filter**: Ensure content safety by enabling or disabling NSFW images with a simple parameter.
- **User-Controlled API Keys**: As with ApexChat, you can provide your own API key if needed, allowing for more personalized integration with external models.

---

## 🛠 **Model & Configuration Settings**

- **AI Models**: Choose from popular models like `'sdxl-lightning'`, `'niji-v6'`, or others, depending on the image style you want.
- **Custom Dimensions & Content Filtering**: Specify the exact size of the image and filter out NSFW content to ensure the output aligns with your needs.
- **Optional API Key**: Customize your experience by using your own API key, especially if you're working with premium or personalized AI models.

---

💡 **Pro Tip**: Get creative with your prompts! The more detailed and vivid the description, the more tailored and imaginative the generated images will be.