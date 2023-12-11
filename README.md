# casim
Computer Architecture Simulation Infrastructure for CSCE 614 Computer Architecture

ZSim was being used as a simulator for this project

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

We've introduced both off-package and in-package DRAM cache functionalities through the "ddr_mem.c++" and "ddr_mem.h" files. Each cache now has its memory controller, implemented in the "DRAM_controller.c++" file. Line replacement policies have been implemented in the "zsim/src" directory. Additionally, we've integrated a prefetcher that anticipates data based on the program's past behavior. To gather extended statistics, a "stats_cpp" code has been included. Furthermore, we've calculated the data transfer rate (Bytes per instruction transferred) from DRAM to memory. All updated files can be found in the "zsim/src" directory, and certain external libraries specified by the author have been utilized.







### Link for the paper

@misc{yu2017banshee,
      title={Banshee: Bandwidth-Efficient DRAM Caching Via Software/Hardware Cooperation}, 
      author={Xiangyao Yu and Christopher J. Hughes and Nadathur Satish and Onur Mutlu and Srinivas Devadas},
      year={2017},
      eprint={1704.02677},
      archivePrefix={arXiv},
      primaryClass={cs.AR}
}


https://arxiv.org/abs/1704.02677

###### For more information, check `zsim/README.md`
