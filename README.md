## iCaMP Lab RNA-seq Variant Calling Pipeline

This is a pipeline developed for variant calling from RNA-seq data.

To run the pipeline, first create a star directory in ./star/ since this is too large be uploaded to github.

To do this, install and/or load star through HPC or conda and run:

```shell
cd star
STAR --runMode genomeGenerate --genomeDir star_mtDNAref_index --genomeFastaFiles ../chrM_reference/chrMref.fa
```

Then, to run the pipeline, use this command:

```shell
snakemake -s iCaMP_Lab_RNA-seq_Variant_Calling_Pipeline.snake --executor cluster-generic --use-conda --cluster-generic-submit-cmd "qsub -P icamp -pe omp {threads} -o {log} -e {log}" --jobs 12 --rerun-incomplete
```