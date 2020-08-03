# Assignment the First

## Part 1
1. Be sure to upload your Python script.

| File name | label |
|---|---|
| 1294_S1_L008_R1_001.fastq.gz | read1 |
| 1294_S1_L008_R2_001.fastq.gz | index1 |
| 1294_S1_L008_R3_001.fastq.gz | index2 |
| 1294_S1_L008_R4_001.fastq.gz | read2 |

2. Per-base NT distribution
    1.  R1 histogram
        ![R1 histogram](https://github.com/2020-bgmp/demultiplexing-megan-criss/blob/master/Assignment-the-first/r1_avg_phredperposition.png)
        R2 histogram
        ![R2 histogram](https://github.com/2020-bgmp/demultiplexing-megan-criss/blob/master/Assignment-the-first/r2_avg_phredperposition.png)
        R3 histogram
        ![R3 histogram](https://github.com/2020-bgmp/demultiplexing-megan-criss/blob/master/Assignment-the-first/r3_avg_phredperposition.png)
        R4 histogram
        ![R4 histogram](https://github.com/2020-bgmp/demultiplexing-megan-criss/blob/master/Assignment-the-first/r4_avg_phredperposition.png)
    2. Based on these histograms, I would say that a good quality score cutoff would be 25 for this data. It appears that the averages are mostly over 30,      however some are slightly below 30. Because of this, I think that having a quality score cutoff of 25 would take out any  really bad data, while keeping both the good and average data. I believe the standard cutoff score is 20, so 25 is just a little higher than that.
    3.  
            zcat /projects/bgmp/shared/2017_sequencing/1294_S1_L008_R2_001.fastq.gz | awk 'NR%4 ==2'| grep "N" | wc -l
            3976613
            zcat /projects/bgmp/shared/2017_sequencing/1294_S1_L008_R2_001.fastq.gz | awk 'NR%4 ==2'| grep "N" | wc -l
            3328051         
            
3328051+3976613=7304664 indexes


## Part 2
1. Define the problem
2. Describe output
3. Upload your [4 input FASTQ files](../TEST-input_FASTQ) and your [4 expected output FASTQ files](../TEST-output_FASTQ).
4. Pseudocode
5. High level functions. For each function, be sure to include:
    1. Description/doc string
    2. Function headers (name and parameters)
    3. Test examples for individual functions
    4. Return statement
