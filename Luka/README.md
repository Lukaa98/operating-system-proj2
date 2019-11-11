In this project, I measure the cost of the context switch with the set of experiments. I replicate the experimental result illustrated in Figure 1 and Figure 2 from the paper of “Chuanpeng Li, Chen Ding, and Kai Shen. 2007. Quantifying the cost of the context switch.
In the experiment, we had two programs 

MeasureSingle(s1):
we use a single process simulating two processes communicating by sending a single-byte message to itself via a pipe. There are 10,000 simulated round-trip communications.
MeasureSwitch (s2):
two processes repeatedly send a single-byte message to each other via pipes. 10,000 round-trip communications.
After each process becomes runnable, it will access an array of floating-point numbers.

In the first experiment, I was interested to measure the cost of context switch with respect to the different array sizes. So, I made stride size the same for all calculations, therefore you can see that the size of my stride is 8 while the size of the array is changing from 64KB to 32MB. I repeat the experiment a few times and then take average so I could have more precise results.  After I had an average of S1 and S2 I did the calculation of cost by calculating S2-S1 and then I made a graph of results. Also, I made a graph of the average of S1 and S2 so we see all the data on the graph.

In the second experiment, I calculate the cost of context switch with different array sizes and different stride sizes. the size of the array from 32KB to 2MB and the stride size from 6 bytes to 128 bytes. To replicate the experiment as it was described in the document we tried to choose the numbers that were almost the same as in the experiment.


Summary

In my first experiment, I observe that in the cost of context switch there was no huge change when array size was between 64KB and 512KB  because the dataset can be placed in the L2 cache. But from 512KB to 8MB there was change almost as max as 1000 in cost. However, when the array size was 32MB result was less than when the array was 8MB. 
In the second experiment we can see that as stride size was getting larger the greater the context switch was. as well as array size was getting larger this was increasing context switch. 
