``` 
Slowest

** PARAM ************************************************************************
# Data size = 51200000 byte
# Mapper containers = 1
# Reducer containers = 1
# Container memory = 2048
# MAP_MB = 1638
# RED_MB = 1638
#************************************************************************************************

***  TERAGEN ***

real    1m26.305s
user    0m5.387s
sys     0m0.258s

***  TERASORT ***

real    2m12.019s
user    0m7.627s
sys     0m0.292s
Deleted tg-10GB-1-1-2048
Deleted ts-10GB-1-1-2048



Fastest 


** PARAM ************************************************************************
# Data size = 51200000 byte
# Mapper containers = 16
# Reducer containers = 16
# Container memory = 2048
# MAP_MB = 1638
# RED_MB = 1638
#************************************************************************************************

***  TERAGEN ***

real    1m0.301s
user    0m5.274s
sys     0m0.279s

***  TERASORT ***

real    1m10.294s
user    0m7.329s
sys     0m0.318s
Deleted tg-10GB-16-16-2048
Deleted ts-10GB-16-16-2048
Testing loop ended on Tue Oct 3 17:15:17 EDT 2017
``` 

