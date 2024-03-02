# Resume-Revealer
# CV Parsing using spaCy 3

This project focuses on parsing and extracting information from resumes (CVs) using spaCy 3, a powerful natural language processing library. The project utilizes spaCy's transformer-based model, specifically RoBERTa, for general language understanding and a named entity recognition (NER) component for identifying entities in text.

## Project Overview

The project consists of the following components:

1. *Model Architecture:*
    - *Transformer-Based Model:*
        - *Architecture:* 'spacy-transformers.TransformerModel.v3'
        - *Name:* 'roberta-base'
        - *Tokenizer Configuration:* {"use_fast": true}
    - *NER Model:*
        - *Architecture:* 'spacy.TransitionBasedParser.v2'
        - *Parameters:* state_type, extra_state_tokens, hidden_width, maxout_pieces, use_upper, nO

2. *Dependencies:*
    - spaCy 3
    - spaCy Transformers
    - tqdm
    - json
    - PyMuPDF
    - scikit-learn

## Setup

1. Install the required packages:

    bash
    !pip install spacy_transformers
    !pip install -U spacy
    !pip install PyMuPDF
    

2. Clone the repository:

    bash
    git clone https://github.com/yourusername/CV-Parsing-using-Spacy-3.git
    cd CV-Parsing-using-Spacy-3
    

3. Download the pre-trained transformer model (roberta-base) for spaCy:

    bash
    python -m spacy download roberta-base
    

4. Run the main script to train the model and generate predictions:

    bash
    python your_main_script.py
    

## Training and Evaluation

- The project includes a training script (python -m spacy train) using the provided configurations (config.cfg).
- Training and test data are split using scikit-learn's train_test_split.
- The trained model is saved, and you can load it for making predictions on new data.

## Inference

- Load the trained model using spaCy (spacy.load).
- Use the model to process text data and extract named entities.

## Example Usage

```python
import spacy

nlp = spacy.load('path_to_your_trained_model')
doc = nlp('Hello, My name is Arham. I had worked at Revelio Labs Private LTD.')

for ent in doc.ents:
    print(ent.text, " --------> ", ent.label_)
