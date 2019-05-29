# Game-of-thrones-bot

<p>The first Chat bot uses seq2seq model. Primarily, the words of questions and answers are not exactly the same in most circumstances. 
Besides, the answer given by a chat bot results from the last two related conversations. 
Consequently, to generate a needed response, we use LSTM (Long Short-Term Memory), which is a variant of the RNN (Recurrent Neural Networks). 
While the keras library provides the necessary functions for implementation, some basic libraries such as NLTK, Numpy are also needed.<p>

## Data
<p>I use data from https://genius.com/ by scraping scripts of game of thrones

## Archirecture
<p>The architecture presented here assumes the same prior distributions for input and output words. Therefore, it shares the embedding layer (Glove pre-trained word embedding) between the encoding and decoding processes through the adoption of a new model. To improve the context sensitivity, the thought vector (i.e. the encoder output) encodes the last two utterances of the conversation up to the current point. To avoid forgetting the context during the answer generation, the thought vector is concatenated to a dense vector that encodes the incomplete answer generated up to the current point. The resulting vector is provided to dense layers that predict the current token of the answer.
