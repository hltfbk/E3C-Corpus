# E3C-Corpus
E3C is a freely available multilingual corpus (Italian, English, French, Spanish, and Basque) of semantically annotated clinical narratives to allow for the linguistic analysis, benchmarking, and training of information extraction systems. It consists of two types of annotations: (i) clinical entities: pathologies, symptoms, procedures, body parts, etc., according to standard clinical taxonomies (i.e. SNOMED-CT, ICD-10); and (ii) temporal information and factuality: events, time expressions, and temporal relations according to the THYME standard. The corpus is organised into three layers, with different purposes. 

* Layer 1: about 25K tokens per language with full manual annotation of clinical entities, temporal information and factuality, for benchmarkingand linguistic analysis. 

* Layer 2: 50-100K tokens per language with semi-automatic annotations of clinical entities, to be used to train baseline systems. 

* Layer 3: about 1M tokens per language of non-annotated medical documents to be exploited by semi-supervised approaches. 

Researchers can use the benchmark training and test splits of our corpus to develop and test their own models. We trained several deep learning based models and provide baselines using the benchmark.

## Cinical Cases
A clinical case is a statement of a clinical practice,presenting the reason for a clinical visit,  the de-scription of physical exams, and the assessment ofthe patient’s situation.  

<code><i>A   25-year-old   man   with   a   historyof   Klippel-Trenaunay   syndrome   pre-sented  to  the  hospital  with  mucopuru-lent  bloody  stool  and  epigastric  persis-tent  colic  pain  for  2  wk.   Colonoscopyshowed continuous superficial ulcers andbleeding.Subsequent  gastroscopy  re-vealed  mucosa  with  diffuse  edema,  ul-cers,  errhysis,  and  granular  and  friablechanges  in  the  stomach  and  duodenalbulb.  A diagnosis of GDUC was consid-ered.  The patient hesitated about iv cor-ticosteroids, so he was treated with pen-tasa 3.2 g/d.  After 0.5 mo of treatment,the symptoms achieved complete remis-sion.  Follow-up examinations showed noevidence of recurrence for 26 mo.</i></code>

## Data Collection and Organization

The table below shows the number of documents(tokens) per language and layer.

| Language    | L1          | L2          | L3              |          
| ----------- | ----------- | ----------- | --------------- |
| English     | 84(25142)   | 171(50371)  | 9779(1075709)   |
| French      | 81(25196)   | 168(50490)  | 25740(66281501) |
| Italian     | 86(24319)   | 174(49900)  | 10213(13601915) |
| Spanish     | 81(24681)   | 162(49351)  | 1876(1030907)   |
| Basque      | 90(22505)   | 111(12541)  | 1232(518244)    |

## Data Annotation
The E3C corpus contains two types of an-notations: (i) temporal information and factuality, and (ii) annotation of clinical entities, specifically disorders.

## Data Distribution
The E3C corpus will be available for download from the ELG platform repository. All documents will be released under Creative Commons licenses.

## Acknowledgements
This work was partially supported by the Eu-ropean  Language  Grid  project  through  itsopen  call  for  pilot  projects  (EU  grant  no.825627),   and  by  the  Basque  Governmentpost-doctoral grant POS202020026.

## References
B. magnini, B. Altuna, A. Lavelli, M. Speranza, and R. Zanoli. 2020. The E3C Project: Collection and Annotation of a Multilingual Corpus of Clinical Cases. In Proceedings of the Seventh Italian Conference on Computational Linguistics, Bologna, Italy, December. Associazione Italiana di Linguistica Computazionale.
