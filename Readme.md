# RAG (Retrieval-Augmented Generation)

## Week 1

### RAG Introduction

1. What is RAG  
2. Prompt Creating Using Relevant Documents/Data  
3. Why Do We Need  
   - Latest Information (Transformers are trained on data up to specific years)
   - Private and Sensitive Data
   - Reduce Hallucinations in Transformers  

4. Simple Flow  


---

## Week 2

### Information Retrieval and Search Foundation

1. Keyword Search  
- Word Matching  

2. Semantic Search  
- Similar meaning without matching words  

3. Metadata Filtering  
- Excludes documents based on rigid criteria  
- Does not perform retrieval  
- Narrows results based on user attributes, not query  

4. Keyword Search: TF-IDF (Term Frequency – Inverse Document Frequency)

**Bag of Words**
- Vector size = vocabulary size  
- Each index represents frequency of a word in the document (0 if absent)


- All vectors have the same size (vocabulary size = m)
- Matrix size = m × n  
  - Columns → documents  
  - Rows → word frequencies  

**Example Query:** `Hello World`

- Check rows for `Hello` and `World`
- Frequency > 0 → 1, else 0
- Score per document:
  ```
  column.sum() / vocab_size
  ```

**Cons**
- Word presence matters, not frequency  

**Term Frequency (TF)**
- Captures word frequency
- Sum frequencies across columns
- Normalize by number of words in document  

**Cons**
- Common and rare words treated equally  

**Document Frequency (DF)**
DF = Number of documents containing word / Total documents

**Inverse Document Frequency (IDF)**
IDF = log(1 / DF)


**TF-IDF**
TF-IDF = TF Matrix × IDF Matrix

5. BM25 (Best Matching 25)

- Ranking function derived from TF-IDF  

**Improvements**
- Term Frequency Saturation  
- Document Length Normalization (better than simple length division)

