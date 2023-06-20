# recommender-system
## Description of the assignment:

In this scenario, the client has a question or search query, and they have a set of documents available. By utilizing KNN, the algorithm can calculate the similarity between the query and the documents based on their vector representations (e.g., TF-IDF), and identify the k nearest neighbors (documents) that are most similar to the query.
The k-nearest neighbors (KNN) algorithm can be used for ranking based on TF-IDF (Term Frequency-Inverse Document Frequency) and other similarity metrics. TF-IDF is a commonly used method to represent the importance of a term in a document relative to a collection of documents.

TF-IDF (Term Frequency-Inverse Document Frequency)assigns a weight to each term in a document, taking into account both the local importance of the term within the document (TF) and the global importance of the term across the document collection (IDF).

TF (Term Frequency) measures the frequency of a term within a document. It indicates how often a specific term appears in a document, providing insight into the importance of the term within that document.

IDF (Inverse Document Frequency) measures the significance of a term in a document collection. It quantifies the rarity of a term by calculating the logarithm of the ratio between the total number of documents and the number of documents containing the term.

Cosine similarity is a similarity measure that determines the cosine of the angle between two vectors, which in this case, represent documents or queries.

## Description of developed code:

The program is written in python. Firstly, it is necessary to import required libraries. After that various functions are defined that perform required analyses. Lastly, the __name__ == '__main__'  method is utilized, as it allows the functions to be run directly.

List of functions:
1. load_documents(file_path): This function takes the file path as input and reads the plain text file. It returns a list of documents where each line in the file represents a document. The function opens the file, reads its content, and strips any leading or trailing whitespace from each line before storing it in the documents list.
2. TF(document): This function takes a document as input and generates the term frequency (TF) for each term in the document. It splits the document into individual terms and counts the number of occurrences for each term, storing the results in a dictionary where the term is the key and its frequency is the value. The function returns the term frequency dictionary.
3. IDF(documents, term): This function calculates the Inverse Document Frequency (IDF) for a given term in the set of documents. It takes the list of documents and the term as input. The IDF is computed by dividing the total number of documents by the number of documents that contain the term. If the term does not appear in any document, the IDF is set to 0.0. The function returns the IDF value.
4. TF_IDFf(term_frequency, idf): This function calculates the Term Frequency-Inverse Document Frequency (TF-IDF) for each term in a document. It takes the TF dictionary and the IDF value as input. The TF-IDF for each term is calculated by multiplying its term frequency by the IDF. The function returns a dictionary with the term as the key and its corresponding TF-IDF value as the value.
5. display_table(documents): This function displays the document table with the index, term, TF, IDF, and TF-IDF columns. It iterates through each document and generates the term frequency table using the generate_term_frequency function. It also keeps track of all unique terms across all documents. Then, it calculates the IDF and TF-IDF for each term using the calculate_inverse_document_frequency and calculate_tf_idf functions, respectively. The function prints the table in a formatted manner.
6. calculate_cosine_similarity(documents): This function calculates the cosine similarity between all pairs of documents using TF-IDF vectors. It utilizes the TfidfVectorizer from sklearn.feature_extraction.text to transform the documents into TF-IDF vectors. The cosine_similarity function from sklearn.metrics.pairwise is then used to compute the similarity matrix.
7. display_similarity_matrix: displays the cosine similarity matrix as a DataFrame resembling a confusion matrix. The function creates a DataFrame using the similarity matrix, where the columns and index labels are labeled as "Document 1", "Document 2", etc. The values in the DataFrame correspond to the cosine similarity between each pair of documents.


## Example of use:

When you run the program a prompt will ask you to add a name of the txt file you want to analyze. Don't forget the path to the document. When left blank, it will execute with the documents from the assignment.

