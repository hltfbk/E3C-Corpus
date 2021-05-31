# E3C-Corpus

E3C is a freely available multilingual corpus (English, French, Italian, Spanish, and Basque) of semantically annotated clinical narratives to allow for the linguistic analysis, benchmarking, and training of information extraction systems. It consists of two types of annotations: (i) clinical entities (e.g., pathologies), (ii) temporal information and factuality (e.g., events). Researchers can use the benchmark training and test splits of our corpus to develop and test their own models. We trained several deep learning based models and provide baselines using the benchmark.


## Clinical Cases

A clinical case is a statement of a clinical practice, presenting the reason for a clinical visit, the description of physical exams, and the assessment of the patient’s situation.  

<code><i>A   25-year-old man with a history of Klippel-Trenaunay syndrome presented to the hospital with mucopurulent bloody stool and epigastric persistent colic pain for 2  weeks. Colonoscopy showed continuous superficial ulcers and bleeding. Subsequent gastroscopy revealed mucosa with diffuse edema,  ulcers,  errhysis,  and  granular  and  friable changes in the stomach and duodenal bulb. A diagnosis of GDUC was considered. The patient hesitated about iv corticosteroids, so he was treated with pentasa 3.2 g/d. After 0.5 mo of treatment, the symptoms achieved complete remission. Follow-up examinations showed no evidence of recurrence for 26 mo.</i></code>


## Data Collection and Organization

The E3C corpus contains clinical narratives extracted either from publications, such as PubMed (journal abstracts) and The Pan African Medical Journal (clinical cases), or from existing corpora like the SPACCC corpus. Other documents were collected from admission tests for specialties in medicine, patient information leaflets for medicines and abstracts of theses in medical science. The corpus is organised into three layers, with different purposes.

* Layer 1: about 25K tokens per language with full manual annotation of clinical entities, temporal information and factuality, for benchmarking and linguistic analysis. 

* Layer 2: 50-100K tokens per language with semi-automatic annotations of clinical entities, to be used to train baseline systems. 

* Layer 3: about 1M tokens per language of non-annotated medical documents to be exploited by semi-supervised approaches. 

The table below shows the number of documents (tokens) per language and layer. Release [v1.1.0](https://github.com/hltfbk/E3C-Corpus/releases/tag/v1.1.0) contains this data.  

| Language    | L1           | L2           | L3               |          
| ----------- | ------------ | ------------ | ---------------- |
| English     | 84 (25142)   | 171 (50371)  | 9779 (1075709)   |
| French      | 81 (25196)   | 168 (50490)  | 25740 (66281501) |
| Italian     | 86 (24319)   | 174 (49900)  | 10213 (13601915) |
| Spanish     | 81 (24681)   | 162 (49351)  | 1876 (1030907)   |
| Basque      | 90 (22505)   | 111 (12541)  | 1232 (518244)    |


## Data Annotation

We are currently annotating the collected data with two types of annotations: (i) clinical entities: pathologies, symptoms, procedures, body parts, etc., according to standard clinical taxonomies (i.e., UMLS); and (ii) temporal information and factuality: events, time expressions, and temporal relations according to the THYME standard. Release v2.0.0 due to July 2021 will contain this data. 


## Data Distribution and Licence

All documents are released under Creative Commons licenses.


## Acknowledgements

This work was partially supported by the European  Language  Grid  project  through  its open  call  for  pilot  projects  (EU  grant  no.825627),   and  by  the  Basque  Government post-doctoral grant POS202020026.


## References

B. magnini, B. Altuna, A. Lavelli, M. Speranza, and R. Zanoli. 2020. The E3C Project: Collection and Annotation of a Multilingual Corpus of Clinical Cases. In Proceedings of the Seventh Italian Conference on Computational Linguistics, Bologna, Italy, December. Associazione Italiana di Linguistica Computazionale.
