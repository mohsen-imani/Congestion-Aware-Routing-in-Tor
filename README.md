# Congestion-Aware Routing in Tor
This is an implemention of Congestion-Aware Routing (CAR) in Tor. Wang et al [1]. proposed opportunistic and active probing techniques to measure RTTs, which allows them to compute congestion times, and they use these measurements to mitigate congestion using both an instant response for temporary congestion and a long-term response for low-bandwidth conditions. In our simulation, we follow the method of Wacek et al. [2], who also simulated CAR and ignored the long-term response due to its small impact on performance. According to the paper, the CAR discards the circuits that are congested and reattaches the streams to other circuits. We did not implement this because it causes new connections to the servers and everything will start from scratch and will harm the users' experience.

# Implementations
- **CAR-tor-0.2.5.2-alpha** is the implementation on the Tor 0.2.5.2-alpha
- **CAR-tor-0.2.4.20** is the implementation on the Tor 0.2.4.20 

# Setting
The CAR drops the congestions and stops using them. The threshold to detect the congested circuits can be control through this option in *torrc* file.
- CUTOFF: this option controls the threshold for pruning the circuits. The default value is 600 mseconds which means circuits their median congestion time is more than 600 mseconds will be used.
