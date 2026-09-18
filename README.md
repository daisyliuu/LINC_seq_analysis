# LINC_seq_analysis
Analysis pipeline for LINC-seq: NGS read processing, enrichment scoring, and count-table generation for combinatorial TCR-peptide-MHC library screens.
All steps are implemented as parameterized functions in a single notebook, linc_seq_pipeline.ipynb. Edit the configuration block at the top of the notebook to point the pipeline at a new sample.

# System requirements
Operating system: macOS or Linux (the pipeline calls external command-line tools via subprocess; Windows is not directly supported, but works under WSL).

Python: 3.9 or later. Tested with Python 3.10.
Python packages:
pandas
numpy
scipy

External command-line tools (must be installed and available on your PATH):
cutadapt — adapter and length trimming
fastp — quality filtering
seqtk — read sampling / reverse complement (preprocessing log only)
pigz — parallel gzip compression/decompression
## Running analyses on your data
Place your paired-end FASTQ files in a directory
Run the notebook sections in order (trimming/QC → merging/filtering → translation/scoring → reformatting → optional multi-sample merge).
