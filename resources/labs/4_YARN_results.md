Fastest Round
```
########### Parameter ######################
# Data size = 51200000 byte
# Mapper containers = 5
# Reducer containers = 5
# Container memory = 1024
# MAP_MB = 819
# RED_MB = 819
#####################################

## teragen ##

real    0m58.177s
user    0m4.725s
sys     0m0.237s

## terasort ##

real    2m9.642s
user    0m5.891s
sys     0m0.268s
```
Slowest Round
```
########### Parameter ######################
# Data size = 51200000 byte
# Mapper containers = 16
# Reducer containers = 1
# Container memory = 2042
# MAP_MB = 1633
# RED_MB = 1633
#####################################

## teragen ##

real    1m12.267s
user    0m4.676s
sys     0m0.257s

## terasort ##

real    3m12.609s
user    0m5.707s
sys     0m0.319s
```
