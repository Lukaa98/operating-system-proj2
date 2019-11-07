#**Experiment and Parameter values **

	In this experiment, we duplicated the experiments performed by Chuanpeng Li, Chen Ding, and Kai She.
We measure the indirect cost of context switch using a controlled workload.
In particular, we measure the impact of array data sizes, and stride size of a context switch cost.

##** We use two programs: **
	 MeasureSingle(s1), we use a single process simulating two processes communicating
by sending a single-byte message to itself via pipe. There are 10,000 simulated round-trip communications.
	MeasureSwitch (s2), two processes repeatedly send a single-byte message to each other via pipes.
10,000 round-trip communications.

After each process becomes runnable, it will access an array of floating-point numbers.

**In the first experiment:** * "Effect of Array Size on Context Switch" * 
	We are interested in appraising the cost of context switch with respect to the different array size.
Therefore, I made stride size constant, and in my experiment, I decided to go with 16-byte stride.
In hindsight it would've been better to choose a smaller stride size, because we don't want the stride size interfering with our goal of our experiment-- which is to see array size
and its relationship to cost of context switch.
The array size ranged from 64 KB to 8 MB.
	 I selected a greater array size to test than in the report because I wanted to grasp a good understanding of the cost of
context switch with large array size.

**In the Second experiment:** * "Measuring Indirect Context Switch" *
	In this experiment, we want to calculate the cost of context switch with respect to different array size
and different stride size.
The stride size ranges from 8 bytes to 128 bytes.
The array size ranges from 32 KB to 2 MB.
In order to really quantify the cost of context switch of these two parameters, I decided
to choose values that closely matches to that from the report,* Quantifying the Cost of Context Switch.* 


#** Results **

In our first experiment:
 	We deduce from our graph that when using a constant, and small, stride size,
we can see that when the array size is between 64KB-512Kb, the curve is relatively flat. This is because the dataset
can fit into the L2 cache, and no cache interference is present. From 512KB-8MB, there is a noticeable increase in 
context switch. There is more overhead in repopulating the cache, when the data size is larger. Additionally, cache 
interference is present. 

In our second experiment:	
	We deduce from our graph that when the data size is larger than cache size, the greater the stride size, the greater the cost of context switch.
We know that large array size causes more cost of context switch from the previous experiment. 
Stride Size affects the cost of cache warm-up in a similar way it affects program running time.
