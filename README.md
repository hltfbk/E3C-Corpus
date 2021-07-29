# E3C-Corpus

E3C is a freely available multilingual corpus (English, French, Italian, Spanish, and Basque) of semantically annotated clinical narratives to allow for the linguistic analysis, benchmarking, and training of information extraction systems. It consists of two types of annotations: (i) clinical entities (e.g., pathologies), (ii) temporal information and factuality (e.g., events). Researchers can use the benchmark training and test splits of our corpus to develop and test their own models.


### Clinical Cases

A clinical case is a statement of a clinical practice, presenting the reason for a clinical visit, the description of physical exams, and the assessment of the patient’s situation.  

<code><i>A   25-year-old man with a history of Klippel-Trenaunay syndrome presented to the hospital with mucopurulent bloody stool and epigastric persistent colic pain for 2  weeks. Colonoscopy showed continuous superficial ulcers and bleeding. Subsequent gastroscopy revealed mucosa with diffuse edema,  ulcers,  errhysis,  and  granular  and  friable changes in the stomach and duodenal bulb. A diagnosis of GDUC was considered. The patient hesitated about iv corticosteroids, so he was treated with pentasa 3.2 g/d. After 0.5 mo of treatment, the symptoms achieved complete remission. Follow-up examinations showed no evidence of recurrence for 26 mo.</i></code>


## Data Collection and Organization

The E3C corpus is organised into three layers (Table 1).

* Layer 1: about 25K tokens per language with full manual annotation of clinical entities, temporal information and factuality, for benchmarking and linguistic analysis. 

* Layer 2: 50-100K tokens per language with semi-automatic annotations of clinical entities. 

* Layer 3: about 1M tokens per language of non-annotated medical documents to be exploited by semi-supervised approaches. 
<br/><br/> 

| Language    | L1           | L2           | L3               |          
| ----------- | ------------ | ------------ | ---------------- |
| English     | 84 (25142)   | 171 (50371)  | 9779 (1075709)   |
| French      | 81 (25196)   | 168 (50490)  | 25740 (66281501) |
| Italian     | 86 (24319)   | 174 (49900)  | 10213 (13601915) |
| Spanish     | 81 (24681)   | 162 (49351)  | 1876 (1030907)   |
| Basque      | 90 (22505)   | 111 (12541)  | 1232 (518244)    |

Table 1: number of documents (tokens counted by whitespace) per language and layer.
<br/><br/>

We collected clinical narratives extracted either from publications, such as PubMed (Journal Abstracts) and The Pan African Medical Journal (Journal), or from existing corpora like the SPACCC corpus (Dataset). Other documents were collected from admission tests for specialties in medicine, patient information leaflets for medicines and abstracts of theses in medical science. Table 2 shows this distribution.

| Layer       | Source      | English      | French       | Italian      | Spanish      | Basque       |
| ----------- | ----------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| L1+L2       |             |              |              |              |              |              |
|             | pubmed      | 91           | 48           | 0            | 0            | 0            |
|             | journal     | 164          | 201          | 206          | 0            | 201          |
|             | dataset     | 0            | 0            | 0            | 243          | 0            |
|             | other       | 0            | 0            | 54           | 0            | 0            |
| L3          |             |              |              |              |              |              |
|             | pubmed      | 9227         | 84           | 0            | 0            | 0            |
|             | journal     | 552          | 1436         | 592          | 504          | 0            |
|             | dataset     | 0            | 0            | 0            | 1372         | 0            |
|             | other       | 0            | 24220        | 9621         | 0            | 1232         |

Table 2: number of documents per source and layer.
<br/><br/>

Since the length of the documents may affect the temporal information in text (i.e., the longer the  text,  the more complex temporal graph) we created a balanced document set in terms of size (Table 3). Short (<200 tokens), medium (200–400 tokens) and long (400–600 tokens).

| Layer       | Size        | English      | French       | Italian      | Spanish      | Basque       |
| ----------- | ----------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| L1          |             |              |              |              |              |              |
|             | short       | 28           | 24           | 29           | 27           | 36           |
|             | medium      | 28           | 29           | 29           | 27           | 44           |
|             | long        | 28           | 28           | 28           | 27           | 10           |
| L2          |             |              |              |              |              |              |
|             | short       | 57           | 56           | 58           | 54           | 106          |
|             | medium      | 57           | 56           | 60           | 54           | 1            |
|             | long        | 57           | 56           | 56           | 54           | 4            |

Table 3: number of documents of short, medium and long length in Layer 1 and Layer 2.
<br/><br/>

