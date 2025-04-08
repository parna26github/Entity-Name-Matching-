# Entity-Name-Matching
Comparative Analysis of Traditional Text Similarity Methods vs. BERT for Entity Name Linking Across Data Sources

Project Overview:

In many real-world applications—like data integration, deduplication, and knowledge graph construction—it is crucial to match and merge different representations of the same entity (e.g., "Apple Inc." and "Apple" or "IBM" and "International Business Machines"). This project aims to compare traditional text similarity techniques with BERT (Bidirectional Encoder Representations from Transformers) to determine which approach provides the most effective solution for entity name matching, particularly when dealing with diverse and noisy data sources.


Overview:


Fuzzy Matching: This technique is based on string similarity and computes a "match score" based on various string metrics, such as Levenshtein distance. It is useful for matching entities with slight variations in spelling, abbreviations, or typos.


BERT-based Semantic Matching: This method uses pre-trained BERT models to compute semantic similarity between entity names. Unlike fuzzy matching, BERT captures the deeper meaning of the text and can identify entities that are conceptually the same but may differ in their wording.

Results Comparison:


Fuzzy Matching Results:
The fuzzy matching technique returned the following match scores between the original entity names and their corresponding source names.



![image](https://github.com/user-attachments/assets/1d55691f-eac2-4476-8dc4-256f21b049e0)




BERT-based Semantic Matching Results:

The BERT-based method computed semantic similarity scores between the original entity names and source names. These scores represent how closely the names align semantically, with 1.0 indicating a perfect match.



![image](https://github.com/user-attachments/assets/3526ebe9-23d5-4fe6-bc37-207e25f6adc0)




Key Observations:

Fuzzy Matching provides simpler, numeric match scores that are highly sensitive to small string variations (such as punctuation, capitalization, or partial matches).


BERT-based Similarity gives more accurate results for semantically matching names. For example, "asml nv" and "asml holding nv" have a perfect similarity score (1.0) according to BERT, as BERT can recognize they refer to the same entity, even though the names are not identical.


Fuzzy Matching struggles with variations such as "royal dutch shell" (match score 48) compared to BERT, which gives a higher similarity score (0.879).

BERT can capture deeper semantic meanings and understand abbreviations, synonyms, or related entities, but it requires more computational resources compared to fuzzy matching.
