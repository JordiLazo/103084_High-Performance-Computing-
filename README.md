# 103084 - Higher Performance Computing

## Summary
1. [Introduction](#introduction)
2. [Learning objectives](#learning-objectives)
3. [Moore](#moore)
4. [Assignment 1: Benchmarking](#assignment-1-benchmarking)
5. [Assignment 2: OMP Mandelbrot Fractal](#assignment-2-omp-mandelbrot-fractal)
6. [Assignment 3: MPI Mandelbrot Fractal](#assignment-3-moi-mandelbrot-fractal)
7. [Assignment 4: Hybrid OMP-MPI Mandelbrot Fractal](#assignment-4-hybrid-omp-mpi-mandelbrot-fractal)
8. [Assignment 5: Supercomputing Work or Comparison](#assignment-5-supercomputing-work-or-comparison)

## Introduction
To follow this course, the student should have solid knowledge of structured programming in C language and
Architecture and Computer Technology. Specifically, it is important that the student has good knowledge
of concepts of memory hierarchy and pipelining.

## Learning objectives
* Knowledge the use of benchmarking tools applied to the high performance computing environments.
* Capacity for analysis and understanding the computer perfomance.
* Knowledge of the parallel programming paradigms.
* Implementation and debugging of parallel applications using the OpenMP and MPI paradigms.
* Knowledge and understanding of the cloud computing paradigm.
* Practical use of frameworks and cloud computing technologies.
* Knowledge and understanding the architecture and operation for the most common HPC Infrastructures most
booming in the market.
* Solving numerical algorithms using a Hybridization of OpenMP and MPI technologies and evaluating its
performance.
* Communication of ideas and concepts in english in an understandable way, writing and speaking.

## Moore
In order to do the project, you need to install in your local computer a ssh client and a user account in the EPS teaching cluster (moore.udl.cat). 

Moore is an homogeneous Cluster with a total of 32 processing units and 32GB of main memory, distributed over 8 nodes with an Intel Core i5 processor with 4  cores at 3.1 GHz and 4GB of main memory.

http://moore.udl.cat/wordpress/

In the cluster, you will have all the software that you need to do the project. Likewise, in order to develop and test the code on your local computer, you will need to install any software that implements OpenMP (version 2) and MPI. In relation to MPI, you can use whatever you want, but we recommend the open software MPICH2, which is portable and very popular. You can download and find information about its installation and its use at the following address:

http://www.mcs.anl.gov/research/projects/mpich2


## Assignment 1: Benchmarking
The main aim of this practice is to learn to execute a parallel benchmark (application) written in the both most extended used parallel languages, MPI and OpenMP. Likewise, we will learn how to analyze the performance of a parallel machine by means of a benchmark. According to this, you must use the NAS parallel benchmark suite. (NPB3.3.1) (https://www.nas.nasa.gov/publications/npb.html). This suite is composed by 12 different benchmarks with different characteristics each one. Each benchmark is written in MPI, OpenMP and a serial version. You must install, execute and analyze only two of the benchmarks of the suite. You can choose anyone of them, apart from the both benchmarks (EP and IS) explained on class. All executions will be carried out in the cluster “moore.udl.cat ”, which is the educational cluster of the 
Polytechnic School.

## Assignment 2: OMP Mandelbrot Fractal
This project aims to solve a specific problem by means of OpenMP programming models. Specifically, the main aim is to understand the given real problem, to provide different parallel solutions and analyse the scalability of the provided solutions and the effects of the design decisions.

We want to implement a parallel version for a popular program, the Mandelbrot set. The Mandelbrot set is a geometric figure of infinite complexity (fractal nature) obtained from a mathematical formula and a small recursive algorithm, as shown in the following figure:
<img src="./images/MANDELBROT_OMP_seq_600.png" width="600" height="400" alt="mandelbrot OMP 600x400" title="mandelbrot OMP 600x400" style="display: block; margin: 0 auto"/>

In order to obtain the best performance of an application implemented with a parallel programming model, we should start by optimizing the application at node-level. According to this, the first activity will be focused on study the operation of the sequential version, analysing the pieces of code candidate to be parallelized following a work and data decomposition model. Next, we will apply the OpenMP directives to parallelize the corresponding code according to the hardware and the suitable work decomposition model at node level.

The commands to execute the parallelized program in the moore cluster of the University of Lleida are the following:

To compile the code:
```
gcc mandelbrot_omp.c -o mandelbrot_omp -lm -fopenmp
```
To run the programm in the cluster:
```
qsub run-simple-omp.sh
```

## Assignment 3: MPI Mandelbrot Fractal

In this activity, you should propose a new implementation using the MPI library. MPI implementation is providing us the possibility to apply a data decomposition mode.

The commands to execute the parallelized program in the moore cluster of the University of Lleida are the following:

To compile the code:
```
mpicc mandelbrot_mpi.c -o mandelbrot_mpi -lm -fopenmp
```
To run the programm in the cluster:
```
qsub run-extended-mpi
```
## Assignment 4: Hybrid OMP-MPI Mandelbrot Fractal
In this activity, you should propose a new implementation combining both programming models, MPI and OpenMP. You should compare the performance of this hybrid solution in relation to the previous delivery for different problem
and processes sizes. MPI implementation is providing us the possibility to apply a data decomposition model.

The commands to execute the parallelized program in the moore cluster of the University of Lleida are the following:

To compile the code:
```
mpicc mandelbrot_hybrid.c -o mandelbrot_hybrid -lm -fopenmp
```
To run the programm in the cluster:
```
qsub run-extended-mpi
```
## Assignment 5: Supercomputing Work or Comparison


