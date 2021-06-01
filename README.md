# E3C-Corpus

E3C is a freely available multilingual corpus (English, French, Italian, Spanish, and Basque) of semantically annotated clinical narratives to allow for the linguistic analysis, benchmarking, and training of information extraction systems. It consists of two types of annotations: (i) clinical entities (e.g., pathologies), (ii) temporal information and factuality (e.g., events). Researchers can use the benchmark training and test splits of our corpus to develop and test their own models. We trained several deep learning based models and provide baselines using the benchmark.


## Clinical Cases

A clinical case is a statement of a clinical practice, presenting the reason for a clinical visit, the description of physical exams, and the assessment of the patient’s situation.  

<code><i>A   25-year-old man with a history of Klippel-Trenaunay syndrome presented to the hospital with mucopurulent bloody stool and epigastric persistent colic pain for 2  weeks. Colonoscopy showed continuous superficial ulcers and bleeding. Subsequent gastroscopy revealed mucosa with diffuse edema,  ulcers,  errhysis,  and  granular  and  friable changes in the stomach and duodenal bulb. A diagnosis of GDUC was considered. The patient hesitated about iv corticosteroids, so he was treated with pentasa 3.2 g/d. After 0.5 mo of treatment, the symptoms achieved complete remission. Follow-up examinations showed no evidence of recurrence for 26 mo.</i></code>


## Data Collection and Organization

The corpus is a collection of clinical narratives extracted either from publications, such as PubMed (Journal Abstracts) and The Pan African Medical Journal (Journal), or from existing corpora like the SPACCC corpus (Dataset). It also contains medical documents collected from admission tests for specialties in medicine, patient information leaflets for medicines and abstracts of theses in medical science. Table 1 shows this ditribution.

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

Table 1: number of documents per source and layer.
<br/><br/>

The corpus is organised into three layers, with different purposes.

* Layer 1: about 25K tokens per language with full manual annotation of clinical entities, temporal information and factuality, for benchmarking and linguistic analysis. 

* Layer 2: 50-100K tokens per language with semi-automatic annotations of clinical entities, to be used to train baseline systems. 

* Layer 3: about 1M tokens per language of non-annotated medical documents to be exploited by semi-supervised approaches. 
<br/><br/> 

Table 2 shows how the documents were assigned to the three different layers.

| Language    | L1           | L2           | L3               |          
| ----------- | ------------ | ------------ | ---------------- |
| English     | 84 (25142)   | 171 (50371)  | 9779 (1075709)   |
| French      | 81 (25196)   | 168 (50490)  | 25740 (66281501) |
| Italian     | 86 (24319)   | 174 (49900)  | 10213 (13601915) |
| Spanish     | 81 (24681)   | 162 (49351)  | 1876 (1030907)   |
| Basque      | 90 (22505)   | 111 (12541)  | 1232 (518244)    |

Table 2: number of documents (tokens) per language and layer.
<br/><br/>

Since Layer 1 and Layer 2 are the core of the corpus, we have created a balanced document set in terms of size (Table 3). Short (<200 tokens), medium (200–400 tokens) and long (400–600 tokens) texts have been selected, as we presumed that text length would directly affect the temporal information in text; the longer the  text,  themore complex temporal graph.

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

Release [v1.1.0](https://github.com/hltfbk/E3C-Corpus/releases/tag/v1.1.0) of the corpus contains data collected through data collection.


## Data Annotation

We are currently annotating the collected data with two types of annotations: (i) clinical entities: pathologies, symptoms, procedures, body parts, etc., according to standard clinical taxonomies (i.e., UMLS); and (ii) temporal information and factuality: events, time expressions, and temporal relations according to the THYME standard. Release v2.0.0 of the corpus will contain this data (see Release Schedule below). 


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
