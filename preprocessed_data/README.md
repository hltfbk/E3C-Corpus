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

|   | Training | Test |
|   | Gold | Preprocessed | Gold | Preprocessed |
|---|---|---|---|---|
| all     | 2,791  | 2,695  | 3,684  | 3,526  |
| English |   463  |   437  |   561  |   516  |
| French  |   596  |   569  |   731  |   695  |
| Italian |   361  |   345  |   508  |   481  |
| Spanish |   525  |   509  |   820  |   800  |
| Basque  |   846  |   835  | 1,064  | 1,054  |

Number of annotated entities before and after data pre-processing.

# Temporal Information
