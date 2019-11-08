#Experiment and Parameter values

	In this project I duplicated the experiments performed by Chuanpeng Li, Chen Ding, and Kai She by measuring the cost of context switch using different array sizes. 

# There were two programs:

	 MeasureSingle where there was a single process simulating two processes communicating by sending a single-byte message to itself and MeasureSwitch where there were two processes repeatedly send a single-byte message to each other. The experiment measured the Effect of Array Size on Context Switch by evaluating the cost of context switch with respect to the different array sizes, and in my experiment I had a constant of 128-byte stride and the array size ranged from 64 KB to 16 MB.

#Results

In our experiment:
 	We observe that when the array size is between 64KB-512KB, there is little to no change because it could fit into the L2 cache, and no cache interference is present. As the size exceeds the range of L2 cache, there is a spike in context change because there is more overhead in repopulating the cache and cache interference, when the data size is larger. We then conclude that there is a direct relationship between array size and context switch so that as array size increases the cost of context switch increases.
