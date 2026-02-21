# Women's Clothing Reviews NLP: Sentiment Analysis Data Preparation

## Overview
This project focuses on the foundational step of Natural Language Processing (NLP): **Data Cleaning and Preprocessing**. It takes raw text data from the Women's Clothing E-Commerce Reviews dataset and cleans it to prepare the text for sentiment analysis and machine learning models.

## Dataset
The dataset used is the `Womens Clothing E-Commerce Reviews.csv`. The project specifically extracts and processes:
- `Review Text`: The raw text of the customer review.
- `Recommended IND`: The binary label indicating whether the customer recommended the product (1) or not (0).

## Project Workflow / Preprocessing Pipeline

1. **Data Loading & Selection**
   - Loads the initial subset of the data using `pandas`.
   - Filters out rows with missing `Review Text` or `Recommended IND`.
   
2. **Exploratory Data Analysis (EDA)**
   - Analyzes the dataset's class distribution (Recommended vs. Not Recommended).
   - Generates a bar chart visualization of the class distribution using `matplotlib`.

3. **Text Normalization & Preprocessing**
   A robust NLP pipeline is applied to the text data containing the following sequential steps:
   - **Lowercasing:** Converts all characters to lowercase.
   - **Fixing Contractions:** Expands contractions (e.g., "don't" -> "do not") using the `contractions` library and normalizes apostrophe types.
   - **Removing Special Symbols:** Strips out punctuation, numbers, and non-alphabetic characters using RegEx.
   - **Tokenization:** Splits the text into individual words using `nltk`.
   - **Reducing Repeated Characters:** Shrinks elongated strings of characters (e.g., "sooo" -> "soo") while verifying words in WordNet.
   - **Spell Correction:** Corrects misspelled words using the `autocorrect` library's `Speller` tool.
   - **Stopword Removal:** Eliminates common English stopwords (e.g., "the", "and") using `nltk`.
   - **Lemmatization:** Reduces words to their base or dictionary form (e.g., "running" -> "run") using `nltk`'s `WordNetLemmatizer`.

4. **Data Transformation Output**
   - Applies the constructed pipeline to the `Review Text`.
   - Stores the fully preprocessed tokens back into a new dataframe column called `Cleaned Review Text`.

## Technologies & Libraries Used
- **Data Manipulation:** `pandas`
- **Visualization:** `matplotlib`, `seaborn`
- **NLP & Text Processing:** 
   - `nltk` (punkt, stopwords, wordnet)
   - `contractions`
   - `autocorrect`
   - `re` (Regular Expressions)
- **Machine Learning (Prep):** `scikit-learn`

## How to Run the Project
1. **Install Dependencies:**
   Ensure you have the required Python libraries installed:
   ```bash
   pip install pandas matplotlib seaborn nltk autocorrect contractions scikit-learn
   ```

2. **Download NLTK Corpora (Handled in Notebook):**
   The notebook automatically downloads the required NLTK data (`punkt`, `stopwords`, `wordnet`).

3. **Execute the Notebook:**
   Open `Womens_Clothing_Reviews_NLP_ipynb_or_Sentiment_Analysis_Prep.ipynb` in Jupyter Notebook or Google Colab and run the cells sequentially to observe the text transformations and EDA visualizations.