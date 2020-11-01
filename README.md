# QuiNE-GT 1.0
QuiNE-GT 1.0 is the first release of QuiNE-GT, an expert-controlled, concept-focused ground truth constructed as part of the paper "Expert Concept-Modeling Ground Truth Construction for Word Embeddings Evaluation in Concept-Focused Domains", (forthcoming, COLING 2020).

QuiNE-GT 1.0 consists of
(a) a corpus;
(b) a conceptual model and multiple research questions, distilled from the model by experts, that can be answered on the basis of the corpus; 
(c) lists of terms (hierarchically ordered) manually selected and linked by experts to the concepts appearing in the model; 
(d) specifically delimited text segments that are identifiable and retrievable by means of a uniquer identifier, in which terms linked to the concepts appear and that are judged by experts relevant to the research questions, with a varying degree of relevance.

Unfortunately, it is not possible for us to release our Quine datasets from the Quine in Context corpus at this moment for copyright reasons, as the books from the Quine corpus are copyrighted. If you do own the works in the corpus, contact us for the derived data sets. Construction of the Quine in Context dataset is described below for rough reproducibility.

## Ground truth construction log

A step-by-step overview of the ground truth construction is available [here](https://docs.google.com/document/d/1ffZD3iTT_P_JWY4-ujAP_XQDnUuv2DwRKHQjWTNFvq0/edit?usp=sharing).

## The Quine in Context corpus  
The Quine in Context dataset contains all philosophical texts written by W. V. Quine (228 books and articles from between 1932 and 2008) in plaintext format. Every file in the dataset corresponds to one single article or one section, chapter or essay of a book, resulting in a total of 818 files. The dataset has been produced from pdf files, which have been first OCR-ed, and then manually cleaned by the Quine in Context Project team (Katjoesja Kruiger, Suze van Scheers, Lisa Dondorp, Thijs Ossenkoppele, Maud van Lier, Yvette Oortwijn) and by the student cohorts of Arianna Betti's slow-reading class on Quine's Word and Object in 2015/16 and 2016/17 at the University of Amsterdam (https://quine1960.wordpress.com/about/), supervised by the project team. All data that is irrelevant to the content of the article or section has been removed. This includes information on the institution the article or book was published at, repeating headers with the title of the chapter and metadata. Some of the texts are formula-rich and/or symbol-rich: formulas and symbols were replaced by short codes (XfZ and XsZ), which function as place-holders. For precise instructions for cleaning, one can find the manual that was used [here]( https://docs.google.com/document/d/1UOEPdWxEmNs73N7nO2p2McfISfTryMzMSZw0e-VM_XM/edit?usp=sharing). This document contains all the settings to be used in the OCR software ABBYY Finereader, and all the steps for manual correction after processing by ABBYY. Subsequently, paragraph structure was detected and restored using purpose-built normalization scripts geared towards batches of texts displaying ranges of similar shortcomings, ad-hoc command lines and finally visual inspection - at times involving comparison to the book images - and manual editing by means of a good editor.

The texts were converted to [FoLiA XML] (https://www.semanticscholar.org/paper/FoLiA%3A-A-practical-XML-Format-for-Linguistic-a-and-Gompel-Reynaert/941b849d75f3a899e3b2a04bfeb2297ca6da1f02) using the English language module of [UCTO] (https://languagemachines.github.io/ucto/), which also provided sentence segmentation and tokenization. FoLiA markup can represent text as, and maintain unique identifiers for, sections, paragraphs, sentences and words. FoLiA can also represent the lemma of each word. A dedicated [FoLiA XML module] (https://github.com/proycon/spacy2folia) called on [Spacy] (https://spacy.io/) using the core model for English (Spacy English core model: en\_core\_web\_sm} available from its website to provide lemmatization).

## Model of Naturalism in Quine and research questions
The model of *naturalism* identified by the domain experts is as follows:
1. Epistemology is an autonomous enterprise with respect to science;
2. By 'science' in 1. only the natural sciences are meant.
3. It is not the case that all epistemological concepts related to sources of knowledge are explained, reduced or founded upon scientific concepts only;
  a. (Sensory) perception is not explained, reduced or founded upon scientific concepts only;
  b. Introspection is not explained, reduced or founded upon scientific concepts only;
  c. Memory is not explained, reduced or founded upon scientific concepts only;
  d. Reason is not explained, reduced or founded upon scientific concepts only;
  e. Testimony is not explained, reduced or founded upon scientific concepts only;
4. By 'scientific concepts' in 3. only concepts from the natural sciences (including logic and mathematics) are meant.

The research questions that are addressed in the ground truth are the following three:
1. is *epistemology* an autonomous enterprise with respect to *science*?
2. is the term *science* only meant to include *natural science*?
3. what is the relation between *epistemology* and *pseudo-science*?

## Term lists 
To retrieve relevant passages, the experts constructed five term lists with the use of HitPaRank:
- [List 1](https://docs.google.com/spreadsheets/d/1e1ELwKa1woXGFdj1_2noc1DQApoViLhujiXsUE94iJc/edit?usp=sharing) consists of 64 terms of immediate evidential weight for RQ1 --- the term we model itself (*naturalism*) and those that are immediately related (e.g., *first philosophy*, *scientism*). 
- [List 2](https://docs.google.com/spreadsheets/d/1duP23UQia--MBfbEtqxMpJPtTynK-HMVTxgmjizZzMM/edit?usp=sharing) consists of 70 terms that are related to epistemology (e.g., *evidence*, *know*). These terms are primarily relevant for RQ1. 
- [List 3](https://docs.google.com/spreadsheets/d/1oXPhKNVTteLRea8gkQUDfa2rwoNUrk6EpkENHzeTxTw/edit?usp=sharing) consists of 907 terms for all (broadly) scientific disciplines and their subfields. For this, among other resources, the [HESA](https://www.hesa.ac.uk/support/documentation/jacs/jacs3-detailed) academic coding system was used to get an overview of all academic subjects and their subfields. These terms are primarily relevant for RQ2. 
- [List 4](https://docs.google.com/spreadsheets/d/17OtRJDAQ3UwcoeXy28MJOzCWfusrctUo3huNP6KQvP0/edit?usp=sharing) consists of 45 terms for the building blocks and the procedures of any scientific enterprise (e.g., *theory*, *truth*). These terms are relevant for RQ1 and RQ2. 
- [List 5](https://docs.google.com/spreadsheets/d/1izp6oTHaGzZc1--nYsNUnQrIj77kcx-VIoHq8dhF80I/edit?usp=sharing) consists of 79 terms for pseudo- (e.g. *parapsychology*) and non-sciences (e.g., *religion*) and their basic faculties (e.g., *clairvoyance*, *revelation*). These terms are relevant for RQ3.

## Annotated passages
Output of HitPaRank in its third mode, retrieving all passages with at least one term from the lists: https://ticclops.uvt.nl/QUINETWIG112.20200629.tar.gz  

Passages filtered for different research questions and annotated:
- [RQ1 passages](https://docs.google.com/spreadsheets/d/1q7BAoRxISzsSjNoVFmZ3jlK_h9GvGYqAmdj2e3PLx9w/edit?usp=sharing): all passages containing naturali* out of the output from HitPaRank. In the sheet “naturali”, 179 entries; paragraph identifiers in column C; paragraphs in column H; ranking in column I. In the sheet “stats”, the statistics for the three different rankings. 
- [RQ2 passages](https://drive.google.com/file/d/1xTV8vKwKsDBbXPjvmTvDR2fMa7VVp0cN/view?usp=sharing): all passages according to one of the following conditions (i) containing natural science or hard science, (ii) containing science and at least one high-ranking term from list Y, (iii) containing humanities or soft sci* or social science*, (iv) containing science and boundar* out of the output from HitPaRank. In the sheet “stats Y scored”, the statistics for the three different rankings over all paragraphs. In sheet “scored”, 466 entries; paragraph identifiers in column A; paragraphs in column B; ranking in column C. 
- [RQ3 passages](https://docs.google.com/spreadsheets/d/1I5wNLuUKWVLFebQw-b52lamHn7ptJiea4x6YYeyn0bw/edit?usp=sharing): all passages containing a term from the U list out of the output from HitPaRank. 185 entries; paragraph identifiers in column B; paragraphs in column C; ranking in F. 

## Contributors 
- Arianna Betti 
- Yvette Oortwijn 
- Thijs Ossenkoppele 
- Martin Reynaert
