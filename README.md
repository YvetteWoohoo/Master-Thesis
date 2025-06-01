# Master-Thesis
This code repository accompanies the paper "Semantic Shifts of Democracy in Political Science Discourse: A Diachronic Word Embedding Approach"

data.ipynb
* data cleaning
* Ingests and cleans raw PDFs and JSONL metadata files
* Processes files from multiple sources (JSTOR, Portico, direct PDFs)
* Aggregates data into structured format with:
    * Year ranges (1971-1980 to 2021-2024)
    * Journal types (American/British Journal of Political Science)
* Outputs cleaned corpus for analysis

preprocess.ipynb
* Performs text cleaning and normalization:
    * Sentence tokenization
    * Stopword removal
    * Metadata stripping
* Groups text into subcorpora by:
    * Journal type
    * Time period
    * Outputs preprocessed text files for modeling

bigram model.ipynb
* Trains and evaluates bigram phrase detectors
* Optimizes parameters through precision/recall analysis
* Bigram identification
* Saves optimized phrase detectors for semantic analysis

word embedding model.ipynb
* Implements bootstrapped word embedding training:
    * 25 bootstrap samples per subcorpus
    * Skip-gram negative sampling architecture (300-dim vectors)
* Analyzes semantic shifts of key terms (e.g., "democracy")
* Includes:
    * Sentence iterators
    * Phrasing pipelines
* Model evaluation framework

cosine similarities.ipynb
* Implements semantic dimension definition using anchor words.
* Calculates vector representations for semantic dimensions using Word2Vec.
* Computes cosine similarities between words and semantic dimensions.
* Computes cosine similarities between semantic dimensions.

validation for anchor words.ipynb
* Loads and processes anchor words for various dimensions.
* Splits anchor words into training and testing sets.
* Validates anchor word semantic coherence via nearest neighbors in Word2Vec models.

anchor word frequency.ipynb
* Computes normalized frequency of anchor words across subcorpora.
* Visualizes word frequencies and distribution trends.
* Aids in understanding the prevalence of key terms.

regression.ipynb
* Performs mixed-effects and OLS regression analysis on cosine similarity data.
* Analyzes the influence of temporal and contextual factors on semantic relationships.

