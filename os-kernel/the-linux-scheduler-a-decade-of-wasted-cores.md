## High level

Issues: os system has free core resources, but scheduler takes time(e.g ~s) to schedule the runnable threads.

Thought:
* Linux CFS scheduler works very similar to the one in Solaris(steal threads from other runqueues; but need to be aware cache affinity etc.)
* Runqueue balancing algorithm works very similar to the one in Solaris which will take considering on process group(for different NUMA node)
* Fixing the performance bugs will be trivial, but understand the issue rocks!

1. Starts with linux scheduler 101
  1. CFS(complete fair scheduling):
    * weighted based scheduler
    * divide available timeslice amount all the runnable threads based on their weights(priority)
    * multi-core system has one runqueue per core(like Solaris)
    * Runqueue balancing based on thread's weight and its average cpu util.(cgroup to bring fairness between groups of threads.)

References:
- http://www.ece.ubc.ca/~sasha/papers/eurosys16-final29.pdf
- https://blog.acolyer.org/2016/04/26/the-linux-scheduler-a-decade-of-wasted-cores/
- https://github.com/jplozi/wastedcores //tools and patches from the paper