**Release [v1.1.0](https://github.com/hltfbk/E3C-Corpus/releases/tag/v1.1.0) of the corpus contains all the documents collected through data collection.**


## Data Cleaning

With reference only to the documents of Layer 1, we applied a basic preprocessing step:

* Remove sentences (at the beginning or at the end of documents) that are not part of clinical cases.
* Remove references to figures and tables.
* Restore punctuation and capitalization.


## Data Annotation

The documents in Layer 1 contain full manual annotation of clinical entities, temporal information and factuality, for benchmarking and linguistic analysis. The documents in Layer 2 contain semi-automatic annotations of clinical entities.

**Layer 1:** We are currently annotating the collected data with two types of annotations: (i) clinical entities: pathologies, symptoms, procedures, body parts, etc., according to standard clinical taxonomies (i.e., UMLS); and (ii) temporal information and factuality: events, time expressions, and temporal relations according to the THYME standard. **Release v2.0.0 of the corpus will contain this data (see Release Schedule below).** 


|                     | Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| Documents           |                     |              |              |              | 81           | 90           |
| Sentences*          |                     |              |              |              | 1134         | 3126         |
| Tokens*             |                     |              |              |              | 28815        | 34052        |
|                     | CLINENTITY          |              |              |              | 1345         | 1910         |
|                     | EVENT               |              |              |              | 4767         | 7910         |
|                     | ACTOR               |              |              |              | 319          | 505          |
|                     | BODYPART            |              |              |              | 814          | 1410         |
|                     | TIMEX3              |              |              |              | 383          | 638          |
|                     | RML                 |              |              |              | 391          | 1101         |
|                     | TIMEX3TimexLinkLink |              |              |              | 604          | 969          |
|                     | RMLPERTAINSTOLink   |              |              |              | 473          | 1196         |
|                     | EVENTTLINKLink      |              |              |              | 4096         | 7012         |
|                     | EVENTALINKLink      |              |              |              | 92           | 113          |

Table 4: number of manually annotated entities in Layer 1.<br>
(*) produced by [WebAnno](https://webanno.github.io/webanno/)
<br/><br/>


**Layer 2:** Clinical entities in these documents have been automatically recognized by dictionary matching. The dictionary of each language was obtained by combining the entities present in the UMLS dictionaries of that language, and the entities annotated in the training split of Layer 1.

|                     | Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| Documents           |                     | 171          | 168          | 174          | 162          | 111          |
| Sentences*          |                     | 2873         | 2389         | 2436         | 2347         | 1594         |
| Tokens*             |                     | 59006        | 58523        | 61992        | 57875        | 18784        |
|                     | CLINENTITY          | 2140         | 2033         | 1686         | 2625         | 488          |

Table 5: number of automatically annotated entities in Layer 2.<br>
(*) produced by [WebAnno](https://webanno.github.io/webanno/)
<br/><br/>


## Data Curation

To have an overall estimation of the quality of the clinical entities in Layer 2, about 10% of the tokens in Layer 2 have been manually annotated (Table 6). Table 7 reports the accuracy values calculated on the entities extracted from this subset of tokens.

|                     | Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| Documents           |                     | 19           | 18           | 18           | 18           | 10           |
| Sentences*          |                     | 334          | 293          | 275          | 261          | 468          |
| Tokens*             |                     | 6654         | 6220         | 6698         | 6361         | 5031         |
|                     | CLINENTITY          | 254          | 272          | 226          | 330          | 336          |

Table 6: number of manually annotated entities in Layer 2.<br>
(*) produced by [WebAnno](https://webanno.github.io/webanno/)


| Entity      | Language    | Precision    | Recall       | F1               |          
| ----------- | ----------- | ------------ | ------------ | ---------------- |
| CLINENTITY  |             |              |              |                  |
|             | English     | 91.45        | 84.25        | 87.70            |
|             | French      | 83.10        | 65.07        | 72.99            |
|             | Italian     | 91.21        | 73.45        | 81.37            |
|             | Spanish     | 76.45        | 67.88        | 71.92            |
|             | Basque      | 92.86        | 30.95        | 46.43            |

Table 7: Precision, Recall and F1 measure of the entities that were manually verified.<br>


## Data Distribution and Licence

The E3C corpus is released under Creative Commons NonCommercial license (**CC BY-NC**).


## E3C for Machine Learning

The E3C corpus allows for training and evaluation of information extraction systems. To let researchers compare their models under the same experimental conditions, the three layers of which E3C is made have to be used as following. 

Layer 1: about 25K tokens per language of clinical narratives with full manual annotation of clinical entities, temporal information and factuality. It comes with two partitions, one for training purposes (about 10K tokens) and one for testing (models evaluation) (see train_test_split.txt to get the list of documents for training).

Layer 2: 50-100K tokens per language of clinical narratives with automatic annotation of clinical entities and manual check of a small sample (about 10%) of this annotation. 
This data can be used together with or alternatively to the training data of Layer 1 to train models.

Layer 3: about  1M  tokens  per  language  of non-annotated medical documents (not necessarily clinical narratives) to be exploited by semi-supervised approaches.


## E3C Project Web Site

[https://e3c.fbk.eu/home](https://e3c.fbk.eu/home)


## Release Schedule
v2.0.0

Date: July 2021

New features:

* Clinical Cases annotated


## Acknowledgements

This work was partially supported by the European  Language  Grid  project  through  its open  call  for  pilot  projects  (EU  grant  no.825627),   and  by  the  Basque  Government post-doctoral grant POS202020026.


## References

B. magnini, B. Altuna, A. Lavelli, M. Speranza, and R. Zanoli. 2020. The E3C Project: Collection and Annotation of a Multilingual Corpus of Clinical Cases. In Proceedings of the Seventh Italian Conference on Computational Linguistics, Bologna, Italy, December. Associazione Italiana di Linguistica Computazionale.
