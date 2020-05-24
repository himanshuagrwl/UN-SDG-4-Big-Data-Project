# UN-SDG-4-Big-Data-Project

## About:
This project is done as part of the CSE 545 Big Data Analytics at Stony Brook University Spring 2020.
The aim of this project is to work towards the UN-SDG-4 Quality Education. A complete report of this project is available in this reporsitory.

## Concepts Used:
In this project I have used various big-data concepts as follows:
1. Similarity Search (Using Cosine Similarity)
2. Hypothesis Testing

## Technologies Used:
1. Apache Spark (on Google Cloud Platform Clusters)
2. Hadoop Distributed File System (HDFS)
3. MapReduce Concept

## How to Run:
The dataset is included for reference.
Steps:
1. Setup an apache framework on HDFS(I have used GCP Clusters running Apache Spark)
2. Preprocess Step- Run the data_preprocess.py by using Spark Submit job. (Please go through file to know about the input file naming and their sequence)

   ` Command: spark-submit data_preprocess.py 'hdfs file paths for all files needed to merge as seperate args'`
   
   **Output:** preprocessed_data.csv is written as the preprocessed data file which will be used for Similarity Search, Hypothesis Testing and Visualization.
3. For Hypothesis testing- The input to this program is preprocessed_data.csv.
    
    `Command: spark-submit hypothesis_testing.py 'hdfs file path'`
4. Similarity Search- The input to this program is preprocessed_data.csv.

   ` Command: spark-submit county_similarity.py 'hdfs file path'`
5. Visualization.ipynb takes input preprocessed_data.csv. It contains the visualization code for getting useful insights from the output data.


### Settings for my GCP CLuster:
Tutorial I used [Link](https://www.youtube.com/watch?v=6DD-vBdJJxk). Configuration is below:

```
Region - us-east1
Zone - us-east1-c
Autoscaling - Off
Scheduled deletion - Off
Enhanced flexibility mode - Off
Master node - Standard (1 master, N workers)
Machine type  - e2-standard-2
Number of GPUs - 0
Primary disk type - pd-standard
Primary disk size - 64GB
Worker nodes - 2
Machine type - e2-highmem-4
Number of GPUs - 0
Primary disk type - pd-standard
Primary disk size - 32GB
Local SSDs - 0
Preemptible worker nodes - 0
Cloud Storage staging bucket   ---
Subnetwork - default
Network tags - None
Internal IP only - No
Image version - 1.4.26-debian9
```
