random_walk.py
Random walk code, select the meta path in the heterogeneous network to get a random walk instance
Input: Associated Network
Output: Random Walk Instance

metapath2vec++ :
Training options:
	-train <file>£ºUse the data in <file> to train the model
	-output <file>£ºSave the generated diseases vector using <file>
	-size <int>£ºSet the size of diseases vector; default is 100
	-window <int>£ºSet the maximum skip length between diseases; default is 5
	-sample <float>£ºSet threshold for occurrence of diseases. Those that appear with higher frequency in the training data will be randomly down-sampled; default is 1e-3, useful range is (0, 1e-5)
	-pp <int>:Use metapath2vec ++ or metapath2vec; the default value is 1 (metapath2vec ++); for metapath2vec, use 0
	-negative <int>:Number of negative examples; default is 5, the usual value is 3 - 10 (0 = not used)
	-threads <int>:Use <int> thread (default is 12)
	-iter <int>:Run more training iterations (default is 5)
	-min-count <int>:This will discard diseases that are less than <int> times; the default is 5
	-alpha <float>:Set the initial learning rate; the default value of skip-gram is 0.025

Examples:
./metapath2vec -train input.txt -output ../output -pp 1 -size 128 -window 7 -negative 5 -threads 32

Input: Instance data obtained by random walk
Output: Multidimensional vector data for each disease

cosine.py:
Calculate the similarity between diseases based on multidimensional vectors
Input: Multidimensional vector data
Output: A table of similarity data between diseases

