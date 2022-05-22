/ [Home](index.md)

# Tf-idf 

Tf-idf stands for term frequency-inverse document frequency and is a method to measure the importance of a term with respect to a document or a collection of documents.

𝑇𝐹(𝑡)=(Number of times term t appears in a document)/(Total number of terms in the document)

𝐼𝐷𝐹(𝑡)=log𝑒(Total number of documents)/(Number of documents with term t in it)

for numerical stabiltiy we will be changing this formula little bit

𝐼𝐷𝐹(𝑡)=log𝑒(Total number of documents)/(Number of documents with term t in it+1.)

* If you need the term frequency (term count) vectors for different tasks, use Tfidftransformer.
* If you need to compute tf-idf scores on documents within your “training” dataset, use Tfidfvectorizer
* If you need to compute tf-idf scores on documents outside your “training” dataset, use either one, both will work.

With Tfidftransformer you will systematically compute word counts using CountVectorizer and then compute the Inverse Document Frequency (IDF) values and only then compute the Tf-idf scores.

With Tfidfvectorizer on the contrary, you will do all three steps at once. Under the hood, it computes the word counts, IDF values, and Tf-idf scores all using the same dataset.