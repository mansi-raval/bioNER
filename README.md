# Named Entity Recognition (NER) on Biomedical Text using BERT for Token Classification
 Named entity recognition (NER) on biomedical text to accurately identify complex, domain-specific entities like proteins, genes, and medical terms using BERT for Token Classification. Traditional NER models struggle with specialized vocabulary and limited labeled data in biomedical text. Existing systems often rely on general-purpose models, lacking domain-specific training to effectively capture nuanced biomedical terminology.

### Dataset And Data Preprocessing
- **Dataset Used:** MeDAL, a large medical text dataset curated for abbreviation disambiguation.
- **Data Preprocessing Steps:**
  1. **Filtering Labels:** Retained labels occurring at least 145 times to reduce label imbalance.
  2. **Cleaning Text:** Removed special characters and accents using regex to standardize inputs and reduce noise, including handling Unicode characters for robust tokenization.
  3. **Data Structuring:** Assigned a unique sentence_id to each sentence, splitting sentences into individual words with labels based on an entity type or marked as "O" (Outside) for non-entities.
  4. **Group by Sentence:**
     Sentence: Complete sentence formed by concatenating words.
     Word Labels: List of entity tags for each word in the sentence.
  5. **Finalizing Data:** Consolidated dataset with columns "sentence" and "word_labels", removing duplicates for efficient token classification.

### Model
- **BERT for Token Classification**:
  -   **Encoder:** Extracts contextual embeddings for each token.
  -   **Classification Head:** Assigns entity labels using established label mappings during preprocessing
    
The model was trained using batches of tokenized data passed through BERT for token classification, with optimization using the Adam optimizer and hyperparameter tuning (e.g., learning rate, sequence length) to improve convergence.

### Evaluation Metrics
Precision, Recall, F1 Score, Accuracy, Classification Report
