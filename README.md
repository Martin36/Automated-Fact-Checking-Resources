# Automated Fact Checking Resources

## Introduction
This repo is dedicated to resources in the area of Automated Fact Checking

### Contribution
If you would like to contribute to this repository, feel free to create a Pull Request with your changes. If you do, please consider the current format of the file and use the same for your changes. 

## Contents
- [Papers](#papers)
- [Datasets](#datasets)

## Papers 

### [Web-based statistical fact checking of textual documents (Magdy et al 2010)](https://dl.acm.org/doi/abs/10.1145/1871985.1872002)

### [Toward computational fact-checking (Wu et al 2014)](https://dl.acm.org/doi/10.14778/2732286.2732295)

### [Fact Checking: Task definition and dataset construction (Vlachos et al 2014)](https://www.aclweb.org/anthology/W14-2508/)

### [Computational Fact Checking from Knowledge Networks (Ciampaglia et al 2015)](https://www.researchgate.net/publication/270905908_Computational_Fact_Checking_from_Knowledge_Networks)

### [Show Me Your Evidence – an Automatic Method for Context Dependent Evidence Detection (Rinott et al 2015)](https://www.aclweb.org/anthology/D15-1050/)

### [Identification and Verification of Simple Claims about Statistical Properties (Vlachos et al 2015)](https://www.aclweb.org/anthology/D15-1312/)

In this study the aim is to verify statistical claims, such as "the population of France is 66 million". 

The first task is to find textual patterns which contain the entities. In the example above that would be "the population of X is -", where "X" could be any country and "-" could be any number. 

To collect data, they selected 16 properties from the Freebase knowledge base, each property containing around 150-175 values, most of which were countries. Then they combined the region with the property and made a Bing search query and took the top 50 results for each query. This would result in about 16*150*50 = 120,000 web pages extracted.

To get the patterns they extracted the text of the named entity, which in this case were locations, and the number, for example population. 


### [Detecting Check-worthy Factual Claims in Presidential Debates (Hassan et al 2015)](https://www.researchgate.net/publication/301800740_Detecting_Check-worthy_Factual_Claims_in_Presidential_Debates)

### [The State of Automated Factchecking (Babakar et al 2016)](https://fullfact.org/blog/2016/aug/automated-factchecking/)

### [Toward Automated Fact-Checking: Detecting Check-worthy Factual Claims by ClaimBuster (Hassan et al 2017)](https://dl.acm.org/doi/10.1145/3097983.3098131)

### [A simple but tough-to-beat baseline for the Fake News Challenge stance detection task (Riedel et al 2017)](https://arxiv.org/abs/1707.03264)

This paper describes their submission to the 2017 Fake News Challenge. Their model is relatively simple and consists of an MLP with one hidden layer. As features they use the following: 
- TF vector of the headline
- TF vector of the body text
- Cosine similarity between the L2-normalized TF-IDF vectors of the headline and body

### [Fake News Detection using Stacked Ensemble of Classifiers (Thorne et al 2017)](https://aclanthology.org/W17-4214/)

### [FEVER: a large-scale dataset for Fact Extraction and VERification (Thorne et al 2018)](https://arxiv.org/abs/1803.05355)

### [Combining Fact Extraction and Verification with Neural Semantic Matching Networks (Nie et al 2018)](https://arxiv.org/abs/1811.07039)

They introduce a model that they are calling *Neural Semantic Matching Network (NSMN)*. This model contains 4 layers. The first layer is the *encoding layer* which consists of two BiLSTMs, one for each of the input sequences (e.g. claim and document). 

The next layer is called the *alignment layer*. In this layer an alignment matrix is created, which is the matrix multiplication between the two input sequences. 

For the word embeddings they use a combination of GloVe and ELMo because their combination gives a comprehensive and contextualized lexical representation of the inputs.

### [UKP-Athene: Multi-Sentence Textual Entailment for Claim Verification (Hanselowski et al 2018)](https://arxiv.org/abs/1809.01479)

For the document retrieval phase they extract entities from the claim and try to match these with document titles in Wikipedia. All the noun phrases are considered as entities in the claim. But this is not enough, since names of movies can consist of other phrases. To account for this they do a constituency parse of the claim, and take the tokens before the main verb as an entity. With these entities they search the MediaWiki API to find matching documents. The top match will be the documents with the largest overlap. 

Their results for the document retrieval are 92.60 in accuracy for the top 3 docs. 

For their sentence selection model they use what is called Enhanced Sequential Inference Model (ESIM). This model uses BiLSTMs to encode the claim and evidence sentences. For each claim they have the labelled evidence and they also sample sentences for negative evidence from the other sentences on the correct page. 

Their result for sentence recall at top 3 sentences is 85.37.

In the recognizing textual entailment phase they also use a variant of the ESIM model. As input to the model are concatenated word embeddings from GLoVe and FastText. Then each evidence sentence is combined with the claim before propagation through the model. 


### [Automated Fact Checking: Task formulations, methods and future directions (Thorne et al 2018)](https://www.aclweb.org/anthology/C18-1283/)

### [UCL Machine Reading Group: Four Factor Framework For Fact Finding (HexaF) (Yoneda et al 2018)](https://aclanthology.org/W18-5515/)

### [Towards Debiasing Fact Verification Models (Schuster et al 2019)](https://arxiv.org/abs/1908.05267)

### [Team DOMLIN: Exploiting Evidence Enhancement for the FEVER Shared Task (Stammbach et al 2019)](https://www.aclweb.org/anthology/D19-6616/)

### [Buckle: evaluating fact checking algorithms built on knowledge bases (Huynh et al 2019)](https://dl.acm.org/doi/10.14778/3352063.3352069)

### [MultiFC: A Real-World Multi-Domain Dataset for Evidence-Based Fact Checking of Claims (Augenstein et al 2019)](https://aclanthology.org/D19-1475/)

### [TabFact: A Large-scale Dataset for Table-based Fact Verification (Chen et al 2020)](https://arxiv.org/abs/1909.02164)

In this paper they develop a new dataset which focuses on fact verification, where the given facts are in a tabular format. The task is then to predict the truthfulness of a claim given a table. For this task they explain two different models, Latent Program Algorithm (LPA) and Table-BERT. 


### [Generating Fact Checking Explanations (Augenstein et al 2020)](https://arxiv.org/abs/2004.05773)

### [Fact or Fiction: Verifying Scientific Claims (Wadden et al 2020)](https://arxiv.org/abs/2004.14974)

### [Factual Error Correction of Claims (Thorne et al 2020)](https://arxiv.org/abs/2012.15788)

In this paper they are tackling the task of error correction of factual claims. Given a claim that is incorrect, the task is to retrieve evidence for or against this statement and then to reformulate the statement so that the claim is expressing the retrieved evidence.

### [Factual Error Correction of Claims (Thorne et al 2020)](https://arxiv.org/abs/2012.15788)

### [Language Models as Fact Checkers? (Lee et al 2020)](https://www.aclweb.org/anthology/2020.fever-1.5/)



## Datasets

### [LIAR Dataset](https://github.com/thiagorainmaker77/liar_dataset)

### [Politifact Factcheck Data](https://www.kaggle.com/shivkumarganesh/politifact-factcheck-data)

### [UKP Snopes Corpus (2019)](https://tudatalib.ulb.tu-darmstadt.de/handle/tudatalib/2081)
This corpus contains data from the fact checking website Snopes. The corpus contains 6,422 validated claims, 16,507 evidence text snippets (annotated with sentence level evidence), and 14,296 documents with their sources (URLs).

### [MultiFC (2019)](https://competitions.codalab.org/competitions/21163)
A dataset with claims scraped from various fact-checking websites. 

### [CLIMATE-FEVER (2020)](https://www.sustainablefinance.uzh.ch/en/research/climate-fever.html)
A dataset with climate change related claims. The dataset contains the following for each claim:

- claim_id: unique claim id
- claim: claim text
- claim_label: overall label assigned to claim (based on majority vote on evidences)
- evidences: top five evidence sentences
  - evidence_id: unique evidence id
  - evidence_label: micro-verdict label
  - article: title of source article (Wikipedia page)
  - evidence: evidence sentence
  - entropy: entropy reflecting uncertainty of votes
  - votes: array containing individual votes

### [SciFact (2020)](https://github.com/allenai/scifact)
A dataset with scientific claims. 

### [PUBHEALTH (2020)](https://github.com/neemakot/Health-Fact-Checking)
A dataset with health related claims. 

### [PolitiHop (2020)](https://github.com/copenlu/politihop)
A dataset of political claims, which is targeting *multi-hop* claims e.g. claims that require reasoning over several pieces of evidence. The dataset is structured as follows:

- article_id - article id corresponding to the id of the claim in the LIAR dataset
- statement - the text of the claim
- author - the author of the claim
- ruling - a comma-separated list of the sentences in the Politifact ruling report (this excludes sentences from the summary in the end)
- url_sentences - a comma-separated list of ids of the sentences with a corresponding source url(s)
- relevant_text_url_sentences - a comma-separated list of ids of the sentences with a corresponding source url(s) that are actually relevant to the selected evidence sentences
- politifact_label - label assigned to the claim by PolitiFact fact-checkiers
- annotated_evidence - a json dict of the evidence chains (keys) and the sentences that belong to the chain (value, which is a list of sentence ids from the ruling)
- annotated_label - label annotated by annotators of PolitiFact - True, False, Half-True
- urls - a comma-separated list of source urls used in the corresponding PolitiFact article
- annotated_urls - a json dict mapping sentence ids to the corresponding urls ids. One sentence can have multiple urls


### [FaVIQ: FAct Verification from Information-seeking Questions (2021)](https://faviq.github.io/)


