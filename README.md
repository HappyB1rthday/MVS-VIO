<h1 align="center">MVS-VIO: Dense Monocular Visual Inertial Odometry with Lightweight MVSNET</h1>
We propose MVS-VIO, a dense monocular VIO system that can perform global-scale-consistent 
pose estimation and reconstruct global TSDF map in real-time. Our MVS-VIO achieves 
state-of-art performance in all real-world sequences of EuRoC.


An available video demo of our MVS-VIO is: https://www.youtube.com/watch?v=yRKlclXRUXk or https://www.bilibili.com/video/BV1eg4y1u7dL

We wrote the core MVS-VIO code in C++ and trained LW-MVSNET using Pytorch, which relies on a more complex environment configuration to run. 
We are in the process of configuring the relevant docker environment and fixing related bugs in the code.

The code will be open sourced after the paper is accepted. However, we can open the core experimental data to prove the excellent 
performance of our system in the paper.
### Experimental Results
We provide the main experimental data from 4.2 of the paper and the ablation experimental data from Appendix B. 
This experimental data contains the pose estimation results of MVS-VIO on all 11 sequences of EuRoC, and the 
visualized evaluation python script. Each sequence was run 10 times, for a total of 110 times. The range of the 
uncertainty mask is [0.05, 0.6]. Run the following command to view our experimental data:

    cd experimental_results
    find . -type f -name "*.tar.xz" -exec tar -xvf {} \;
    cd ..
    python3 ./evaluation_tools/evaluation.py

If you don't have some bags such as `tqdm`, you can use command `pip3 install -` to obtain them.
