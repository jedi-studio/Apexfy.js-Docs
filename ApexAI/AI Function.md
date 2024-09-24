# 🧠 **ApexChat: AI-Driven Text Responses**

**ApexChat** empowers your application to generate intelligent, customizable chat responses. With built-in memory retention and role-playing features, **ApexChat** is designed for engaging and dynamic conversations, making it a versatile solution for text-based AI interactions.

---

## 🚀 **Installation**

First, import the `ApexChat` function from the `apexify.js` library:

### JavaScript

```javascript
const { ApexChat } = require('apexify.js'); 
```

### TypeScript

```typescript
import { ApexChat } from 'apexify.js'; 
```

---

## 💬 **ApexChat: AI Text Response Generation**

`ApexChat` allows you to generate text-based responses using a variety of AI models. You can enable memory for chat history tracking and give the AI specific instructions to shape its behavior, such as acting in different roles or personalities.

### 📌 **Example Usage**

```javascript
const model = 'gemini'; // AI model (e.g., 'gemini', 'v3', etc.)
const prompt = 'Hey, how are you?'; // The user prompt
const chatOptions = {
  userId: '12345',        // Unique identifier for memory (e.g., user, server, or channel ID)
  memory: true,           // Enable memory to store conversation context
  limit: 12,              // Number of previous messages to recall (memory limit)
  instruction: 'You are a friendly assistant.', // Custom instruction for AI role-playing
  Api_key: 'your-optional-Api-key' // (Optional) Use your own API key
};

const chatResponse = await ApexChat(model, prompt, chatOptions);
console.log(chatResponse); // Logs the AI-generated text response
```

---

## ⚙️ **Parameters**

Here are the key parameters you can use to customize **ApexChat**:

| Parameter     | Description                                                                                   | Required | Default Value |
|---------------|-----------------------------------------------------------------------------------------------|----------|---------------|
| `model`       | Specifies the AI model (e.g., `'gemini'`, `'v3'`).                                             | Yes      | None          |
| `prompt`      | The input message or question from the user.                                                   | Yes      | None          |
| `userId`      | Unique identifier for memory retention (can be user, server, or channel ID).                   | No       | None          |
| `memory`      | Enables chat memory, allowing the AI to recall previous interactions.                          | No       | `false`       |
| `limit`       | The number of previous messages to recall from memory (works only if memory is enabled).       | No       | 10            |
| `instruction` | Custom system-level instruction that defines the AI’s behavior (e.g., as a specific character). | No       | None          |
| `Api_key`     | Optional API key if you want to use a different key for the current AI model.                  | No       | None          |

---

## 🌟 **Key Features**

### 🧠 **Memory Retention**
Enable memory to allow the AI to remember past interactions. Customize how much history is retained by adjusting the `limit`.

### 🎭 **Role-Playing & Custom Instructions**
Set up custom instructions to make the AI act as a particular character or take on a specific personality. For instance, you can make the AI respond like a helpful assistant or simulate an entirely different role.

### 🔑 **API Key Flexibility**
You can provide your own API key for the AI model, but all models come with their own default keys. If you'd like to use a specific key for any reason (e.g., rate limits or custom models), you can easily configure it.

---

## 📚 **How It Works**

1. **Input your AI model**: Choose from available models like `'gemini'`, `'v3'`, etc.
2. **Provide a prompt**: The AI will respond based on the input you give.
3. **Optional memory and instructions**: Enable memory to make the AI recall past interactions, and provide custom instructions to control the AI’s role.
4. **API Key**: Optional, but if provided, it will override the default key.

---

## 🎨 **Advanced Usage Example**

```javascript
const model = 'v3'; // Using the 'v3' chat model
const prompt = 'Tell me a story about a brave knight.'; // Custom user prompt
const chatOptions = {
  userId: 'guild-5678',     // Use a guild or channel ID for group-specific memory
  memory: true,             // Enable memory to retain the conversation context
  limit: 5,                 // Recall the last 5 messages from memory
  instruction: 'You are a storyteller. Speak in a medieval style.', // Custom instruction
  Api_key: ''               // Optional API key if using a custom model
};

const storyResponse = await ApexChat(model, prompt, chatOptions);
console.log(storyResponse); // AI-generated story based on custom instructions
```

---

## 📂 **Customization Options**

- **Flexible Memory**: Adjust how much of the conversation the AI should remember by setting a `limit`.
- **Dynamic Roles**: The `instruction` parameter lets you define a role for the AI, making it adaptable to different use cases.
- **User-Controlled API Keys**: Though models come with preconfigured keys, you can easily provide your own API key to override the defaults.

---

## 🛠 **Model & Configuration Settings**

- **AI Models**: The most popular models like `'gemini'`, `'v3'`, and others are available. Choose based on your needs.
- **Memory & Role-Playing**: Create rich, engaging conversations with the AI that can simulate personalities or stick to predefined instructions.
- **Optional API Key**: Use this only if you have specific requirements for using your own API keys with the AI models.

---

💡 **Pro Tip**: For more interactive chat experiences, experiment with role-playing characters using the `instruction` field! The AI can take on different personas, adding depth to your conversations.
