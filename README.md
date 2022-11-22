# T-REX17

Single-Cell RNAseq pipeline
Publicly available single-cell RNAseq raw data of already filtered 1195 samples from a gastrulating human embryo1 was downloaded from ArrayExpress2 under accession code E-MTAB-93883. The GENCODE4 human transcriptome (GRCh37.p13) and its annotation were downloaded and added with both the spliced and un-spliced T-REX17 and the GSC-DT entries. After building the transcriptome index, the transcripts abundance was quantified via Salmon v1.6.05  in quasi-mapping-based mode using the –seqBias and the –gcBias flags. Data was loaded as a scanpy v1.4.46 object, reproducing clustering as reported by Tyser, R. C. v. et al.1 The resulting clusters were visualized via the scanpy UMAP representation in two dimensions, using default parameters (tl.umap). Differential expression of T-REX17, SOX17, GSC-DT, GSC, GATA6-AS1, GATA6, LINC00261, FOXA2 along clusters was visualized by means of scanpy violin plots and dot plot (pl.violin, pl.dotplot). 

Bulk RNAseq pipeline
To compare T-REX17 read counts in endoderm cells with all the other cell types, endoderm and not-endoderm fastq files were combined in two bulk raw files. Each bulk fastq file went through a bulk RNAseq pipeline comprising a pre-alignment quality control via fastQC v0.11.97, adaptor and low-quality bases trimming using cutadapt v3.48, post-QC and reads alignment against the human genome (GRCh37.p13) by means of STAR v2.7.99 (parameters: --outSAMtype BAM SortedByCoordinate, --chimSegmentMin 20, --outSAMstrandField intronMotif, --quantMode GeneCounts).

The jupyter notebook that comprises the scanpy pipeline for scRNA-seq data analysis and the bulk RNA-seq data analysis is the file "scanpy_pipeline" in this directory.
