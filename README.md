This is a pipeline developed for variant calling from RNA-seq data.

To run the pipeline, use this command:

snakemake -s iCaMP_Lab_RNA-seq_Variant_Calling_Pipeline.snake --executor cluster-generic --use-conda --cluster-generic-submit-cmd "qsub -
P icamp -pe omp {threads} -o {log} -e {log}" --jobs 12 --rerun-incomplete
