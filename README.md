The code needs the following dependencies:

eigen3: http://eigen.tuxfamily.org/index.php?title=Main_Page

boost: http://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html

methgl: http://mathgl.sourceforge.net/doc_en/Installation.html

After installing the dependencies the object file can be make using:

g++ *.cpp -Wno-return-type-c-linkage -I <path to eigeb3> -o out -I <path to mathgl> -lmgl -std=gnu++11

example:

g++ *.cpp -Wno-return-type-c-linkage -I /usr/local/Cellar/eigen/3.2.8/include/eigen3/  -o a  -I /usr/local/include/ -lmgl -std=gnu++11

Finally you can use out to run the code. there is a number of options:

-fa <filepath> : the fasta file to be processed by MLBP_BIN

-svdd <dim> : the SVD dimension, default: 60

-mlbpn <dim> : the MLBP window length, default: 8

-outdir <filepath> : a directory that all the MLBP_BIN results will be saved including cluster labels and .png figure

-no_clust <num> : the number of clusters for kmeans++, default: 10

-covpm <num> : a file contains average coverage depth

-covpstd <num> : a file contains standard deviation coverage depth

-reps <method> : the numerical mapping including EIIP, Real, Integer, Paired, Atomic, default: EIIP

-clust <method> : the clustering method kmeans++ or dbscan: dbscan

-dbep <num> : the epsilon for dbscan, default: 0.02

-dbminpt <num> : the number of minimum neighbouring points for dbscan, default: 8

-save_feat : If the features needs to be saved separately.

examples: 

1. Running with default option on a fasta file indicated by the path and save the results in desired directory

./out -fa /pathtofile/file.fa -outdir /pathtofile/file.fa


2. Check the available options

./out -help

3. run using coverage profile

./out -fa /pathtofile/file.fa -covpm /pathtofile/cpm -covpstd /pathtofile/cpstd


Codes for kmeans++ and dbsacan have been downloaded and modified to match our code:
kmeans++: http://rosettacode.org/wiki/K-means%2B%2B_clustering
dbscan: https://github.com/propanoid/DBSCAN

if there is any question or any bug please email me at <kouchaki.samaneh@gmail.com>

