# 16S_project
## Github for fast species detection using 16S rRNA ONT data

### Introduction
Aim: quick species identification of 16S rRNA ONT data by comparing different pipelines. 

We compared the following 6 different pipelines: 
1. NanoCLUST, 
2. NanoRTax, 
3. BugSeq, 
4. 1928 Diagnostics, 
5. EMU,
6. MABA16S

### Data preprocessing

The datasets provided are from the Academy of Life Sciences Lectorate; the datasets consisted of three samples: 
1. Tuberulosis sample (One species: Mycobacterium tuberculosis 100%) 
2. Spike sample (two species: Imtechella halotolerans, and Allobacillus halotolerans) 
3. Zymomock community (eight bacterial species, two fungi)

All datasets were then trimmed on a minimim read length of 1400 bp, maximum read length of 1700 bp and a mimnimum PHRED score of 10 using NanoFILT (https://github.com/wdecoster/nanofilt.git).
<br>
The trimmed datasets were then used as the input for each pipeline.

### Workflow
The workflow used for this project is visualised in the image below:

[16S ONT version4.pdf](https://github.com/liuweisu/16S_project/files/11763647/16S.ONT.version4.pdf)

![16S ONT version4](https://github.com/liuweisu/16S_project/assets/127951831/efa7c734-8ceb-4164-b784-c26e7acaee5f)

### Code availability 
- The changed code for NanoCLUST and NanoRTax can be found in the links in respective order: 
<br> - https://github.com/liuweisu/NanoCLUST.git 
<br> - https://github.com/liuweisu/NanoRTax.git 
<br> Later, the changed code can also be found in this repository 16S_project/pipeline_NanoCLUST/NanoCLUST-master.zip and 16S_project/NanoRTax, in respective order. 
- A copy of the MABA16S repository can be found in the original repository of MUMC-MEDMIC: 
<br> -https://github.com/MUMC-MEDMIC/MABA16S.git
<br> A copy of the MABA16S repository can later also be found in this repository; 16S_project/pipeline_MABA16S. 
- The link to the EMU repository is available on gitlab: https://gitlab.com/treangenlab/emu.git
- Since BugSeq and 1928 Diagnostics are online platforms, these pipelines do not have a github page. Instead, the links to BugSeq and 1928 Diagnostics are given:
<br> - BugSeq: https://bugseq.com/
<br> - 1928 Diagnostics: https://www.1928diagnostics.com/


