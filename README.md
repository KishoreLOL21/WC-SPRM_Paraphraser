#  WC-SPRM: Lightweight Word Cloud-Based Paraphraser

WC-SPRM (**Word Cloud Synonym-based Paraphrasing using Radial Mapping**) is a lightweight, interpretable paraphrasing model designed to generate semantic paraphrases efficiently by leveraging synonym embeddings within a controlled vector space. It provides a fast and compact alternative to traditional heavy-weight language models.

---

##  Overview

WC-SPRM builds a paraphrasing system in 4 major stages:

1. **Word Embedding Generation**: 
   - Uses a modified Skip-Gram model trained with MSE loss to generate custom word embeddings.

2. **Word Cloud Creation**: 
   - For each parent word, synonyms are retrieved and mapped within a radius of 0.2 in the embedding space using perturbation logic.

3. **Model Training**: 
   - A Feed Forward Neural Network (FFNN) is trained to learn the transformation from parent embedding to synonym embeddings.

4. **Paraphrasing Engine**: 
   - Uses the trained model to paraphrase sentences by replacing words with their closest synonym embeddings in real-time.

---

##  Features

- ✅ Custom word embeddings
- ✅ Synonym cloud formation using Word2Vec & Datamuse API
- ✅ Synonym embedding prediction using FFNN
- ✅ Real-time word-level sentence paraphrasing
- ✅ Evaluation using Sentence-BERT cosine similarity
- ✅ Performance benchmarking with Word2Vec, GloVe, FastText
- ✅ Visualizations of word clouds and timing comparisons

---

##  Project Structure

<pre lang="markdown"> ```WC-SPRM/ │
   ├── Dataraw/ │ 
      ├── Augmented_Dataset_v2.xlsx # Parent-synonym dataset with labels │
      ├── parent-synonym-embedding.csv # Training-ready parent-synonym embeddings │
      ├── synonyms.csv # Extracted synonym words per parent │ 
      └── word_vectors.csv # Trained word vectors for vocabulary │
   ├── Notebooks/ │
      ├── 1. Vectorise_Vocabulary.ipynb # Generate embeddings using modified Skip-gram │ 
      ├── 2. Word_Cloud_Creation.ipynb # Create synonym clouds using vector radius │ 
      ├── 3. WordCloudParaphraser_FFNN.ipynb# Train FFNN on word cloud data │ 
      └── WC_SPRM_SRIP_Final.ipynb # End-to-end pipeline and evaluation ``` </pre>


---

##  Project Workflow

### 1. Vocabulary Vectorization
Generate word embeddings using a skip-gram model trained with MSE loss.

### 2. Word Cloud Creation
Extract synonyms using Datamuse API and group vectors within a 0.2 radius to form a "word cloud".

### 3. FFNN Model Training
Train a feedforward neural network to learn the mapping from parent to synonym embeddings.

### 4. Paraphrasing
For any given sentence, predict synonym embeddings and replace words to generate semantic paraphrases.

---

##  Features

- Custom word embeddings trained on input vocabulary
- Lightweight FFNN-based synonym predictor
- Word cloud logic for embedding proximity
- Sentence paraphrasing at word-level granularity
- Evaluation using Sentence-BERT cosine similarity
- Visual comparisons with baseline embedding models

---

## ✅ Requirements

Install dependencies using:

```bash
pip install -r requirements.txt ```bash
 How to Run
Run 1. Vectorise_Vocabulary.ipynb to create embeddings.

Run 2. Word_Cloud_Creation.ipynb to form synonym clouds.

Train the model using 3. WordCloudParaphraser_FFNN.ipynb.

Test the paraphrasing system using WC_SPRM_SRIP_Final.ipynb.

Example Output
Input:
A good OS is very important for any computer to work
Output:
 A right OS is very profound for any computer to work

 Highlights
Lightweight FFNN-based synonym generator

Custom-trained word embedding model

Embedding cloud filtering for semantic proximity

Evaluated with S-BERT similarity and cosine distance

Outperforms traditional models (Word2Vec, GloVe, FastText) in efficiency

🧑‍💻 Author
Developed by Kishore S
📧 kishorespms@gmail.com
🔗 [GitHub Profile](https://github.com/KishoreLOL21)
```
