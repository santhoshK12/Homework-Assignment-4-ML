# Homework 4 – NLP & Clustering

## Student Information
Name: Santhosh Reddy Kistipati  
Course: Machine Learning 
Assignment: Homework 4 – Clustering, NLP Theory, and Coding
Easyly access the whole content throw the link in brightspace : https://github.com/santhoshK12/Homework-Assignment-4-ML/tree/main

---

## Repository Contents
- Homework_4_ML.pdf  
  Contains all written theory answers:
  • Part A – Hierarchical clustering calculations (MIN & AVERAGE)  
  • Part B – Conceptual questions: attention, positional encoding, fairness, AI harm  
- home_assignment_4_coding_answers_ml.py  
  Python script for all coding questions in Part C.

---

## Part A – Clustering (Q1)

### What I Did
1. Computed Euclidean distance between all pairs of points P1–P7 using  
   d(Pi,Pj) = sqrt((xi−xj)² + (yi−yj)²).  
   Filled the complete 7×7 distance matrix.

2. Performed MIN (single-link) hierarchical clustering:  
   • At each step, identified the smallest distance.  
   • Merged the closest clusters.  
   • Updated the distance matrix using:  
     d(A∪B, C) = min(d(A, C), d(B, C)).  
   • Recorded merge heights and drew the MIN dendrogram with correct ordering.

3. Performed AVERAGE linkage clustering (centroid distance):  
   • After every merge, computed centroid of the new cluster.  
   • Recalculated distances to other clusters using centroid distances.  
   • Updated matrices, recorded merge heights, and drew the AVERAGE dendrogram.

4. Added all matrices, merge steps, and final dendrograms in the PDF.

---

## Part B – Theory Questions (Q2 & Q3)

### Topics Covered
1. Hierarchical Clustering  
   • Explained agglomerative clustering (bottom-up).  
   • Discussed how different linkage types change cluster formation.  
   • Explained dendrogram interpretation.

2. Scaled Dot-Product Attention & Positional Encoding  
   • Provided the attention formula.  
   • Explained Q, K, V vectors.  
   • Explained why positional encoding is required and gave the sine/cosine formulas.  
   • Clarified the meaning of d_model.  
   • Compared Transformer encoder vs decoder and explained masked self-attention.

3. AI Harm, Fairness, Privacy  
   • Defined black-box API in model-stealing context.  
   • Explained why fairness cannot be solved fully in one model.  
   • Listed harms: misinformation, privacy leakage, biased predictions.  
   • Mentioned mitigation strategies: filtering, evaluation benchmarks, regulations.

All explanations are included in the PDF in clear paragraph form.

---

## Part C – Coding (Q1 & Q2)
All code is in: `home_assignment_4_coding_answers_ml.py`.

### Dependencies
Install spaCy and the English model:
```bash
pip install spacy
python -m spacy download en_core_web_sm
```

### How to Run the Script
```bash
python home_assignment_4_coding_answers_ml.py
```

The script executes both coding questions automatically.

---

## Coding Question 1 – Tokenization, Stopwords, Lemmatization, POS Filtering

### What the Code Does
1. Loads spaCy model:
```python
import spacy
from spacy.lang.en.stop_words import STOP_WORDS
nlp = spacy.load("en_core_web_sm")
```

2. Input text is processed using spaCy:
```python
text = "John enjoys playing football while Mary loves reading books in the library."
doc = nlp(text)
```

3. Performs:
   • Tokenization  
   • Stopword removal  
   • Lemmatization using token.lemma_  
   • POS filtering (keeps only NOUN and VERB)

4. Prints:
   • All tokens  
   • Tokens without stopwords  
   • Final list of lemmatized nouns and verbs

This fully completes Q1 requirements.

---

## Coding Question 2 – NER + Pronoun Ambiguity Warning

### What the Code Does
1. Defines input text:
```python
text = "Chris met Alex at Apple headquarters in California. He told him about the new iPhone launch."
doc = nlp(text)
```

2. Runs NER:
```python
for ent in doc.ents:
    print(f"{ent.text} --> {ent.label_}")
```

3. Checks for ambiguous pronouns:
```python
pronouns = {"he", "she", "they", "him", "her", "them"}

if any(token.text.lower() in pronouns for token in doc):
    print("Warning: Possible pronoun ambiguity detected!")
```

4. Outputs:
   • All named entities  
   • A warning if pronouns indicating possible ambiguity appear

This completes Q2 requirements exactly as stated in the assignment.

---

## Summary
- Part A: Full hierarchical clustering calculations and dendrograms included in the theory PDF.  
- Part B: All conceptual and short-answer theory questions answered in the PDF.  
- Part C: Python script implements NLP pipelines for tokenization, stopwords, lemmatization, POS tagging, NER, and pronoun-ambiguity detection.

This README explains how each part was solved and how to execute the code.
# Homework-Assignment-4-ML
