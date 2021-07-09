# Panama Papers: Data Cleaning Exercise

This **offshore leak data** was *hand typed in multiple languages* (English, French, Spanish, Portuguese, German) by an international team of journalist, the **raw dataset is not ready for analysis**. 

You will find here 3 jupyter notebooks to help you clean this database. 

**This cleanup is extensive and accountable**;
- *Non-exact duplicates where not removed*, and are still connected to their 'master' nodes. 
- The original strings are kept intact. 
- As I speak French, English and German fluently as well as a bit of Spanish, I *normalized the database to English*.
- The complete database was **reduced by over 39%**. 

After running these notebooks, you will be at a better starting point for any further analysis. 

## 1. Normalizing Edges:

Edges represent links or relationships. They are the connections types between the entities, officers, intermediaries and addresses nodes in the dataset. Here we normalize the relationship types and descriptions to simplify the database into fewer edge categories.

## 2. Normalizing and Deduplicating Addresses with Fuzzy Matching:

By removing punctuation, country names and sorting words, 2112 addresses (2% of the address database) were found as direct duplicates and cleansed from the 'edges.csv' file.

Furthermore, using fuzzy matching 40,257 addresses (45% of the address database) were found to be over 75% similar to 11,119 unique addresses from a total of 93,454. These similarities are now grouped into 'master' nodes. However, as these similarities are not exact duplicates, they are still connected to the master nodes and saved in the new 'similarity.edges.csv' for accountability. All the links to these similarities have been transfered to the master nodes.

**Overal, over 47% of the addresses were found to be duplicates to some degree.** 

## 3. Normalizing and Deduplicating Officers: 
Here, Bearer nodes where grouped and normalized before splitting the dataset into companies and people nodes. 

A multilingual corpus of Incorporation markers was used to further cleanse the company names. The corpus is not available here as I have created CleanCorp, a library created specificaly for cleaning and infering on company names.

**Over 17% of the officer nodes in the database were removed as direct duplicates.**

## 4. Intermediaries: 

As the file was lost in a catastrophic water damage, you should consider running the same notebook used for the officer nodes on the intermediary nodes.
