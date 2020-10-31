# QuiNE-ground-truth-1.0
The QuiNE-ground-truth-1.0 was constructed as part of the paper "Expert Concept-Modeling Ground Truth Construction for Word Embeddings Evaluation in Concept-Focused Domains", (forthcoming, COLING 2020).

QuiNE-ground-truth-1.0 contains
(a) a corpus;
(b) a conceptual model and multiple research questions, distilled from the model by experts, that can be answered on the basis of the corpus; 
(c) lists of terms (preferably hierarchically ordered) manually selected and linked by experts to the concepts appearing in the model; 
(d) automatically segmentable fragments of text, ideally paragraphs, in which terms linked to the concepts appear and that are judged by experts relevant to the research questions, preferably with a varying degree of relevance.

The Quine in Context dataset contains all philosophical texts written by W. V. Quine (228 books and articles from between 1932 and 2008) in plaintext format. Every file in the dataset corresponds to one single article or one section, chapter or essay of a book, resulting in a total of 818 files. The dataset has been produced from pdf files, which have been first OCR-ed, and then manually cleaned by the Quine in Context Project team (Katjoesja Kruiger, Suze van Scheers, Lisa Dondorp, Thijs Ossenkoppele, Maud van Lier, Yvette Oortwijn) and by the student cohorts of Arianna Betti's slow-reading class on Quine's Word and Object in 2015/16 and 2016/17 at the University of Amsterdam (https://quine1960.wordpress.com/about/), supervised by the project team. All data that is irrelevant to the content of the article or section has been removed. This includes information on the institution the article or book was published at, repeating headers with the title of the chapter and metadata. Some of the texts are formula-rich and/or symbol-rich: formulas and symbols were replaced by short codes (XfZ and XsZ), which function as place-holders. For precise instructions for cleaning, one can find the manual that was used here https://docs.google.com/document/d/1UOEPdWxEmNs73N7nO2p2McfISfTryMzMSZw0e-VM_XM/edit?usp=sharing. This document contains all the settings to be used in the OCR software ABBYY Finereader, and all the steps for manual correction after processing by ABBYY. Subsequently, paragraph structure was detected and restored using purpose-built normalization scripts geared towards batches of texts displaying ranges of similar shortcomings, ad-hoc command lines and finally visual inspection - at times involving comparison to the book images - and manual editing by means of a good editor.

The uniformized Quine texts were converted to FoLiA XML by means of UCTO (https://languagemachines.github.io/ucto/) running its English language module. FoLiA mainly segments texts into divisions, paragraphs and, after sentence detection and tokenization, into sentences and words. For the lemmatized version of the corpus, we enticed the FoLiA XML and attendant tool developers to provide a module (https://github.com/proycon/spacy2folia) to extract the Quine texts from FoLiA, feed them through the multilingual system Spacy (https://spacy.io/) and reincorporate the lemma and POS enriched text back into the appropriate FoLiA. We ran Spacy on the QUINE corpus in this fashion, using the core model for English (en_core_web_sm) available from its website.

## Contributors 
- Arianna Betti 
- Thijs Ossenkoppele 
- Yvette Oortwijn 
- Martin Reynaert
