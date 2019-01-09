# CRISPR-Net: A Fused Recurrent Convolutional Network Quantifies CRISPR Off-target Activities with Indels and Mismatches
This repository includes a fused long-term recurrent convolutional neural network for predicting the off-targets activities with indels and mismatches in CRISPR/Cas9 gene editing.

# PREREQUISITE
CRISPR-Net was conducted by using Python 3.6 and TensorFlow v1.4.1. 
Following Python packages should be installed:
<ul>
<li><p>scipy</p></li>
<li><p>numpy</p></li>
<li><p>pandas</p></li>
<li><p>scikit-learn</p></li>
<li><p>TensorFlow</p></li>
</ul>

# Usage

CRISPR-Net can run with:

    CRISPR_net.py [-h] input_file

positional arguments: input_file

optional arguments:
  -h, --help  show this help message and exit

Example input file:

GAGT_CCGAGCAGAAGAAGAATGG,GAGTACCAAGTAGAAGAAAAATTT
GTTGCCCCACAGGGCAGTAAAGG,GTGGACACCCCGGGCAGGAAAGG
GGGTGGGGGGAGTTTGCTCCCGG,GTGTGGGGTAAATTTGCTCCCAG
GGGTGGGGGGAGTTTGCTCCAGG,AGGTGGGGTGA_TTTGCTCCAGG

Save it as 'input.txt'.

Now you can run CRISPR-Net as following:

    $> ./CRISPR_net.py input.txt
    ...
Then output file will be generated :
- The first column of the output file indicates the given query sequence,
- The second column is the FASTA title (if you downloaded it from UCSC or Ensembl, it is usually a chromosome name),
- The third column is the position of the off-target site (same convention with Bowtie),

out.txt:

    GGCCGACCTGTCGCTGACGCNNN chr8    49679        GGgCatCCTGTCGCaGACaCAGG +       5
    GGCCGACCTGTCGCTGACGCNNN chr8    517739       GcCCtgCaTGTgGCTGACGCAGG +       5
    GGCCGACCTGTCGCTGACGCNNN chr8    599935       tGCCGtCtTcTCcCTGACGCCAG -       5
    GGCCGACCTGTCGCTGACGCNNN chr8    5308348      GGCaGgCCTGgCttTGACGCAGG -       5
    GGCCGACCTGTCGCTGACGCNNN chr8    9525579      GGCCcAgCTGTtGCTGAtGaAAG +       5
    GGCCGACCTGTCGCTGACGCNNN chr8    12657177     GGCCcACCTGTgGCTGcCcaTAG -       5
    GGCCGACCTGTCGCTGACGCNNN chr8    12808911     GGCCGACCaGgtGCTccCGCCGG +       5
    GGCCGACCTGTCGCTGACGCNNN chr8    21351922     GGCCcACCTGaCtCTGAgGaCAG -       5
    GGCCGACCTGTCGCTGACGCNNN chr8    21965064     GGCCGtCCTGcgGCTGctGCAGG -       5
    GGCCGACCTGTCGCTGACGCNNN chr8    22409058     GcCCGACCccTCcCcGACGCCAG +       5
--------------------------------------------------
CRISPR-Net-mismatches-only can run with:

    CRISPR_net_mismatches_only.py [-h] input_file

positional arguments: input_file

Example input file:

GATGGTAGATGGAGACTCAGAGG,GGTAGGAAATGGAGAGGCAGAGG
GGGTGGGGGGAGTTTGCTCCCGG,GTGTGGGGTAAATTTGCTCCCAG

optional arguments:
  -h, --help  show this help message and exit


# CONTAINS:
<ul>
<li><p>CFDScoring/cfd-score-calculator.py : Python script to run CFD score </p></li>
<li><p>predictions/cnn_std_prediction_TF.py : CNN_std conducted by TensorFlow</p></li>
<li><p>predictions/cnn_std_keras.py : CNN_std conducted by Keras used for off-target prediction </p></li>
</p></li>
</ul>

---------------------------------------
Jiecong Lin

jieconlin3-c@my.cityu.edu.hk

January 10 2019
