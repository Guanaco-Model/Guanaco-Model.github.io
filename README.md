# Guanaco - Generative Universal Assistant for Natural-language Adaptive Context-aware Omnilingual outputs
Our new 🏆SOTA work: [CausalLM](https://causallm.org/) 72B(preview), 14B & 7B, #1 SOTA model of its size, outperforming ALL open models.

**Recent update:** Added support for multimodal VQA.

Guanaco is an advanced instruction-following language model built on Meta's LLaMA 7B model. Expanding upon the initial 52K dataset from the Alpaca model, an additional 534,530 entries have been incorporated, covering English, Simplified Chinese, Traditional Chinese (Taiwan), Traditional Chinese (Hong Kong), Japanese, Deutsch, and various linguistic and grammatical tasks. This wealth of data enables Guanaco to perform exceptionally well in multilingual environments.

In an effort to foster openness and replicability in research, we have made the [Guanaco Dataset](https://huggingface.co/datasets/JosephusCheung/GuanacoDataset) publicly accessible and released the [model weights](https://huggingface.co/JosephusCheung/Guanaco). By providing these resources, we aim to inspire more researchers to pursue related research and collectively advance the development of instruction-following language models.

When utilizing the Guanaco model, please bear in mind the following points:

- The Guanaco model has not been filtered for harmful, biased, or explicit content. As a result, outputs that do not adhere to ethical norms may be generated during use. Please exercise caution when using the model in research or practical applications.

## 1. Improved context and prompt role support:

The new format is designed to be similar to ChatGPT, allowing for better integration with the Alpaca format and enhancing the overall user experience.

Instruction is utilized as a few-shot context to support diverse inputs and responses, making it easier for the model to understand and provide accurate responses to user queries.

The format is as follows:

```
### Instruction:
User: History User Input
Assistant: History Assistant Answer
### Input:
System: Knowledge
User: New User Input
### Response:
New Assistant Answer
```

This structured format allows for easier tracking of the conversation history and maintaining context throughout a multi-turn dialogue.

## 2. Role-playing support:

Guanaco now offers advanced role-playing support, similar to Character.AI, in English, Simplified Chinese, Traditional Chinese, Japanese, and Deutsch, making it more versatile for users from different linguistic backgrounds.

Users can instruct the model to assume specific roles, historical figures, or fictional characters, as well as personalities based on their input. This allows for more engaging and immersive conversations.

The model can use various sources of information to provide knowledge and context for the character's background and behavior, such as encyclopedic entries, first-person narrations, or a list of personality traits.

The model will consistently output responses in the format "Character Name: Reply" to maintain the chosen role throughout the conversation, enhancing the user's experience.

## 3. Rejection of answers and avoidance of erroneous responses:

The model has been updated to handle situations where it lacks sufficient knowledge or is unable to provide a valid response more effectively.

Reserved keywords have been introduced to indicate different scenarios and provide clearer communication with the user:

- NO IDEA: Indicates that the model lacks the necessary knowledge to provide an accurate answer, and will explain this to the user, encouraging them to seek alternative sources.
- FORBIDDEN: Indicates that the model refuses to answer due to specific reasons (e.g., legal, ethical, or safety concerns), which will be inferred based on the context of the query.
- SFW: Indicates that the model refuses to answer a question because it has been filtered for NSFW content, ensuring a safer and more appropriate user experience.

## 4. Continuation of responses for ongoing topics:

The Guanaco model can now continue answering questions or discussing topics upon the user's request, making it more adaptable and better suited for extended conversations.

The contextual structure consisting of System, Assistant, and User roles allows the model to engage in multi-turn dialogues, maintain context-aware conversations, and provide more coherent responses.

The model can now accommodate role specification and character settings, providing a more immersive and tailored conversational experience based on the user's preferences.

It is important to remember that Guanaco is a 7B-parameter model, and any knowledge-based content should be considered potentially inaccurate. We strongly recommend providing verifiable sources, such as Wikipedia, for knowledge-based answers. In the absence of sources, it is crucial to inform users of this limitation to prevent the dissemination of false information and to maintain transparency.

## 5. Multimodal Visual Question Answering (VQA) Support:

Guanaco expands its capabilities into the realm of multimodal interactions, now offering support for Visual Question Answering (VQA). The model achieves this by integrating data from the blip2-flan-t5-xxl for multilingual VQA tasks, marking a significant milestone in the development of multimodal chatbots.

This new feature allows the model to interpret and respond to queries that involve both text and visual inputs, providing a richer, more interactive, and comprehensive user experience. Users can now ask questions about an image, and the model will analyze the visual content in conjunction with the textual query to provide a response.

A noteworthy addition is the [Guanaco VQA Dataset](https://huggingface.co/datasets/JosephusCheung/GuanacoVQADataset), publicly accessible now.

Now as a multimodal chatbot, Guanaco can bridge the gap between visual and linguistic understanding, making it an incredibly versatile tool for a wide array of applications.

However, as always, we encourage responsible and ethical use of this model. Please note that while Guanaco strives to provide accurate and helpful responses, it is still crucial to cross-verify the information from reliable sources for knowledge-based queries.
