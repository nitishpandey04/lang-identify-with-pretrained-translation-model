# lang-identify-with-pretrained-translation-model
Training model to identify/classify the language script using pretrained multilingual translation models.

Problem:
Existing language identification models like [fasttext](https://github.com/facebookresearch/fastText) is not accurate in various usecases. 

Solution:
Train a custom language identification model using a pretrained base model which understands the nuances of various languages. 

- The task is to identify the language given a sentence of a particular language.
- I train a classification model using pretrained translation models like [NLLB](https://huggingface.co/facebook/nllb-200-distilled-600M) and [Madlad](https://huggingface.co/google/madlad400-3b-mt) as the base model.
- Experimented with hyperparameters like number of additional classification layers, batch size, etc.

The code uses [pytorch](https://github.com/pytorch/pytorch) library for training. Familiarity with basic `pytorch` will be helpful in following the code.
