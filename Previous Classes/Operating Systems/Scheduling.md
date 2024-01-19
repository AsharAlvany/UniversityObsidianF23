**Evaluation Metrics for scheduling**$$T_{turnaround} = T_{completion}-T_{arrival}$$$$T_{response} = T_{arrival}$$
**Workload Assumptions**
- All jobs arrive at the same time
- All jobs only use the CPU
- The run-time of each job is known
- FIFO
**Convoy Effect**
- You have a long job that has in front of a shorter task that decreases the aggregate average turnaround time
- Solution: Pause the long task when a short job arrives, switch to the short job, complete the short job, switch back to the longer job
**Round Robin**
- JOS uses this
- Run a job for a fixed-length time slice also known as a time quantum
- Similar to timer interrupt
- Switch to the next job in the queue
- After reaching the tail of the queue, start over
- This is better for response time but worse for turnaround time