# Clinical Entities

Training and test data must be converted to an appropriate format before feeding into machine
learning models. Typically models for clinical entity recognition require input data to be in IOB format.
In turn, to generate the IOB format, the input data must be tokenized and split into sentences.

Even though the E3C corpus has already been pre-tokenized and sentence-segmented, its documents are distributed in a format (UIMA
CAS XMI) that has to be transformed into IOB before being used by the models. 

To make data preprocessing easier, the **clinical_entities** directory contains the training and test partitions of data in IOB format.

Unfortunately, the IOB format cannot be adopted to represent discontinuous or nested entities, which are both
present in the corpus (3.4% and 0.2% respectively). For this reason, this kind of entities has
been removed from consideration. Another issue that had to be addressed was related to the character encoding of
a document (IT101195). Given that it was not possible to parse this document correctly, the latter
has been discarded from the corpus.

|   | Gold | Preprocessed |
|---|---|---|
| English |   1,024  :|   953  |
| French  |   1,327  :| 1,264  |
| Italian |     869  :|   805  |
| Spanish |   1,345  | 1,309  |
| Basque  |   1,910  | 1,889  |

Number of annotated entities before and after data pre-processing

# Temporal Information
