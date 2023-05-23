# OntoGENTLE coreference data

This directory contains an alternative version of the coreference annotations in GENTLE, following the OntoNotes annotation scheme. This means in particular:

  * Singleton mentions (entities mentioned only once in a document) are excluded
  * Non-named compound modifiers cannot corefer with other mention and are therefore never included
  * Predicative mentions are considered non-referential and are excluded
  * Indefinite NPs can only be antecedents, but not anaphors
  * Co-referetial verbal spans (e.g. "X [visited] Spain ... the visit") encompass only the main lexical verb of the anaphoric expression span
  * Non-identity coreference, such as bridging anaphora is excluded

As well as several other less frequent adjustments. In general, this means that this data has substantially fewer coreference annotations than the data in `coref/gentle/`. The OntoGENTLE data can be used for out-of-domain evaluation of coreference resolution systems trained on OntoNotes, as well as for supplementing OntoNotes training and development data. If you use this data for an academic paper, please cite the following reference, which describes the conversion process of the larger GUM corpus to the OntoGUM version:

```
@InProceedings{ZhuEtAl2021,
  author    = {Yilun Zhu and Sameer Pradhan and Amir Zeldes},
  booktitle = {Proceedings of ACL-IJCNLP 2021},
  title     = {{OntoGUM}: Evaluating Contextualized {SOTA} Coreference Resolution on 12 More Genres},
  year      = {2021},
  pages     = {461--467},
  address   = {Bangkok, Thailand}
}
```

For more information on this data and an evaluation of OntoNotes coreference resolution on OntoGUM data, please see the paper.

