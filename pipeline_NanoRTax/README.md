# NanoRTax

The changed NanoRTax code is the NanoRTax-master.zip file

Input file: 
- FASTQ file

Output files: 
- Computational power used per step
- FASTQC
- Relative abundance per taxonomic class (Order, Family, Genus, Species)
- Read clusters


------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Quick Start
i. Install nextflow

ii. Install either Docker for full pipeline reproducibility or use Conda

iii. Download the pipeline and example databases and test it on a minimal dataset with a single command

**#UPDATE:Taxonomic data necessary for taxonkit**
<br>
`wget ftp://ftp.ncbi.nih.gov/pub/taxonomy/taxdump.tar.gz
<br>
tar -xzvf taxdump.tar.gz -C db/`
<br>
**#BLAST database**
<br>
`mkdir db db/taxdb`
<br>
`wget https://ftp.ncbi.nlm.nih.gov/blast/db/16S_ribosomal_RNA.tar.gz && tar -xzvf 16S_ribosomal_RNA.tar.gz -C db`
<br>
`wget https://ftp.ncbi.nlm.nih.gov/blast/db/taxdb.tar.gz && tar -xzvf taxdb.tar.gz -C db/taxdb`
<br>
**#Kraken2 RDP database**
<br>
`wget ftp://ftp.ccb.jhu.edu/pub/data/kraken2_dbs/16S_RDP11.5_20200326.tgz && tar -xzvf 16S_RDP11.5_20200326.tgz -C db`
<br>

**#Centrifuge P_COMPRESSED database (more information: https://ccb.jhu.edu/software/centrifuge/manual.shtml#database-download-and-index-building)**
<br>
`wget https://genome-idx.s3.amazonaws.com/centrifuge/p_compressed_2018_4_15.tar.gz && tar -xzvf p_compressed_2018_4_15.tar.gz -C db'`

------------------------------------------------------------------------------------------------------------------------------------------------------------------

**TEST RUN USING THE TEST DATASET**

`nextflow run main.nf -profile test,<docker/conda>`

<br> 
------------------------------------------------------------------------------------------------------------------------------------------------------------------
<br>
iv. Start running your own analysis!

We provide an example configuration profile with the default parameters for running the pipeline (conf/default.config) and it is a good starting point to easily customize your NanoRTax workflow. This configuration is loaded by specifying "default" in the profiles list of pipeline command.

a. Run classification on a single FASTQ file

`nextflow run main.nf -profile <default,docker/conda> --reads '/seq_path/sample.fastq'`
<br> 
b. Run classification on an entire sequencing run directory. NanoRTax will detect the barcode directories and analyze all samples:

`nextflow run main.nf -profile <default,docker/conda> --reads '/seq_path/fastq_pass/**/*.fastq'`
<br> 
c. Real-time mode.
<br>

`nextflow run main.nf -profile <default,docker/conda> --reads_rt '/seq_path/fastq_pass/**/*.fastq'`
<br>

Similar to the normal mode but using --reads_rt for input. Partial results are stored in an output directory and are accessible as .csv file and web app visualization files. In this mode, the workflow will run endlessly, so it needs to be stopped manually by Ctrl+C once all FASTQ files are completely processed.

Note: This mode is intended to work with non-bulk FASTQ files (ie: 500 reads per file) in order to provide a fluid real-time analysis of generated reads. This aspect can be configured before starting the experiment via MinKNOW sequencing software.

v. Visualize partial/complete outputs using NanoRTax web application (./viz_webapp)

Before running the web application, make sure to have the necessary dependencies installed or use the provided viz_webapp/environment.yml file to build a conda environment (recommended):

`conda env create -f environment.yml`
`conda activate nanortax_webapp`
Start the web application server with the command below and access the interface with a web browser (http://127.0.0.1:8050/ by default).

`cd viz_webapp && python dashboard.py`
See usage docs for all of the available options when running the pipeline.
