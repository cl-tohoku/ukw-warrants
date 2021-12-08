# Exploring Methodologies for Collecting High-Quality Implicit Reasoning in Arguments

A preliminary dataset of crowdsourced semi-structured warrants. This repository contains data and supplementary materials for our ArgMining 2021 paper. Use the following citation if you use the data set:

```
@inproceedings{singh-etal-2021-exploring,
    title = "Exploring Methodologies for Collecting High-Quality Implicit Reasoning in Arguments",
    author = "Singh, Keshav  and
      Mim, Farjana Sultana  and
      Inoue, Naoya  and
      Naito, Shoichi  and
      Inui, Kentaro",
    booktitle = "Proceedings of the 8th Workshop on Argument Mining",
    month = nov,
    year = "2021",
    address = "Punta Cana, Dominican Republic",
    publisher = "Association for Computational Linguistics",
    pages = "57--66",
}
```
 
 > **Abstract** Annotation of implicit reasoning (i.e., warrant) in arguments is a critical resource to train models in gaining deeper understanding and correct interpretation of arguments. However, warrants are usually annotated in unstructured form, having no restriction on their lexical structure which sometimes makes it difficult to interpret how warrants relate to any of the information given in claim and premise. Moreover, assessing and determining better warrants from the large variety of reasoning patterns of unstructured warrants becomes a formidable task. Therefore, in order to annotate warrants in a more interpretative and restrictive way, we propose two methodologies to annotate warrants in a semi-structured form. To the best of our knowledge, we are the first to show how such semi-structured warrants can be annotated on a large scale via crowdsourcing. We demonstrate through extensive quality evaluation that our methodologies enable collecting better quality warrants in comparison to unstructured annotations. To further facilitate research towards the task of explicating warrants in arguments, we release our materials publicly (i.e., crowdsourcing guidelines and collected warrants).
}

* Contact person: Keshav Singh, keshav.singh29@gmail.com
  * NLP Lab (Tohoku University): https://www.nlp.ecei.tohoku.ac.jp/

For license information, see LICENSE. 

# User-defined Keyword-based Warrants (UKW) Dataset
Data for ArgMining21 are in a csv format. The first row is column headers and each row is then a single instance in the following form:

| topic  | premise | claim  | mace_ibm | hidden_reasoning_keyword  | claim_keyword | premise_keyword  |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Zoos	| we should abolish these zoos because animals did not ask to be captive and gawked at. |	We should abolish zoos | 0.929201449 |	prevents a mental decline of these animals |	Abolishing zoos |	because animals did not ask to be captive and gawked at. |

where **claim_keyword** and **premise_keyword** contain the necessary information from **claim** and **premise** respectively. The **hidden_reasoning_keyword** contains the implicit knowledge required to bridge the gap between **claim_keyword** and **premise_keyword**

### How to understand the data?

From the example above, we can construct this statement which acts as the warrant:

**`claim_keyword`** **`hidden_reasoning_keyword`** **`premise_keyword`** 
i.e. 

> Abolishing zoos prevents a mental decline of these animals because animals did not ask to be captive and gawked at.

---

Our preliminary dataset can be found under `data/final_data_with_hr.csv`, which contains an additional column named `mace_ibm`. Each row of this column contains MACE score originally given to premise (Argument) as stated in [Gretz et al. (2019)](https://arxiv.org/pdf/1911.11408.pdf). 
