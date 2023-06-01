# recommender-system
Description of developed code:

The program is written in python. Firstly, it is necessary to import required libraries. After that various functions are defined that perform required analyses. Lastly, the if __name__ == '__main__'  method is utilized, as it allows the functions to be run directly.

List of functions:
load_documents(file_path): This function takes the file path as input and reads the plain text file. It returns a list of documents where each line in the file represents a document. The function opens the file, reads its content, and strips any leading or trailing whitespace from each line before storing it in the documents list.

TF(document): This function takes a document as input and generates the term frequency (TF) for each term in the document. It splits the document into individual terms and counts the number of occurrences for each term, storing the results in a dictionary where the term is the key and its frequency is the value. The function returns the term frequency dictionary.
IDF(documents, term): This function calculates the Inverse Document Frequency (IDF) for a given term in the set of documents. It takes the list of documents and the term as input. The IDF is computed by dividing the total number of documents by the number of documents that contain the term. If the term does not appear in any document, the IDF is set to 0.0. The function returns the IDF value.
TF_IDFf(term_frequency, idf): This function calculates the Term Frequency-Inverse Document Frequency (TF-IDF) for each term in a document. It takes the TF dictionary and the IDF value as input. The TF-IDF for each term is calculated by multiplying its term frequency by the IDF. The function returns a dictionary with the term as the key and its corresponding TF-IDF value as the value.
display_table(documents): This function displays the document table with the index, term, TF, IDF, and TF-IDF columns. It iterates through each document and generates the term frequency table using the generate_term_frequency function. It also keeps track of all unique terms across all documents. Then, it calculates the IDF and TF-IDF for each term using the calculate_inverse_document_frequency and calculate_tf_idf functions, respectively. The function prints the table in a formatted manner.
calculate_cosine_similarity(documents): This function calculates the cosine similarity between all pairs of documents using TF-IDF vectors. It utilizes the TfidfVectorizer from sklearn.feature_extraction.text to transform the documents into TF-IDF vectors. The cosine_similarity function from sklearn.metrics.pairwise is then used to compute the similarity matrix.
display_similarity_matrix: displays the cosine similarity matrix as a DataFrame resembling a confusion matrix. The function creates a DataFrame using the similarity matrix, where the columns and index labels are labeled as "Document 1", "Document 2", etc. The values in the DataFrame correspond to the cosine similarity between each pair of documents.


Example of use
When you run the program a prompt will ask you to add a name of the txt file you want to analyze. When left blank, it will execute with the documents from the assignment.

