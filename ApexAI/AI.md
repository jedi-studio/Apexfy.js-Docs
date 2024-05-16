# ApexAI

This script enables the `ApexAI` to process messages in a designated channel, perform various tasks including `voice processing`, `image processing`, `chat processing`, and more.

## Installation

1.**Import the `ApexAI` function** from the `apexify.js` library:

+++ JS

```javascript
const { ApexAI } = require('apexify.js'); 
```

+++ TS

```typescript
import { ApexAI } from 'apexify.js'; 
```

+++

## Usage

### Voice Processing

Use the following code to enable voice processing:

- **voice_code:** Is the language code and voice speech. You may find more at voice modals in previews & samples in ApexAI section.
- **apiKey:** The key for the api for apexAI and zenithAI voiceModal. You can purchase a key by contacting us on discord on the server.
- **type:** The person either man/woman and old/teen/adult.

```javascript
const { ApexAI } = require('apexify.js');

client.on('messageCreate', async (message) => {
  if (message.author.bot) return;

  const aiOptions = {

    voice: {
      textVoice: {
        enable: true,
        voiceModal: "google",
        voice_code: "en-US-3",
        apiKey: "your-api-key",
        type: "b"
      }
    }
  };

  await ApexAI(message, aiOptions)
});
```

### Image Processing

Use the following code to enable image processing:

- **drawTrigger:** The key word that triggers imagine.
- **imageModel:** The modal that will be used for generating images. There is plenty of them please check modals at previews & samples in ApexAI section
- **numOfImages:** Number of the generated images. The limit is 4.
- **nsfw:** To enable anitNSFW. Making sure generated images doesnt contain nsfw. You can add your own keywords or keep it empty array to use default words.
- **enhancer:** To enhance your prompt making it more descriptive and better visiualizing and to appy art into it.

`Note That:` drawTrigger is the first word of your message.

```javascript
const aiOptions = {
  imagine: {
    enable: true,
    drawTrigger: ["create", "رسم"],
    imageModel: "prodia",
    numOfImages: 2,
    nsfw: {
      enable: false,
      keywords: ['first word', 'second word']
    },
    enhancer: {
      enable: false,
      enhancerModal: 'ESRGAN_4x',
      negative_prompt: '',
      cfg_scale: 7,
      sampler: 'DDIM',
      steps: 20,
      seed: -1,
      imgStyle: 'enhance'
    }
  }
};
```

### Chat Processing

Use the following code to enable chat processing:

- **chatModel:** The chat model of the ai. There is plenty of them please check modals at previews & samples.
- **readFiles:** To read files such as PDF/TXT. Soon will read ppt & docs files.
- **readImages:** Without enabling it the ai read images but only those with text on them. If images you will provide contains no text it would be better to enable this.
- **API_KEY:** Add your own key if using gemini-pro/gemini-flash. Add your own key in case you only recieved rate limit.
- **personality:** Personalize your ai. Create a text file add the personality then define its path and add it.
- **memory:** To enable memory into your ai and remember chat history. You can add in id either server/channel/user ID.
- **TypeWrting:** To enable the ability to text like real ai bot.


```javascript
const aiOptions = {
  chat: {
    chatModel: "v3",
    readFiles: true,
    readImages: false,
    API_KEY: '',
    personality: '',
    memory: {
      memoryOn:  false,
      id: ''
    },
    typeWriting: {
      enable: false,
      speed: 70,
      delay: 2000
    }
  }
};
```

### Other Options

Additional options for configuring keyword responses, loader messages, channel settings, and permissions:

- **messageType:** Clarify the type of message either `send` or `reply` and add intital message content in bot response as you like.
- **buttons:** To add buttons to the generated message.
- **keywords && keywordResponses:** Make the ai reply to specific prompt with specific custom replies
- **loader:** The intial message being sent before response.
- **channel:** Specifying the channels for ai to work at.
- **permissions:** Specifying the permissions that ai will respond to and blacklist user/roles

```javascript
const aiOptions = {
  others: {
    messageType: {
      type: 'send',
      intialContent: `<@${message.author.id}>,`
    },
    buttons: [row1, row2],
    keywords: ["help", "info"],
    keywordResponses: {
      'help': "I'm here to assist you!",
      'info': "Here is some information for you."
    },
    loader: {
      enable: true,
      loadingMessage: "Please wait while I process your request...",
      loadingTimer: 5000
    },
    channel: {
      enable: true,
      id: ['id1', 'id2']
    },
    permissions: {
      enable: true,
      role: ['id1', 'id2'],
      permission: ['ManageGuild', 'SendMessages'],
      blockedUsers: ['user1', 'user2']
    }
  }
};
```

## Combined Options

- You can combine voice processing, image processing, chat processing, and other options in a single `aiOptions` object:

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
    // Image processing options...
  },
  chat: {
    // Chat processing options...
  },
  others: {
    // Other options...
  }
};
```

## Features

- **Voice Processing:** Enable voice processing with options to specify voice modal, language, and API key.
- **Image Processing:** Enable image processing with options for drawing triggers, image models, number of images, and more.
- **Chat Processing:** Enable chat processing with options for chat model, reading files/images, and type writing.
- **Keyword Responses:** Define specific keywords and their corresponding responses.
- **Loader Message:** Display a loading message while processing requests.
- **Channel Configuration:** Specify channels for the bot to chat in.
- **Permissions:** Configure permissions for the bot to respond to specific roles and users.


### Other Moudles Usages:

==- ApexImagen & ApexChat

1.**ApexChat:**
```js
    const { ApexChat } = require('apexify.js');
    
    await interaction.deferReply()
    const modal = interaction.options.getString('modal');
    const prompt = interaction.options.getString('prompt');


      const response = await ApexChat(modal, prompt);

      await interaction.editReply({ content: `${response}` });
```

2.**Valid Chat Modals:**

- v3, v3-32k
- turbo, turbo-16k
- gemini, apexChat
- yi-ai, facebook-ai
- starChat, gemini-pro
- gemini-flash

| Name       | Type     | Required | Description                       |
| :---       | :---:    | ---                               |
| `response` | `string` | True | The response generated by the AI. |
| `modal`    | `string` | True | The modal used by the AI.         |
| `prompt`   | `string` | True | The prompt provided by the user.  |


3.**ApexImagine:**
```js
await interaction.deferReply();

const modal = interaction.options.getString('modal');
const prompt = interaction.options.getString('prompt');
const count = interaction.options.getInteger('count');
const negativePrompt = interaction.options.getString('negative') || '';


  const response = await ApexImagine(modal, prompt, { number: count, negative: negativePrompt });
  const uniqueUrls = new Set(response);

  const attachments = Array.from(uniqueUrls).map(url => new AttachmentBuilder(url));

  await interaction.editReply({ files: attachments });
```

4.**Valid Imagine Modals:**

- lexica, prodia 
- animefy, raava 
- shonin 

!!!info
More valid imagine modals at Previews & Samples section.
!!!

| Name       | Type     | Required | Description                       |
| :---       | :---:    | ---                               |
| `response` | `string` | True | The images generated by the AI. |
| `modal`    | `string` | True | The modal used by the AI.         |
| `prompt`   | `string` | True | The prompt provided by the user.  |
| `number`   | `number` | false | Number of images to generate.  |
| `negative`   | `string` | false | The negative prompt provided by the user.  |

===
