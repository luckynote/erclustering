# End-to-end Face Detection and Cast Grouping in Movies Using Erdős–Rényi Clustering

This code computes Rank-1 Count similarity scores between N different face images. 


### Compiling

```
g++ -o run.bin main.cpp Rank1Count.h Rank1Count.cpp
```

## Running the tests
By default, this demo code takes as input the encodings of the first 10 LFW images.
```
AJ_Cook/AJ_Cook_0001.jpg
AJ_Lamas/AJ_Lamas_0001.jpg
Aaron_Eckhart/Aaron_Eckhart_0001.jpg
Aaron_Guiel/Aaron_Guiel_0001.jpg
Aaron_Patterson/Aaron_Patterson_0001.jpg
Aaron_Peirsol/Aaron_Peirsol_0001.jpg
Aaron_Peirsol/Aaron_Peirsol_0002.jpg
Aaron_Peirsol/Aaron_Peirsol_0003.jpg
Aaron_Peirsol/Aaron_Peirsol_0004.jpg
Aaron_Pena/Aaron_Pena_0001.jpg
```

```
$ ./run.bin
-------------------------------------------------
>> fname_testset: data/test.data 
>> fname_refset: data/reference.data 
>> gallerysize: 50 
>> F: 4096 
-------------------------------------------------
>> Test set
	+ file name: data/test.data
	+ N: 10 
>> Reference set
	+ file name: data/reference.data
	+ G: 1000 
>> Calling Rank-1 Count...
starting deleteions
accumrnaks
-------------------------------------------------
    0.00    83.99    89.82   116.12    92.19    89.09    99.21   106.27    88.22    50.60 
   84.35     0.00    76.76    93.69    77.62    82.76    71.09    63.25    79.24    89.99 
   87.39    76.74     0.00   114.11    69.47   129.86    99.90    92.30   112.81    74.42 
  117.58    93.75   115.19     0.00    75.61   128.14   129.25    99.41    86.13    77.29 
   90.22    76.91    69.74    75.68     0.00    65.61    71.45    67.46   102.97    75.46 
   86.69    81.84   129.75   122.02    65.61     0.00   314.22   267.77   199.52    85.82 
   96.21    70.65    99.61   125.91    70.90   316.54     0.00   238.06   188.70    64.03 
  105.94    62.35    91.97    97.13    66.99   274.87   242.10     0.00   259.16    75.98 
   89.20    78.46   117.24    87.28   102.93   197.99   192.73   256.73     0.00    76.71 
   50.21    89.23    74.78    77.14    74.23    85.18    63.90    75.17    77.03     0.00 
-------------------------------------------------

```

You can also run the code with the encodings of your own test set 
```
./run.bin {fname_testset} {fname_refset} {gallerySize} {F}
```
where
```
const char *fname_testset="data/test.data"; 	// file name of the test set. a binary file	
const char *fname_refset="data/reference.data"; // file name of the reference set. a binary file 
int gallerySize=50; 				// How large of a gallery to simulate? (default:50)
int F=4096;                                     // feature dimension
```

A binary file can be easily generated from **X**(NxF matrix). Here is a simple code for Matlab users.
```
fid = fopen('data/test.data', 'w');
fwrite(fid, X, 'single');
fclose(fid);
```

## Publication
SouYoung Jin, Hang Su, Chris Stauffer, and Erik Learned-Miller. End-to-end face detection and cast grouping in movies using Erdős–Rényi clustering. International Conference on Computer Vision (ICCV), 10 pages, 2017. [project page](http://souyoungjin.com/erclustering)

## Contact
If you have any questions, please contact [SouYoung Jin](souyoungjin@cs.umass.edu)

## Acknowledgments

This research is based in part upon work supported by the Office of the Director of National Intelligence (ODNI), Intelligence Advanced Research Projects Activity (IARPA) under contract number 2014-14071600010. The views and conclusions contained herein are those of the authors and should not be interpreted as necessarily representing the official policies or endorsements, either expressed or implied, of ODNI, IARPA, or the U.S. Government.  The U.S. Government is authorized to reproduce and distribute reprints for Governmental purpose notwithstanding any copyright annotation thereon.
