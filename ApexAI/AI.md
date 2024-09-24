# 🧠 **ApexAI: Comprehensive AI Integration**

**ApexAI** offers a powerful blend of AI capabilities, including **voice processing**, **image generation**, and **chat interactions**. It's built for flexible and dynamic AI use, allowing deep customization through API keys, role-playing features, and memory retention for more interactive experiences.

---

## 🚀 **Installation**

Start by importing `ApexAI` from the `apexify.js` library:

### JavaScript

```javascript
const { ApexAI } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexAI } from 'apexify.js'; 
```

---

## 💡 **ApexAI Capabilities**

ApexAI supports multiple AI-driven features: **Voice Processing**, **Image Generation**, **Chat Interactions**, and additional customization options. Let's explore each component in detail.

---

### 🔊 **Voice Processing**

Leverage ApexAI's voice processing to convert text into speech, choose voice models, and specify languages.

#### Example Usage:

```javascript
const aiOptions = {
  voice: {
    textVoice: {
      enable: true,
      voiceModel: "google",         // Select voice model
      voice_code: "en-US-3",        // Language and voice code
      apiKey: "your-api-key",       // Your API key
      type: "b"                     // Voice type (e.g., b for male, female, etc.)
    }
  }
};
```

#### Key Parameters:

- **`voice_code`**: Defines language and voice accent (e.g., `'en-US-3'`).
- **`apiKey`**: API key for voice service (optional).
- **`type`**: Defines voice type (e.g., `b` for specific voices like age or gender).

---

### 🎨 **Image Generation**

ApexAI can generate images based on user prompts and customizable settings.

#### Example Usage:

```javascript
const aiOptions = {
  imagine: {
    enable: true,                       // Whether to enbale or disbale the imagine feature
    drawTrigger: ["create", "draw"],   // Keywords to trigger image generation
    imageModel: "prodia",              // Select the model for image generation
    numOfImages: 2,                    // Number of images to generate
    ApiKeys: {
        groqAPI: 'your-groq-api-key', 
        electronHubKey: 'your-electron-api-key',
        rsnAPIkey: 'your-rsn-api-key',
        prodiaAPI: 'your-prodia-api-key',
        freesedGPTApi: 'your-fresed-api-key',
    },
    nsfw: {
      enable: true,                    // Enable NSFW filtering
      keywords: ['explicit', 'violence'],
      deepCheck: true
    },
    enhancer: {
      enable: true,                    // Enhance the generated image
      enhancerModal: 'ESRGAN_4x',
      negative_prompt: 'no text',
      cfg_scale: 7,
      sampler: 'DDIM',
      steps: 20,
      seed: -1,                        // Seed for reproducibility
      imgStyle: 'enhance',
      width: 512,
      height: 512,
      upscale: 2
    }
  }
};
```

#### Key Parameters:

- **`drawTrigger`**: Specifies words that trigger image generation.
- **`imageModel`**: The AI model used for image generation (e.g., `'prodia'`).
- **`nsfw`**: Enable NSFW filters to block inappropriate content.
- **`enhancer`**: Settings to improve image quality using models like `'ESRGAN_4x'`.
- **`dimensions`**: Adjust the **width** and **height** of the generated images.
- **`steps`, `cfg_scale`, `sampler`, `seed`**: Fine-tune the image generation process.

---

### 💬 **Chat Interactions**

ApexAI enables AI-powered chat responses, with memory retention and customizable personalities.

#### Example Usage:

```javascript
const aiOptions = {
  chat: {
    enable: true,                       // Whether to enbale or disbale the chat feature
    chatModel: "v3",                    // Chat model (e.g., 'v3', 'gemini')
    readFiles: true,                    // Enable file reading (PDFs, TXT)
    readImages: false,                  // Enable/disable image text extraction
    instruction: '',                    // To add instruction for the system to obey
    memory: {
      memoryOn: true,                   // Enable memory retention
      id: 'server-id'                   // Unique identifier (e.g., server or user ID)
    },
    typeWriting: {
      enable: true,                     // Simulate typewriting effect
      speed: 70,                        // Typing speed (characters per second)
      delay: 2000                       // Delay before typing starts (ms)
    },
    Api_Keys: {
      groq_API: 'your-groq-api-key',
      rsn_API: 'your-rsn-api-key',
      geminiAPI: 'your-gemini-api-key'
      electronHub_Key: 'your-electron-api-key',
    },
    lang: 'en',                         // Language of voice message
    personality: '/path/to/personality.txt'  // Path to personality profile
  }
};
```

#### Key Parameters:

- **`chatModel`**: The chat AI model (e.g., `'v3'`, `'gemini'`).
- **`readFiles`**: Enable AI to read and interpret file contents (e.g., PDFs, TXT).
- **`memory`**: Enable memory to recall past conversations for a specific user, server, or channel.
- **`typeWriting`**: Add a typewriting effect with customizable speed and delay.
- **`personality`**: Load a personality file to shape the AI's behavior.

---

### ⚙️ **Other Customization Options**

ApexAI allows further customizations, such as setting up message types, loader messages, and permission control.

#### Example Usage:

```javascript
const aiOptions = {
  others: {
    onMention: true,
    messageType: {
      type: 'send',
      intialContent: `<@${message.author.id}>, Hello!`
    },
    loader: {
      enable: true,
      loadingMessage: "Processing your request...",
      loadingTimer: 5000
    },
    permissions: {
      enable: true,
      role: ['admin-role-id'],
      blockedUsers: ['user1', 'user2']
    }
  }
};
```

#### Key Features:

- **`messageType`**: Choose between sending a new message or replying to a user.
- **`loader`**: Display a loading message during processing.
- **`permissions`**: Set access controls based on roles and users.
- **`channel`**: Specify channels where the bot will respond.

---

## 🌟 **Key Features & Customizations**

- **Voice Processing**: Convert text to speech with various voice models and accents.
- **Image Generation**: Generate and enhance images using models like `'prodia'` and set NSFW filters.
- **Chat Memory**: Retain conversation context for richer interactions.
- **Role-Playing**: Customize the AI’s personality by uploading a file or setting character instructions.
- **Keyword Responses**: Define specific replies to certain keywords.
- **Loading Messages**: Show custom messages while AI processes input.
- **Channel & Permission Settings**: Restrict bot usage to specific channels or users.

---

## 🛠 **Advanced Configuration**

ApexAI allows you to combine multiple features in a single configuration:

```javascript
const aiOptions = {
  voice: {
    textVoice: {
      enable: true,
      // Voice processing options...
    }
  },
  imagine: {
    enable: true,
    // Image generation options...
  },
  chat: {
    enable: true,
    // Chat interaction options...
  },
  others: {
    // Other customization options...
  }
};
```

💡 **Pro Tip**: You can customize each feature independently or together to build a more interactive and responsive AI.

---

## 📚 **Additional Information**

- **AI Models**: Use powerful models like `'gemini'`, `'v3'`, `'llama'`, and more.
- **Flexible API Keys**: Configure API keys per feature or use the defaults provided.
- **Completely Customizable**: All options, from voice to chat, can be personalized to suit your needs.