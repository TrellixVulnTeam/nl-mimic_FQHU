# Predicting What Someone Would Say

This is a compilation of my attempts at solving this problem -- predicting what someone might say, based on what they have said in the past. I update this once in a while, when I get new ideas or more experience. Here is a summary of the attempts I have made so far:

### Attempt #1 - 2/20/2022

Took a very convoluted approach. Created two classes, a word `link` and a `pool` of word links. Links contain two words which appeared consecutively in the input text, and the pool contains all the possible links for the text. To obtain a result, I traverse these links both stochastially and deterministically, noticing that doing so deterministically stabilizes the model in word cycles.

Then, I tried to transform this into what I would later find out is an adjacency matrix, which was preprocessed. Sadly, it did not have the improved performance I believed it would have when it came to making predictions.

### Attempt #2 - 8/15/2022

I found out that Markov Chains are indeed just directed graphs of states. So, I planned a solution similar to the adjacency matrix, except this time I used an adjacency list to form the digraph. It turned out much more elegant, and had the desired improvement in performance. It might just be me, but the predictions also seem a bit more accurate (perhaps as an artifact of a better use of random choices to better represent edge weights).
