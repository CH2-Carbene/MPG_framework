# MPG_framework
A parallel executing and logging framework for HPC cluster.  
See `example.ipynb` for usage.

#### How to use MPG with more compute nodes running together (HPC task command has both n>1 and N>1)?
I used a 'flag' trick (create lock-file, or flag, on the shared disk, so that each compute node can process data without competing; then, I can applicate a lot of HPC tasks, using exactly the same command/code). However, I wrote the trick in my custom function, so the trick has not been added to MPG framework. It will be added later. Before that, you can try it by yourself.

#### It's based on lib multiprocessing, why don't use it directly?
1. The multiprocessing lib is not user-friendly enough.
2. Multiprocessing lacks some useful function that is very important in data processing: logging, time-calculation, exception processing (to be precise, it has, but is REALLY hard to use for a non-professional developer).

All in all, nothing is better than useful.