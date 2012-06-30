Python-DP-Means-Clustering
==========================

DP-means K-means clustering algorithms comparison

"cluster.py" has implementations of k-means and dp-means clustering algorithms.

Implementations were intended to be straight-forward, understandable and give
full output for diagnostics, rather than optimized implmentations.

For more information on the dp-means, see Revisiting k-means: New Algorithms via Bayesian Nonparametrics
at http://arxiv.org/abs/1111.0352/

CLUSTERING
==========

> ./cluster.py -h
Usage: cluster.py [options]

Options:
  -h, --help            show this help message and exit
  -k CLUSTERS, --kmeans-clusters=CLUSTERS
                        If present, use kmeans with number of clusters
                        specified
  -l LAM, --lamda=LAM   If preset, use dpmeans with lambda parameters
                        specified


> cat input/c3_s20_f2.csv | ./cluster.py -k2
Tolerance reached at step 3
Iterations completed: 3
Final error: 1.393216
elapsed time: 2.834797 ms

> cat input/c3_s20_f2.csv | ./cluster.py -l2
Tolerance reached at step 2
Iterations completed: 2
Final error: 0.143098
elapsed time: 2.573967 ms

Plot errors,

> ./plotResult.r 
Loading required package: methods
Loading required package: grid
       V1              V2               V3             V4     cluster
 Min.   :1.552   Min.   :0.1274   Min.   :0   Iter-0    :63   0:84   
 1st Qu.:2.179   1st Qu.:1.1073   1st Qu.:0   Iter-1    :63   1:84   
 Median :2.343   Median :3.4010   Median :1   Iter-2    :63   2:84   
 Mean   :3.114   Mean   :2.7831   Mean   :1   Iter-Final:63          
 3rd Qu.:4.822   3rd Qu.:3.8628   3rd Qu.:2                          
 Max.   :5.206   Max.   :4.3299   Max.   :2                          
       V1            V2        
 Min.   :0.0   Min.   :0.1431  
 1st Qu.:0.5   1st Qu.:0.1431  
 Median :1.0   Median :0.1431  
 Mean   :1.0   Mean   :0.1518  
 3rd Qu.:1.5   3rd Qu.:0.1561  
 Max.   :2.0   Max.   :0.1691 

CLUSTERING TESTS
================

> ./test.py > ./output/test.csv
...
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
Tolerance reached at step 1
Iterations completed: 1
Final error: 0.091798
...

Plot the test results,

> ./plotTest.r 
Loading required package: methods
Loading required package: grid
        V1           V2                V3                 V4        
 dp-means:19   Min.   : 0.7065   Min.   : 0.08673   Min.   : 951.8  
 k-means :14   1st Qu.: 1.0684   1st Qu.: 0.10805   1st Qu.:1667.0  
               Median : 2.3492   Median : 0.15049   Median :2372.7  
               Mean   : 4.4026   Mean   : 0.80153   Mean   :2265.1  
               3rd Qu.: 7.0000   3rd Qu.: 0.21527   3rd Qu.:2674.7  
               Max.   :14.0000   Max.   :14.11991   Max.   :3484.1  
      method  
 dp-means:19  
 k-means :14  

