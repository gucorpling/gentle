# GENTLE

Repository for the Genre Tests for Linguistic Evaluation (GENTLE) Corpus

This repository contains release versions of the Genre Tests for Linguistic Evaluation ([GENTLE](https://gucorpling.org/gum/gentle.html)) corpus, an English out-of-domain test set following the same multilayer annotations found in the [GUM corpus](https://gucorpling.org/gum/). The texts are of the following 8 genres:

  * dictionary entries
  * live esports commentary
  * legal documents
  * medical notes
  * poetry
  * mathematical proofs
  * course syllabuses
  * threat letters

## Splits - test only

The entire corpus is designed to be a *test set* of challenging genres for NLP systems to be evaluated on. Although one can train a model on this corpus, or concatenate it to another training set, we present this entire corpus as a test set, and do not provide any official train / dev data.

## Citing

To cite this corpus, please refer to the following article:

  * Aoyama, Tatsuya, Shabnam Behzad, Luke Gessler, Lauren Levine, Jessica Lin, Yang Janet Liu, Siyao Peng, Yilun Zhu and Amir Zeldes (2023) "[GENTLE: A Genre-Diverse Multilayer Challenge Set for English NLP and Linguistic Evaluation](https://aclanthology.org/2023.law-1.17.pdf)". In: Proceedings of the Seventeenth Linguistic Annotation Workshop (LAW-XVII 2023), 166–178. Toronto, Canada.

```bibtex
@inproceedings{aoyama-etal-2023-gentle,
    title = "{GENTLE}: A Genre-Diverse Multilayer Challenge Set for {E}nglish {NLP} and Linguistic Evaluation",
    author = "Aoyama, Tatsuya  and
      Behzad, Shabnam  and
      Gessler, Luke  and
      Levine, Lauren  and
      Lin, Jessica  and
      Liu, Yang Janet  and
      Peng, Siyao  and
      Zhu, Yilun  and
      Zeldes, Amir",
    booktitle = "Proceedings of the 17th Linguistic Annotation Workshop (LAW-XVII)",
    year = "2023",
    address = "Toronto, Canada",
    url = "https://aclanthology.org/2023.law-1.17",
    doi = "10.18653/v1/2023.law-1.17",
    pages = "166--178",
}
```


## Directories

The corpus is downloadable in multiple formats. Not all formats contain all annotations: The most accessible format is probably CoNLL-U dependencies (in `dep/`), but the most complete XML representation is in [PAULA XML](https://www.sfb632.uni-potsdam.de/en/paula.html), and the easiest way to search in the corpus is using [ANNIS](http://corpus-tools.org/annis). Here is [an example query](https://gucorpling.org/annis/#_q=ZW50aXR5IC0-YnJpZGdlIGVudGl0eSAmICMxIC0-aGVhZCBsZW1tYT0ib25lIg&_c=R0VOVExF&cl=5&cr=5&s=0&l=10) for phrases headed by 'one' bridging back to a different, previously mentioned entity. Other formats may be useful for other purposes. See website for more details.

  * _build/ - The [build bot](https://gucorpling.org/gum/build.html) and utilities for data merging and validation
  * annis/ - The entire merged corpus, with all annotations, as a relANNIS 3.3 corpus dump, importable into [ANNIS](http://corpus-tools.org/annis)
  * const/ - Constituent trees with function labels and PTB POS tags in the PTB bracketing format (automatic parser output from gold POS with functions projected from gold dependencies)
  * coref/ - Entity and coreference annotation in two formats: 
    * conll/ - CoNLL shared task tabular format (with Wikification but no bridging or split antecedent annotations)
    * tsv/ - WebAnno .tsv format, including entity type, salience and information status annotations, Wikification, bridging, split antecedent and singleton entities
    * ontogum/ - alternative version of coreference annotation in CoNLL, tsv and CoNLL-U formats following OntoNotes guidelines (see Zhu et al. 2021)
  * dep/ - Dependency trees using Universal Dependencies, enriched with metadata, summaries, sentence types, speaker information,  enhanced dependencies, entities, information status, salience, centering, coreference, bridging, Wikification, XML markup, morphological tags/segmentation, CxG constructions, eRST discourse relations/connectives/signals, PDTB style relations and Universal POS tags according to the UD standard
  * paula/ - The entire merged corpus (excl. Reddit) in standoff [PAULA XML](https://github.com/korpling/paula-xml), with all annotations
  * rst/ - Enhanced Rhetorical Structure Theory (eRST) analyses and other discourse relation annotations
    * rstweb/ - full .rs4 format data as used by RSTTool and rstWeb, with secondary edges + relation signals (recommended)
    * lisp_nary/ - n-ary basic RST lisp trees (.dis format) 
    * lisp_binary/ - binarized basic RST lisp trees (.dis format) 
    * dependencies/ - a converted eRST dependency representation with secondary edges in a separate column (.rsd format)
    * disrpt/ - plain segmentation, connective detection and relation-per-line data formats following the DISRPT shared task specification
    * gdtb/ - shallow discourse relations following PDTB v3 guidelines in two formats: PDTB pipes and DISRPT .rels
  * xml/ - vertical XML representations with 1 token or tag per line, metadata, summaries and tab delimited lemmas, morphological segmentation and POS tags (extended VVZ style, vanilla, UPOS and CLAWS5, as well as dependency functions), compatible with the IMS Corpus Workbench (a.k.a. TreeTagger format).
