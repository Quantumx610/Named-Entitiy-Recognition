# Named Entity Recognition (NER) using Bidirectional LSTM and LSTM

This project demonstrates the implementation of a Named Entity Recognition (NER) model using a combination of Bidirectional LSTM and LSTM layers in TensorFlow. The model is trained on a dataset of sentences and their corresponding tags, and can be used to identify named entities in new text.

## Dataset

The dataset used for training and evaluating the model is a CSV file containing the following columns:

* Sentence #: Sentence number
* Word: The word itself
* POS: Part-of-speech tag
* Tag: Named entity tag

## Model Architecture

The model consists of the following layers:

* Embedding layer: This layer converts each word in the input sequence into a vector of a specified size.
* Bidirectional LSTM layer: This layer processes the input sequence in both forward and backward directions, capturing context from both sides of each word.
* LSTM layer: This layer further processes the output of the Bidirectional LSTM layer, capturing long-term dependencies in the sequence.
* TimeDistributed Dense layer: This layer applies a dense layer to each time step of the output of the LSTM layer, predicting the tag for each word.

  [Model Architecture](model.png)
  
## Training

The model is trained for 25 epochs, with a batch size of 1000. The Adam optimizer and categorical cross-entropy loss function are used.

## Evaluation

The model is evaluated on a held-out test set, and the results are saved to a Pandas DataFrame.

## Usage

To use the model to identify named entities in new text, simply pass the text to the `nlp` object. The `displacy` library can then be used to visualize the results.
