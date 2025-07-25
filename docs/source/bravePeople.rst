Advanced use cases
==================

SCARLET is quite versative since it allows to mix the different utilities depending on the needs of the user.
The following instructions refer to advanced strategies which go behyond classifying cells or generate cell type specific list of genes.

Use custom lists in SCARLET.py
----------------------------

Suppose that the pipeline of **SCARLET_AnnotaionListsBuilder.py** was exploit to generate the cell type specific lists of genes from an annotation file. The idea is to use these lists for classification. Therefore, the directory containg the lists of SCARLET.py must be changed. 

This can be achieved adjusting a parameter of the classifier in this way:

::

  python3 SCARLET.py new_read_counts.tsv -Types custom -Notation gene_symbol -Min 300 -CPUs 2

Or

::

  python3 SCARLET.py new_read_counts.tsv --Types custom --Notation gene_symbol --Min 300 --CPUs 2

Changing the paratemeter value of **Types** to **custom** forces SCARLET.py to use the lists of genes originated from the annotation file as reference lists for classification.

.. note::

   It is important that, in the previously described case, the new counts used in the classification must have the same gene notation of the counts used for the generation of the lists. So, if the gene symbols are present, specify -Notation gene_symbol or --Notation gene_symbol. Differently, if the ensembl ids are used, specify -Notation ensembl_id or --Notation ensembl_id or leave default setting.


