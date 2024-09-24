# 🎧 **ApexListener: Audio Transcription with AI Response**

**ApexListener** allows you to transcribe audio files and generate AI-powered text responses. Whether the file is hosted online or locally in your project, **ApexListener** makes it simple to transcribe speech and enhance it with intelligent insights.

---

## 🚀 **Installation**

First, import the `ApexListener` function from the `apexify.js` library:

### JavaScript

```javascript
const { ApexListener } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexListener } from 'apexify.js';
```

---

## 🎙 **ApexListener: Audio to Text with AI Integration**

`ApexListener` processes an audio file (local or via URL) and provides an AI-generated response based on the transcription. You can use it for voice assistants, audio logs, and more!

### 📌 **Example Usage**

```javascript
const options = {
  filepath: 'https://example.com/audio.mp3',  // Can be a URL or a local path
  model: 'gemini',                            // AI model to generate the response
  prompt: 'Summarize this audio',             // (Optional) Custom prompt for the AI to enhance transcription
  apiKey: 'your-api-key'                      // (Optional) API key for the transcription service
};

const { response, transcribe } = await ApexListener(options);
console.log('Transcription:', transcribe);    // The text from the audio file
console.log('AI Response:', response);        // The AI's enhanced response based on transcription
```

---

## ⚙️ **Parameters**

Here are the key parameters for **ApexListener**:

| Parameter  | Description                                                                 | Required | Default Value |
|------------|-----------------------------------------------------------------------------|----------|---------------|
| `filepath` | The path or URL of the audio file. **Note**: If local, provide from the main project directory as it is treated as `path.join(process.cwd(), filePath)`. | Yes      | None          |
| `model`    | The AI model for generating responses (e.g., `'gemini'`).                   | Yes      | `'gemini'`    |
| `prompt`   | Custom prompt to influence the AI's response.                               | No       | `''` (empty)  |
| `apiKey`   | Optional API key for transcription services.                                | No       | None          |

---

## 🌟 **Key Features**

### 🔊 **Audio Transcription from URL or File**
Provide a URL or a local audio file path, and **ApexListener** will handle the rest! Local file paths should be relative to your main project directory.

### 🤖 **AI-Enhanced Responses**
Not only does **ApexListener** transcribe the audio, but it also passes the transcription to an AI model (like **ApexChat**) to generate an insightful response. Customize this response by providing your own prompt.

### 💼 **Multiple Audio Formats**
Works with various audio formats like `.mp3`, `.wav`, `.ogg`, and more, ensuring compatibility across different use cases.

---

## 📚 **How It Works**

1. **Provide the Audio**: You can either provide a direct URL or a local file path.
2. **Transcription**: The audio is converted to text.
3. **AI Enhancement**: Optionally, the transcription is passed to an AI model for further analysis or response generation.
4. **Return**: The transcribed text and the AI-generated response are returned for use in your application.

---

## 🎨 **Advanced Usage Example**

```javascript
const options = {
  filepath: 'audio/meeting-summary.mp3',        // Local path from the main project directory
  model: 'gemini-pro',                          // Using the 'gemini-pro' model for a detailed response
  prompt: 'Provide key takeaways from this meeting', // Custom prompt to guide the AI
  apiKey: ''                                    // Optional API key for enhanced transcription services
};

const { response, transcribe } = await ApexListener(options);
console.log('Transcription:', transcribe);      // Logs the transcription of the audio file
console.log('AI Response:', response);          // Logs the AI-generated key takeaways from the transcription
```

---

## 💡 **Notes & Tips**

- **Local File Paths**: When using local files, make sure the file path is relative to the main project directory. Internally, paths are handled as `path.join(process.cwd(), filePath)`, so structure your project accordingly.
  
- **URL Support**: You can also pass a direct URL to an audio file, making it easy to use hosted resources.

- **Custom Prompts**: If you want to guide the AI's response, use the `prompt` parameter to steer the AI towards generating summaries, key takeaways, or other insights from the transcription.

---

## 🌟 **Key Features Recap**

- **🎧 Audio Transcription**: Transcribe speech from an audio file or URL.
- **💬 AI Integration**: Generate AI-driven text responses based on transcriptions.
- **🔗 URL or File Path Support**: Flexibly use either online or local audio files.
- **✏️ Customizable Prompts**: Guide AI responses with your own custom prompts.

---

💡 **Pro Tip**: Combine **ApexListener** with other **ApexAI** capabilities like **ApexChat** and **ApexImagine** for a fully integrated AI-powered experience!

