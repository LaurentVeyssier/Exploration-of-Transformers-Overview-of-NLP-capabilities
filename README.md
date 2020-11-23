# Exploration-of-Transformers---Overview-of-the-capabilities
Testing of the possible use of transformers model for various NLP tasks.

The notebook tries the various tasks offered by Transformers architecture as described on Hugginface [here](https://huggingface.co/transformers/v3.1.0/task_summary.html).


The notebook tests various pretrained models from Hugginface: BERT, GPT2, XLNet... 

The tests are provided for both Pytorch and Tensorflow.

Summary of the tasks implemented in the notebook:
- Sequence classification
  - Sentiment analysis
  - Paraphrase detection
- Extractive Question-Answering. Note this is an extractive version of Q&A.
- Language Modelling
  - Masked language modeling:  mask tokens in a sequence, and prompt the model to fill that mask with appropriate word
  - Causal Language Modeling: predict the next word in a sequence
  - Text generation using XLNet. The goal is to create a coherent portion of text that is a continuation from the given context.
- Named Entity Recognition (NER)
- Text summarization
  - pure extractive method
  - method which appears to combine extractive AND generative using the latest powerful Google t5 model. Refer to a previous analysis in a previous project [here]().
  

Results
- the results are quite impressive for text generation and translation. Both pieces display excellent quality.
- the text generation develops human-like story on its own based on the context which the user provides. "Padding text" is provided along the prompt submitted to the model as primer. "Padding" text is reported to help XLNet with short prompts, reducing the risk of meaningless predictions. Check [here](https://github.com/rusiaaman/XLNet-gen#methodology) for details. XLNet is a novel permutation based language model. XLNet is trained to predict 85 tokens at a time out of 512 in a single example. The rest of the 512-85 = 427 tokens can attend to each other in the attention mechanism (bidrectional attention).
