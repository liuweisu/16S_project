## Data-Analysis pipelines for fast species detection using 16S rRNA ONT data

### Description
An overview of several 16S species identification pipelines to help investigate the clinical suitability of ONT post-processing tools. As shown in the image below, the pipelines use ONT long read data in FastQ format as input files. Before processing through the pipelines, de data first needs to undergo a quality control step followed by a trimming step to remove all reads below 1400 and above 1700 bp. The data was then processed in the NanoCLUST, NanoRTax, BugSeq, 1928, EMU and MABA16S pipelines.

![16S ONT version4](https://github.com/liuweisu/16S_project/assets/127951831/efa7c734-8ceb-4164-b784-c26e7acaee5f)

### Data preprocessing
Provided datasets are from the Academy of Life Sciences Lectorate and consist of: 
1. Tuberulosis sample (One species: Mycobacterium tuberculosis 100%) 
2. Spike sample (two species: Imtechella halotolerans, and Allobacillus halotolerans) 
3. Zymomock community (eight bacterial species, two fungi)

All datasets were then trimmed on a minimim read length of 1400 bp, maximum read length of 1700 bp and a mimnimum PHRED score of 10 using NanoFILT (https://github.com/wdecoster/nanofilt.git). The trimmed datasets were then used as the input for each pipeline. <br>

### Pipeline overview
| **Tool**        | **Input**                              | **Output**   |
| :---            | :---                                   | :---    |
| NanoCLUST       | Unzipped FastQ files                   | Text file |
| NanoRTax        | Unzipped FastQ files                   | Text file and Dash visualisation |
| BugSeq          | Zipped or Unzipped FastQ files         | PDF file and outputs for visualisation in QIIME2 |
| 1928            | Zipped or Unzipped FastQ files         | PDF file output and online visualisation |
| EMU             | Unzipped FastQ files                   | Text file |
| MABA16s         | Zipped files                           | Text file| <br>


### Code availability 
- Revised code for NanoCLUST and NanoRTax can be found on the [NanoCLUST](https://github.com/liuweisu/16S_project/tree/main/pipeline_NanoCLUST) and [NanoRTax](https://github.com/liuweisu/16S_project/tree/main/pipeline_NanoRTax) pages in this GitHub. 
- A copy of the MABA16S repository can be accessed [here](https://github.com/liuweisu/16S_project/tree/main/pipeline_MABA16S). 
- The EMU repository is available on GitLab: https://gitlab.com/treangenlab/emu.git
- The BugSeq online platform can be accessed through https://bugseq.com/
- 1928 Diagnostics can be reached here: https://www.1928diagnostics.com/
