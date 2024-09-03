# CUDA-by-Example-source-code-for-the-book-s-examples-
CUDA by Example, written by two senior members of the CUDA software platform team, shows programmers how to employ this new technology.  The authors introduce each area of CUDA development through working examples. 

# Updates by Miklos Szegedi

The book has been written more than a decade ago. I also tested with an older NVidia GPU.

These are the prerequisites that I tested and that were working.

```
NVIDIA GeForce GTX 1050 Ti
Linux Mint 5.15.0-91-generic #101-Ubuntu SMP Tue Nov 14 13:30:08 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

First test your configuration
```
# docker run -t -i --gpus all nvidia/cuda:12.1.0-devel-ubuntu22.04 nvidia-smi

==========
== CUDA ==
==========

CUDA Version 12.1.0

Container image Copyright (c) 2016-2023, NVIDIA CORPORATION & AFFILIATES. All rights reserved.

This container image and its contents are governed by the NVIDIA Deep Learning Container License.
By pulling and using the container, you accept the terms and conditions of this license:
https://developer.nvidia.com/ngc/nvidia-deep-learning-container-license

A copy of this license is made available in this container at /NGC-DL-CONTAINER-LICENSE for your convenience.

*************************
** DEPRECATION NOTICE! **
*************************
THIS IMAGE IS DEPRECATED and is scheduled for DELETION.
    https://gitlab.com/nvidia/container-images/cuda/blob/master/doc/support-policy.md

Tue Sep  3 03:46:47 2024       
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 535.161.07             Driver Version: 535.161.07   CUDA Version: 12.2     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA GeForce GTX 1050 Ti     Off | 00000000:01:00.0 Off |                  N/A |
| 50%   40C    P0              N/A /  75W |    483MiB /  4096MiB |      1%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+
                                                                                         
+---------------------------------------------------------------------------------------+
| Processes:                                                                            |
|  GPU   GI   CI        PID   Type   Process name                            GPU Memory |
|        ID   ID                                                             Usage      |
|=======================================================================================|
+---------------------------------------------------------------------------------------+
```

Install a supported version of CUDA. You can get a list of supported compute capability by each device.
[https://developer.nvidia.com/cuda-GPUs](https://developer.nvidia.com/cuda-GPUs)

You can just ask copilot to show the supported CUDA version.
[Bing](https://www.bing.com/search?q=What%20cuda%20version%20is%20required%20for%20compute%20capability%206.1?&showconv=1&sendquery=1)

Our configuration supports nvidia/cuda:12.1.0-devel-ubuntu22.04. We do not support any OpenGL calls within a docker container, yet.
Other pure CUDA examples will work.

```
docker run -t -i --gpus all nvidia/cuda:12.1.0-devel-ubuntu22.04 bash
# apt update; apt install -y git
# git clone https://github.com/szegedim/CUDA-by-Example-source-code-for-the-book-s-examples-.git
# cd CUDA-by-Example-source-code-for-the-book-s-examples-/chapter05/
# nvcc --run add_loop_blocks.cu 
0 + 0 = 0
1 + 1 = 2
2 + 4 = 6
3 + 9 = 12
4 + 16 = 20
5 + 25 = 30
6 + 36 = 42
7 + 49 = 56
8 + 64 = 72
9 + 81 = 90
```

# Table of Contents

- Why CUDA? Why Now?
- Getting Started
- Introduction to CUDA C
- Parallel Programming in CUDA C
- Thread Cooperation
- Constant Memory and Events
- Texture Memory
- Graphics Interoperability
- Atomics
- Streams
- CUDA C on Multiple GPUs
- The Final Countdown


# Authors

Jason Sanders is a senior software engineer in NVIDIA’s CUDA Platform Group, helped develop early releases of CUDA system software and contributed to the OpenCL 1.0 Specification, an industry standard for heterogeneous computing. He has held positions at ATI Technologies, Apple, and Novell.

Edward Kandrot is a senior software engineer on NVIDIA’s CUDA Algorithms team, has more than twenty years of industry experience optimizing code performance for firms including Adobe, Microsoft, Google, and Autodesk.




![CUDA-by-Example](https://github.com/CodedK/CUDA-by-Example-source-code-for-the-book-s-examples-/blob/master/Pearson_CUDA_BookCover.jpg)


https://developer.nvidia.com/cuda-example
