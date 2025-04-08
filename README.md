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

Original Name	Source Name	Match Score
asml nv	asml nv	100
unilever bv	unilever nv	91
shell bv	royal dutch shell	48
ing bank nv	ing nv	71
koninklijke filips	koninklijke philips nv	72
adyen nv	adyen nv	100
relx	relx	100
prosus	prosus nv	80
dsm	koninklijke dsm nv	40
aholddelheize	koninklijke ahold delhaize nv	57
heineken breweries	heineken nv	55
apple	apple	100
microsoft	microsoft	100
capgemini india	capgemini	75
samsung lectronics	samsung electronics	97
![image](https://github.com/user-attachments/assets/1d55691f-eac2-4476-8dc4-256f21b049e0)




BERT-based Semantic Matching Results:

The BERT-based method computed semantic similarity scores between the original entity names and source names. These scores represent how closely the names align semantically, with 1.0 indicating a perfect match.


original_name	source_name	similarity_score
asml nv	asml holding nv	1.000000119
unilever bv	unilever nv	1.000000119
shell bv	royal dutch shell plc	0.879339755
ing bank nv	ing group nv	0.859794855
koninklijke filips	koninklijke philips nv	0.947098255
adyen nv	adyen nv	0.999999881
relx plc	relx plc	1
prosus group	prosus nv	0.99999994
dsm	koninklijke dsm nv	0.888809919
ahold-delheize	koninklijke ahold delhaize nv	0.87124604
heineken breweries	heineken nv	0.794587374
apple inc	apple	0.999999881
Microsoft	Microsoft inc	1
Capgemini India pvt limited	Capgemini	0.907113969
SAMSUNG ÃŠLECTRONICS Holding, LTD	samsung electronics	0.867960393
![image](https://github.com/user-attachments/assets/3526ebe9-23d5-4fe6-bc37-207e25f6adc0)




Key Observations:

Fuzzy Matching provides simpler, numeric match scores that are highly sensitive to small string variations (such as punctuation, capitalization, or partial matches).


BERT-based Similarity gives more accurate results for semantically matching names. For example, "asml nv" and "asml holding nv" have a perfect similarity score (1.0) according to BERT, as BERT can recognize they refer to the same entity, even though the names are not identical.


Fuzzy Matching struggles with variations such as "royal dutch shell" (match score 48) compared to BERT, which gives a higher similarity score (0.879).

BERT can capture deeper semantic meanings and understand abbreviations, synonyms, or related entities, but it requires more computational resources compared to fuzzy matching.
