# Next Word Prediction - MDST Fall '23

This is a repository containing the work done for the Next Word Prediction project at the Michigan Data Science during the Fall semester of 2023. The project's main objective was to leverage machine learning methods to reliably generate the next word, or next *n* words, given a sequence of text. Generating conversational-like text or using transformer architecture were outside the scope of the project.

This repository contains several approaches to solving this task, using varied model architectures and datasets. We enumerate them below in the **Next Word Training Models** section. We also created front-end interfaces for getting predictions from the model, which are described in the **Streamlit** section.

## Next Word Training Models

Our approaches included using a LSTM neural network, and a simple n-gram model. Much of the focus of the project meetings were the LSTM. 

### 1. `models/LSTM_sherlock_model.ipynb`
Using a simple LSTM architecture, we trained a neural network on a Sherlock Holmes book. The predictions of the model were generally poor, and after many attempts of training and hyperparamter tuning, we failed to get the training accuracy above 25%. This motivated our search for other datasets, to see if we could achieve better performance.

### 2. `models/LSTM_amazon_reviews_model.ipynb`

### 3. `models/ngram_model.ipynb`
Using n-grams for predictions were never explicitly covered by the Fall '23 project, but is included in this repository for the sake of completeness. The Neural Net approaches all leveraged n-grams to generate input sequences that the models were trained on. But what if we cut out the neural net training process, and train the next word simply using next word probabilities derived from the n-grams themselves?

It turns out that the model performs quite well, generating sequences of text that make sense, but are most times ripped off completely from the training data. The model also cannot generalize at all outside of the given dataset.

### Conclusions
Surprisingly, LSTMs performed quite poorly. We would recommend using Transformer architecture to obtain competitive results in next word prediction.

## Streamlit

We took advantage of the easy-to-use Streamlit library in Python to create front-ends for the next word prediction models. The models are contained in the `streamlit/` directory. To run the apps and see them, `pip install streamlit` and `python -m streamlit run {path_to_file}`. 