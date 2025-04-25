# Summary

UD_Coptic-Bohairic contains manually annotated Bohairic Coptic texts, including Biblical narrative and poetic texts, epistles, and hagiography.

# Introduction

The Bohairic Coptic Universal Dependency Treebank is a manually annotated corpus of Bohairic Coptic texts, currently containing excerpts from the Bohairic New Testament Gospel of Mark, 1 Corinthians, the Old Testament Book of Habakkuk, lives of Sts. Isaac and Shenoute, and the Coptic version of the Lausiac History. Detailed information about the treebank is available in the reference paper cited below.

The data was digitized or previously available in digital format, and annotated manually for part of speech in the project Coptic Scriptorium. For individual credit and further information see:

http://copticscriptorium.org/

Native Coptic XPOS tags come from the Coptic Scriptorium tag set, which is available from the project and treebank websites.

# Further details

## Basic statistics
|      subcorpus            |        documents            | tokens  |
| ------------------------- | --------------------------- | ------- |
| bohairic.1corinthians     | bohairic.1Cor 1-7           |   4,789 |
| bohairic.habakkuk         | bohairic.Habakkuk 1-3       |   1,988 |
| bohairic.lausiac.history  | bohairic.lausiac.history 1  |   4,453 |
| bohairic.life.isaac       | bohairic.life.isaac 1       |   5,433 |
| bohairic.life.shenoute    | bohairic.life.shenoute 1    |   4,970 |
| bohairic.mark             | bohairic.Mark 1-9           |  11,091 |
|                           | Total:                      |  32,724 |

## Tokenization

Coptic was originally written in scriptio continua, without spaces, and modern conventions fuse multiple tokens into so-called bound groups, collapsing clitic pronouns, prepositions and other morphemes into single orthographic units.

The Coptic Treebanks annotate these bound groups as 'multi-word' tokens (MWTs). However, morphological units below the POS level, including affixes and fused compounds (incorporation), are annotated in the treebank in the MISC column, using an attribute `MSeg=A-B-C`, where A, B and C are constituent morphemes of a complex word. There is also a further attribute in the MISC column, called Orig, which appears whenever normalization has taken place and renders the word form as it appeared in the original manuscript. This can include removal of optional diacritics and contracted forms of nomina sacra, which appear expanded in the word form column.

Note that for some fused forms carrying multiple parts of speech, the native Coptic POS tag set assigns portmanteau tags, such as APST_PPERS (auxiliary, past, fused with a subject personal pronoun). In the UD guidelines for Coptic, these forms are tolerated by always selecting the argument as the function-determining unit. Thus APST_PPERS, the past auxiliary with fused pronoun, is attached as *nsubj*, ignoring the *aux* dependency. In a future version, we are considering integrating a more subtle analysis using enhanced dependencies.

For more information on Coptic tokenization, see the Coptic Scriptorium website.

## Entities and Wikification

The data contains partial annotations of typed named and non-named entities (not yet complete for all documents), using the same ten entity types as UD_English-GUM and UD_Coptic-Scriptorium:

  * abstract
  * animal
  * event
  * object
  * organization
  * person
  * place
  * plant
  * substance
  * time

