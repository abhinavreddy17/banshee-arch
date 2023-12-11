# casim
Computer Architecture Simulation Infrastructure for CSCE 614 Computer Architecture



##### 1. Apply a path file for cse server

```
$ git apply cse_server.patch
```

##### 2. Unzip benchmarks files

```
zip -F benchmarks.zip --out single-benchmark.zip && unzip single-benchmark.zip && mkdir benchmarks/parsec-2.1/inputs/streamcluster
```

### 3. Environemnt setup

Everytime you want to build or run zsim, you need to setup the environment variables first.

```
$ source setup_env
```

##### 4. Compile zsim

```
$ cd zsim
$ scons -j4
```

##### 5. Launch a test to run on the benchmark shown

```
./build/opt/zsim tests/mcf.cfg
```

Use the config files in the above zip folder for each benchmark and cache design.

In each config files we provide, different cache design access. You can use it to simulate on Alloy Cache, TDC, etc. as mentioned in the paper.


This project is based on paper below.

Banshee architecture: Banshee's DRAM cache is set-associative. In this architecture we assume both the in-package and off-package DRAM has the same memory controller and few changes were made to the state-of-art DRAM cache design.

Integrating DRAM within the same package as a processor results in a substantial increase in memory bandwidth, exceeding that of traditional off-package DRAM by several times.
We propose to follow the paper with a novel DRAM cache design named "Banshee" that aims to enhance both in-package and off-package DRAM bandwidth efficiency while maintaining low access latency. With this project we aim to understand new architecture for Large memory bandwidth models.



###### For more information, check `zsim/README.md`
