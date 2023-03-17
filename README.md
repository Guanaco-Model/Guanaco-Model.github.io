# Guanaco: A Multilingual Instruction-Following Language Model Based on LLaMA 7B

As artificial intelligence technology rapidly advances, instruction-following language models have made significant progress in both academia and industry. In this context, we introduce a new language model called "Guanaco" to support a broader range of research and applications. Here is a brief overview of the Guanaco model.

## Model Overview

Guanaco is an instruction-following language model trained on Meta's LLaMA 7B model. Building upon the original 52K data from the Alpaca model, we added an additional 54,574 entries, covering Simplified Chinese, Traditional Chinese (Taiwan), Traditional Chinese (Hong Kong), and various linguistic and grammatical tasks. By retraining and optimizing the model with this rich data, Guanaco demonstrates excellent performance and potential in a multilingual environment.

## Dataset and Model Weights

To promote openness and replicability in research, we have made the [Guanaco Dataset](https://huggingface.co/datasets/JosephusCheung/GuanacoDataset) publicly available and plan to release the model weights in the future. By providing these resources, we hope to encourage more researchers to engage in related research and jointly advance the development of instruction-following language models.

The Guanaco model is designed to work well with instruction-following question-answering tasks and continuous conversations. For standard instruction-following QA tasks, use the following template:

```
Below is an instruction that describes a task, paired with an input that provides further context. Write a response that appropriately completes the request.

### Instruction:
{instruction}

### Input:
{input}

### Response:
```

For continuous conversations, adopt the following strategy:

1. Maintain a conversation context window of adjustable length within the Instruction, containing past dialogue records. The dialogue roles are User (for the person asking questions) and Assistant (for the one providing answers).
2. The Input is divided into two parts: a. The System role provides factual information. This information can come from web search data, full-text search or vector search engines, or other knowledge APIs. b. The User role includes the new question in the ongoing conversation.
3. In the Response, the Assistant role answers the question by: a. Adhering to the context provided in the Instruction. b. Strictly following the guidance of the System role to provide accurate information. c. Responding to the User's new question from the Input.

This approach yields better performance on small models compared to using embedded span toolformer structures.

## Precautions

When using the Guanaco model, please note the following points:

The Guanaco model has not yet been filtered for harmful, biased, or explicit content. During use, outputs that do not conform to ethical norms may be generated. Please pay special attention to this issue in research or practical applications.

## Scope of Application

The Guanaco model aims to promote academic research on instruction-following language models and help researchers gain deeper insights into and improve the performance of these models. Please note that the Guanaco model is intended for academic research purposes only and is prohibited for any commercial use.

