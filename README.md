# QuestionAnswering
This repository contains the code for fine-tuning 2 models: T5 (Text-To-Text-Transformer) and BERTforQuestionAnswering on the SQuAD dataset for question answering

## Test-To-Text-Transformer (T5)
T5 is a generative model that has been used for the question answering task in this project. The model was trained using the T5TokenizerFast for efficient tokenization and initialized with a sequence length of 256 for questions and 32 for answers.  Adam optimizer with a learning rate of 0.00001 was used to train the model on a GPU (cuda:0) with a batch size of 10.

## BERTforQuestionAnswering
BERTforQuestionANswereing is a model based on BERT for question answering. The model was initialized using the AutoTokenizer and AutoModelForQuestionAnswering classes from the Hugging Face Transformers library. The training data was processed by tokenizing the questions and context passages with a maximum length of 384 tokens, while ensuring appropriate handling of answer spans using a stride of 128.

The model's training focused on accurately identifying the start and end positions of answers within the context. Special handling was implemented for cases where the answer was not contained within the given span, mapping such cases to the [CLS] token.

