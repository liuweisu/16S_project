# MABA16S

Code: The MABA16S-main.zip is a copy of the MABA16S pipeline

Input: 
- Folder with a zipped FASTQ file

Output:
- An excel sheet with classification to a genus and species level

How to run the pipeline:

1. Install Python 3.6 or higher, conda environment manager and snakemake
2. git clone https://github.com/MUMC-MEDMIC/MABA16S
3. cd MABA16S/maba16s
4. Run the MABA16S pipeline using the code below:

    Code to run the pipeline:
    <br> 
    `python cli.py snakemake -i folder_containing_nanopore16s_reads -o my_output_directory --cores 1`

**Note 1: DO NOT END THE INPUT PATH DIRECTORY WITH A "/"**
<br>
**Note 2: input are directories which hold your nanopore reads. Naming of the output will be done based on the names of these directories**
