Q1. Why do you see a difference in webpage fetch times with small and large router buffers?

- We can see that when the buffer is smaller, our average fetch time is smaller as well. This is because, when a buffer is smaller, it will get filled faster and start dropping packets. This is faster than keeping it in the buffer since protocol would just attempt to resend the packet at another time. Waiting in the buffer until the link can take it, takes more time.

Q2. Bufferbloat can occur in other places such as your network interface card (NIC). Check the output of ifconfig eth0 on your VirtualBox VM. What is the (maximum) transmit queue length on the network interface reported by ifconfig? For this queue size and a draining rate of 100 Mbps, what is the maximum time a packet might wait in the queue before it leaves the NIC?

- The ipconfig eth0 report lists MTU at 1500b. At a draining rate of 100Mbps, the maximum time for a packet to wait in the queue is 1500b/100000000bps = 0.015ms.

Q3. How does the RTT reported by ping vary with the queue size? Write a symbolic equation to describe the relation between the two (ignore computation overheads in ping that might affect the final result).

- We can see that as the queue size increases, so does the average RTT from the ping output. Equation??????

Q4. Identify and describe two ways to mitigate the bufferbloat problem.

-  One way we can mitigate bufferbloat, is by optimizing the buffer size. We would want a size that maximizes throughput and minimizes queue wait times. We can do this by using the input an output speeds to calculate this optimal buffer size such that each packet waits waits in the queue for exactly the same time as the processing time per packet.

- We can implement a queuing algorithm that selects packets within the buffer to send such that throughput is optimized. 
