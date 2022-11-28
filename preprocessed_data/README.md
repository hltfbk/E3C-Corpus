# Clinical Entities

Training and test data must be converted to an appropriate format before feeding into machine
learning models. Typically models for entity recognition require input data to be in IOB format.
In turn, to generate the IOB format, the
input data must be tokenized and split into sentences. Even though the E3C corpus has already
been pre-tokenized and sentence-segmented, its documents are distributed in a format (UIMA
CAS XMI) that has to be transformed into IOB before being used by the models. Unfortunately,
the IOB format cannot be adopted to represent discontinuous or nested entities, which are both
present in the corpus. Concerning the representation of the discontinuous entities (3.4% of the
total entities in the corpus), some extensions to the IOB scheme have been proposed, such as
the scheme of Tang et al. (2013). This scheme requires the tokens inside a discontinuous entity
to be known exactly. Since the mention-level annotation of the corpus does not provide such
information for the discontinuous entities (see Section 3), this kind of entities have been removed
from consideration. As far as the nested entities are concerned, it has been observed that there are
few of them in the corpus (0.2% of the entities). For this reason, only the topmost entities have
been considered. Another issue that had to be addressed was related to the character encoding of
a document (IT101195). Given that it was not possible to parse this document correctly, the latter
has been discarded from the corpus.
