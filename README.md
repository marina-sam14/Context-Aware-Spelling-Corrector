# Context-Aware-Spelling-Corrector

This academic project is the result of our efforts to create a context-aware spelling corrector using n-grams. The following steps outline what we did in this project:

## N-gram Language Models

We implemented bigram and trigram language models using Laplace smoothing (or Kneser-Ney smoothing for advanced users).
We started each sentence with a pseudo-token "start" (or "start1" and "start2" for trigram models) and ended with "end".
We created a vocabulary consisting of words that occurred at least 10 times in the training subset.
We replaced out-of-vocabulary (OOV) words with the special token "UNK".

## Cross-Entropy and Perplexity

We calculated the language cross-entropy and perplexity on a test subset, treating it as a single sequence of sentences.
We excluded probabilities related to start tokens but included probabilities for end tokens.
We counted end tokens but not start, start1, or start2 tokens in the total test corpus length.

## Tuning
We conducted hyperparameter tuning to optimize the performance of our language models.

## Autocompletion

We developed code to demonstrate how bigram and trigram models can autocomplete incomplete sentences.
We generated completions using the most probable next word according to the language model.
Optionally, we explored advanced techniques like beam search or sampling methods for text generation.

## Context-Aware Spelling Corrector

We created a spelling corrector using n-gram language models, a beam search decoder, and formulae for context-aware correction.
We considered the inverse of the Levenshtein distance as a similarity measure.
We fine-tuned hyperparameters to balance the importance of language model scores and error probabilities.

## Test Dataset

We generated an artificial test dataset to evaluate the spelling corrector.
We introduced small probability-based character replacements to mimic spelling errors in the test sentences.

## Evaluation

We evaluated the spelling corrector in terms of Word Error Rate (WER) and Character Error Rate (CER) using the original, unaltered test dataset as the reference.
We calculated WER and CER metrics, considering both word-level and character-level evaluation.