These annotations appear in the MISC column and are bracketed in the conllua convention described by [Universal Anaphora](https://universalanaphora.org/) and the [CorefUD](https://ufal.mff.cuni.cz/corefud) format. Named entities for which corresponding Wikipedia articles exist are also suffixed with a Wikification identifier corresponding to the title of their Wikipedia page, as seen for example for Paul the Apostle and Jesus in the following example:

```CoNLL-U
# newdoc id = bohairic.1corinthians:bohairic.1Cor_01
# global.Entity = etype-identity
# meta::author = Paul the apostle
# meta::document_cts_urn = urn:cts:copticLit:nt.1cor.bohairic_ed:1
# meta::source = Hany Takla, Marcion Project
# meta::title = Bohairic 1 Corinthians 1 (Digital Edition)
# sent_id = bohairic_1corinthians-bohairic_1Cor_01_s0001
# text_en = Paul, called to be an apostle of Jesus Christ through the will of God, and our brother Sosthenes,
# text = ⲡⲁⲩⲗⲟⲥ ⲡⲁⲡⲟⲥⲧⲟⲗⲟⲥ ⲉⲧⲑⲁϩⲉⲙ ⲛⲧⲉⲓⲏⲥⲟⲩⲥ ⲡⲭⲣⲓⲥⲧⲟⲥ ⲉⲃⲟⲗ ϩⲓⲧⲉⲛⲫⲟⲩⲱϣ ⲙⲫⲛⲟⲩϯ ⲛⲉⲙⲥⲱⲥⲑⲉⲛⲏⲥ ⲡⲓⲥⲟⲛ
1	ⲡⲁⲩⲗⲟⲥ	ⲡⲁⲩⲗⲟⲥ	PROPN	NPROP	Foreign=Yes	0	root	_	Entity=(person-Paul_the_Apostle|OrigLang=grc
2-3	ⲡⲁⲡⲟⲥⲧⲟⲗⲟⲥ	_	_	_	_	_	_	_	_
2	ⲡ	ⲡ	DET	ART	Definite=Def|Gender=Masc|Number=Sing|PronType=Art	3	det	_	_
3	ⲁⲡⲟⲥⲧⲟⲗⲟⲥ	ⲁⲡⲟⲥⲧⲟⲗⲟⲥ	NOUN	N	Foreign=Yes	1	appos	_	OrigLang=grc
4-5	ⲉⲧⲑⲁϩⲉⲙ	_	_	_	_	_	_	_	_
4	ⲉⲧ	ⲉⲧⲉ	SCONJ	CREL	_	5	mark	_	_
5	ⲑⲁϩⲉⲙ	ⲑⲱϩⲉⲙ	VERB	VSTAT	VerbForm=Fin	3	acl:relcl	_	_
6-7	ⲛⲧⲉⲓⲏⲥⲟⲩⲥ	_	_	_	_	_	_	_	_
6	ⲛⲧⲉ	ⲛⲧⲉ	ADP	PREP	_	7	case	_	_
7	ⲓⲏⲥⲟⲩⲥ	ⲓⲏⲥⲟⲩⲥ	PROPN	NPROP	Foreign=Yes	3	nmod	_	Entity=(person-Jesus|OrigLang=heb
8-9	ⲡⲭⲣⲓⲥⲧⲟⲥ	_	_	_	_	_	_	_	_
8	ⲡ	ⲡ	DET	ART	Definite=Def|Gender=Masc|Number=Sing|PronType=Art	9	det	_	_
9	ⲭⲣⲓⲥⲧⲟⲥ	ⲭⲣⲓⲥⲧⲟⲥ	NOUN	N	Foreign=Yes	7	appos	_	Entity=person-Jesus)|OrigLang=grc
10	ⲉⲃⲟⲗ	ⲉⲃⲟⲗ	ADV	ADV	ExtPos=ADP	13	case	_	_
11-13	ϩⲓⲧⲉⲛⲫⲟⲩⲱϣ	_	_	_	_	_	_	_	_
11	ϩⲓⲧⲉⲛ	ϩⲓⲧⲉⲛ	ADP	PREP	_	10	fixed	_	_
12	ⲫ	ⲡ	DET	ART	Definite=Def|Gender=Masc|Number=Sing|PronType=Art	13	det	_	Entity=(abstract
13	ⲟⲩⲱϣ	ⲟⲩⲱϣ	NOUN	N	_	5	obl	_	_
14-16	ⲙⲫⲛⲟⲩϯ	_	_	_	_	_	_	_	_
14	ⲙ	ⲛ	ADP	PREP	_	16	case	_	_
15	ⲫ	ⲡ	DET	ART	Definite=Def|Gender=Masc|Number=Sing|PronType=Art	16	det	_	Entity=(person
16	ⲛⲟⲩϯ	ⲛⲟⲩϯ	NOUN	N	_	13	nmod	_	Entity=person)abstract)person-Paul_the_Apostle)
17-18	ⲛⲉⲙⲥⲱⲥⲑⲉⲛⲏⲥ	_	_	_	_	_	_	_	_
17	ⲛⲉⲙ	ⲛⲉⲙ	ADP	PREP	_	18	cc	_	_
18	ⲥⲱⲥⲑⲉⲛⲏⲥ	ⲥⲱⲥⲑⲉⲛⲏⲥ	NOUN	N	Foreign=Yes	1	conj	_	Entity=(person|OrigLang=grc
19-20	ⲡⲓⲥⲟⲛ	_	_	_	_	_	_	_	_
19	ⲡⲓ	ⲡⲓ	DET	ART	Definite=Def|Gender=Masc|Number=Sing|PronType=Art	20	det	_	_
20	ⲥⲟⲛ	ⲥⲟⲛ	NOUN	N	_	18	appos	_	Entity=person)
```

## Cxn

We use the MISC field `Cxn` annotation to distinguish some complex constructions in a Construction Grammar (CxG) framework developed by collaborators from [Dagstuhl Seminar 23191](https://www.dagstuhl.de/en/seminars/seminar-calendar/seminar-details/23191) for the integration of CxG analyses into UD trees. Construction labels are always attached to the highest token belonging to the necessary or defining elements of the construction, and carry hierarchical designations, such as a prefix `Cxn=Conditional` for all conditional constructions, but a more specific `Cxn=Conditional-NegativeEpistemic` for negative epistemic conditionals (the unrealized type seen in "if one had, then one would have"). Individual elements of a construction, such as the Protasis or the Apodosis are annotated using the `CxnElt` MISC annotation. For more information and for work using these annotations, please refer to [Weissweiler et al. 2024](https://aclanthology.org/2024.lrec-main.1471).

# Acknowledgments

The underlying POS tagged material was produced as part of the project Coptic Scriptorium, funded by the NEH (see http://copticscriptorium.org/ for more details). Treebank annotation was done mainly by Nina Speransky and Amir Zeldes. Thanks are also due to Nicholas Wagner for contributions to the annotation of the underlying texts and their POS and entity tagging.

# Data Splits

Dataset splits attempt to balance genres across all sets, as well as preserve contiguous documents whenever possible. Sentence and document IDs in the data indicate the respective source texts. Sentences are not shuffled.

# References

To cite the treebank please refer to the following paper:

  * Zeldes, Amir, Speransky, Nina, Wagner, Nicholas & Schroeder, Caroline T. (2025). "A UD Treebank for Bohairic Coptic". ArXiv preprint.

```bibtex
@Electronic{ZeldesEtAl2025,
  author       = {Amir Zeldes and Nina Speransky and 
                  Nicholas Wagner and Caroline T. Schroeder},
  title        = {A {UD} Treebank for {B}ohairic {C}optic},
  howpublished = {Arxiv Preprint},
  year         = {2025}
}
```

# Changelog

  * 2025-05-15 v2.16

Initial release in Universal Dependencies.

=== Machine readable metadata ==============

Documentation status: complete
Data source: manual
Data available since: UD v2.16
License: CC BY 4.0
Includes text: yes
Lemmas: manual native
UPOS: converted from manual
XPOS: manual native
Features: automatic
Relations: manual native
Genre: bible fiction nonfiction
Contributors: Zeldes, Amir; Speransky Nina
Contributing: elsewhere
Contact: amir.zeldes@georgetown.edu

============================================