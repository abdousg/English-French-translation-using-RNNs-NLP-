# Neural Machine Translation: English to French (NLP Project)

This project, developed by Abdoulaye Gaye, focuses on building and evaluating a neural machine translation (NMT) model that translates English sentences into French. It leverages state-of-the-art Natural Language Processing techniques, including sequence-to-sequence (seq2seq) models with attention mechanisms.

## Objective

The goal is to improve the quality of English-French translation by developing models that better handle context, idiomatic expressions, and sentence structure. The project compares two architectures: a simple RNN with LSTM units, and an RNN with attention layers.

## Dataset

The dataset used consists of 178,000 pairs of English and French sentences, sourced from Kaggle. For performance reasons, a subset of 10,000 sentence pairs was used. Each pair contains:
- An English sentence or phrase
- Its corresponding French translation

## Data Preparation

1. **Cleaning:** Text was converted to lowercase, diacritics and special characters removed.
2. **Tokenization:** Performed using spaCy for both English and French.
3. **Annotation:** `<start>` and `<end>` tokens added to help train the seq2seq model.
4. **Splitting:** Dataset divided into training (80%) and validation (20%) sets using `train_test_split`.

## Data Analysis

- Most sentences contain between 2 and 3 words.
- Common words in English: "I", "you", "it", "is"
- Common words in French: "je", "suis", "nous", "pas"
- The dataset contains mostly short, conversational phrases.

## Model Architectures

### 1. RNN with LSTM Units
- Encoder and decoder based on LSTM layers
- Embedding layers to transform words into dense vectors
- Trained using `sparse_categorical_crossentropy` loss and `Adam` optimizer

### 2. RNN with Attention Mechanism
- Same base as above, with the addition of an attention layer
- Attention provides context at each decoding step, improving translation accuracy

## Training & Evaluation

- Both models trained for 10 epochs
- Evaluation metrics:
  - **RNN with Attention:** Precision: 89%, Loss: 62%
  - **RNN with LSTM only:** Precision: 88%, Loss: 65%

### Sample Translation Results

| Input                    | RNN + Attention       | RNN Only                    |
|-------------------------|-----------------------|-----------------------------|
| "How are you doing?"    | "ça va"               | "est-ce que tu le fais"     |
| "You cannot hear me"    | "pas de me ne pas entendu" | "tu ne m'as pas entendu" |

## Conclusion

- The attention-based model outperforms the LSTM-only model in general metrics, but translation quality varies by example.
- Performance is limited by dataset size and sentence complexity.
- Future improvements could include:
  - Using larger or more diverse datasets
  - Fine-tuning embeddings
  - Increasing the number of epochs

## Author

**Abdoulaye Gaye**  
Master's in Economics and Financial Engineering – Université Paris Dauphine  
Machine Learning & NLP Enthusiast
