# Outside Discord

## 

This script enables the ApexAI to process messages in a designated channel, perform tasks as image processing and chat processing outside discord.

#### Importing Functions

You need to import two main functions from `apexify.js`: `ApexChat` and `ApexImagine`.

+++ JS

```javascript
const { ApexChat, ApexImagine } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexChat, ApexImagine } from 'apexify.js'; 
```

+++

#### Generating AI Responses

##### ApexChat

The `ApexChat` function is used to generate AI-driven text responses. It takes a model and a prompt as input and returns a string response.

```javascript
const model = 'gemini';
const prompt = 'hey how r u?'
const chatreply = await ApexChat(model, prompt);
console.log(response); // Logs the AI-generated response as a string
```

##### ApexImagine

The `ApexImagine` function is used to generate AI-driven images. It takes a model, a prompt, and optional parameters as input and returns an array of image URLs.

```javascript
const model = 'prodia';
const prompt = 'draw a cat'
const imgURLS = await ApexImagine(model, prompt, { count: 2, nsfw: false, deepCheck: true, negative_prompt: 'not blur image', cfg_scale: 9, width: 1024, height: 1024, steps: 19, seed: -1, sampler: "DPM-Solver", image_style: "Cinematic" });
console.log(imageUrls); // Logs an array of image URLs
```

### Parameters

When using `ApexImagine`, you can provide optional parameters:

| Parameter       | Description                                    | Default Value |
|-----------------|------------------------------------------------|---------------|
| `number`        | Number of images to generate                   | 1             |
| `negative`      | Negative prompt for generating contrasting images | null          |

### Example

Let's put it all together in a practical example:

```javascript
// Generating AI chat
const chatModel = 'model_name'; // Specify your chat model name
const chatPrompt = 'Hello, how can I help you?'; // Your chat prompt
const chatResponse = await ApexChat(chatModel, chatPrompt);
console.log(chatResponse); // Logs the AI-generated response

// Generating AI images
const imageModel = 'model_name'; // Specify your image model name
const imagePrompt = 'A beautiful landscape'; // Your image prompt
const imageCount = 3; // Number of images to generate
const imageNegativePrompt = 'A dark and gloomy landscape'; // Negative prompt for contrasting images
const imageUrls = await ApexImagine(imageModel, imagePrompt, { number: imageCount, negative: imageNegativePrompt });
console.log(imageUrls); // Logs an array of image URLs
```

This example demonstrates how to use both `ApexChat` and `ApexImagine` functions with appropriate prompts and parameters. Adjust the model names, prompts, and parameters according to your specific use case.