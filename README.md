# E3C-Corpus

E3C is a freely available multilingual corpus (English, French, Italian, Spanish, and Basque) of semantically annotated clinical narratives to allow for the linguistic analysis, benchmarking, and training of information extraction systems. It consists of two types of annotations: (i) clinical entities (e.g., pathologies), (ii) temporal information and factuality (e.g., events). Researchers can use the benchmark training and test splits of our corpus to develop and test their own models. We trained several deep learning based models and provide baselines using the benchmark.


## Clinical Cases

A clinical case is a statement of a clinical practice, presenting the reason for a clinical visit, the description of physical exams, and the assessment of the patient’s situation.  

<code><i>A   25-year-old man with a history of Klippel-Trenaunay syndrome presented to the hospital with mucopurulent bloody stool and epigastric persistent colic pain for 2  weeks. Colonoscopy showed continuous superficial ulcers and bleeding. Subsequent gastroscopy revealed mucosa with diffuse edema,  ulcers,  errhysis,  and  granular  and  friable changes in the stomach and duodenal bulb. A diagnosis of GDUC was considered. The patient hesitated about iv corticosteroids, so he was treated with pentasa 3.2 g/d. After 0.5 mo of treatment, the symptoms achieved complete remission. Follow-up examinations showed no evidence of recurrence for 26 mo.</i></code>


## Data Collection and Organization

The E3C corpus is organised into three layers, with different purposes (Table 1).

* Layer 1: about 25K tokens per language with full manual annotation of clinical entities, temporal information and factuality, for benchmarking and linguistic analysis. 

* Layer 2: 50-100K tokens per language with semi-automatic annotations of clinical entities, to be used to train baseline systems. 

* Layer 3: about 1M tokens per language of non-annotated medical documents to be exploited by semi-supervised approaches. 
<br/><br/> 

| Language    | L1           | L2           | L3               |          
| ----------- | ------------ | ------------ | ---------------- |
| English     | 84 (25142)   | 171 (50371)  | 9779 (1075709)   |
| French      | 81 (25196)   | 168 (50490)  | 25740 (66281501) |
| Italian     | 86 (24319)   | 174 (49900)  | 10213 (13601915) |
| Spanish     | 81 (24681)   | 162 (49351)  | 1876 (1030907)   |
| Basque      | 90 (22505)   | 111 (12541)  | 1232 (518244)    |

Table 1: number of documents (tokens) per language and layer.
<br/><br/>

We collected clinical narratives extracted either from publications, such as PubMed (Journal Abstracts) and The Pan African Medical Journal (Journal), or from existing corpora like the SPACCC corpus (Dataset). Other documents were collected from admission tests for specialties in medicine, patient information leaflets for medicines and abstracts of theses in medical science. Table 2 shows this ditribution.

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

Since the length of the documents may affect the temporal information in text (i.e., the longer the  text,  themore complex temporal graph) we created a balanced document set in terms of size (Table 3). Short (<200 tokens), medium (200–400 tokens) and long (400–600 tokens).

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

* Remove sentences (at the beginng or at the end of diocuments) that are not part of clinical cases.
* Remove references to figures and tables.
* Restore punctuation and capitalization.

## Data Annotation

We are currently annotating the collected data with two types of annotations: (i) clinical entities: pathologies, symptoms, procedures, body parts, etc., according to standard clinical taxonomies (i.e., UMLS); and (ii) temporal information and factuality: events, time expressions, and temporal relations according to the THYME standard. **Release v2.0.0 of the corpus will contain this data (see Release Schedule below).** 


| Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| CLINENTITY          |              |              |              |  1345        |  199         |
| EVENT               |              |              |              |  4767        | 7910         |
| ACTOR               |              |              |              |  319         | 505          |
| BODYPART            |              |              |              |  814         | 1410         |
| TIMEX3              |              |              |              |  383         | 638          |
| RML                 |              |              |              |  391         | 1101         |
| TIMEX3TimexLinkLink |              |              |              |  604         | 969          |
| RMLPERTAINSTOLink   |              |              |              |  473         | 1196         |
| EVENTTLINKLink      |              |              |              |  4096        | 7012         |
| EVENTALINKLink      |              |              |              |  92          | 113          |

Table 4: number of manually annotated entities in Layer 1.
<br/><br/>


| Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| CLINENTITY          |  2140        | 2033         |  1686        |  2625        | 488          |


Table 5: number of automatically annotated entities in Layer 2.
<br/><br/>


## Data Curation

|                     | Entity              | English      | French       | Italian      | Spanish      | Basque       |
| ------------------- | ------------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
| Documents           |                     |  19          | 18           |  18          |  18          | 10           |
|                     | CLINENTITY          |  254         | 272          |  226         |  330         | 336          |

Table 6: number of curated entities in Layer 2.
<br/><br/>

## Data Distribution and Licence

All documents are released under Creative Commons license.


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
