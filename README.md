# Assignment-3
We will build a simple search engine on Wikipedia articles using a concept almost similar to the Word
Count program. We will create a dictionary of word frequency in each file and we will use this dictionary
to query the given raw Wikipedia articles.

Make sure the Assignment3_Data.txt is in the google colab content folder.

Step 1: Text Preprocessing 
Each document and query is cleaned using the following techniques:

Convert all text to lowercase

Remove URLs (http://, https://, www.)

Remove punctuation and retain only alphabetic characters

Remove stop words like "the", "is", "in", etc.

Step 2: Term Frequency Index Construction 
Parse each line to extract doc_id and text

Split, clean, and map words to (word, doc_id) pairs

Count occurrences of each word per document

Compute log-weighted TF as:

1 + log10(frequency)

Group TF values by word:

(word, [(doc1, tf1), (doc2, tf2), ...])
Convert to string using special formatting:
word@doc1#tf1+doc2#tf2+doc3#tf3...
Output directory: TF_index1

Step 3: Query Processing 
Load saved TF index from TF_index1

Read user query from query.txt

Preprocess query (same as Step 1)

Filter index for query words

Extract and sum TF scores for each document

Sort documents by score in descending order

Output top 10 results
Output directory: Task1Output
Script: TF_query.py

Directory Structure
Assignment3/
│
├── Assignment3_Data.txt        # Wikipedia articles dataset
├── query.txt                   # User query input
├── TF_index1/                  # Saved Term Frequency Index
├── Task1Output/                # Top 10 search results for query
├── TF_query.py                 # Query processing script
└── README.md                   # Project description file

How to Run
1. Setup
Make sure you have Python and PySpark installed:
pip install pyspark

2. Generate TF Index
Run the TF index creation code (included in the notebook or separate script). Output will be saved to TF_index1/.

3. Run Query
Ensure query.txt exists in the same directory with a line of query text. Then run:
spark-submit TF_query.py



