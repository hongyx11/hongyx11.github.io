---
title: "HPC Starter 01: Linux and the cluster workflow"
date: 2026-08-20
permalink: /hpc-starter/linux-cluster-workflow/
tags: [HPC Starter, Linux, Slurm]
excerpt: "Learn SSH, files, processes, environment modules, and responsible use of a scheduled cluster."
---

Most supercomputers run Linux. You usually connect to a **login node**, prepare software and jobs there, and ask a scheduler to run compute-intensive work on **compute nodes**.

## Connect and inspect

```bash
ssh username@cluster.example.edu
hostname
pwd
uname -a
lscpu
```

`hostname` reminds you where a command is running. `lscpu` describes the visible processors. On a shared cluster, never assume the login node represents the compute nodes.

Useful daily commands include:

```bash
ls -lah
mkdir -p results
cp source.cpp source.backup.cpp
mv old-name.txt new-name.txt
find . -maxdepth 2 -type f
du -sh .
```

Use `less`, `head`, and `tail` to inspect large text files without loading everything into an editor. Use `ps`, `top`, or `htop` to inspect processes, but follow the cluster documentation before running workloads interactively.

## Software environments

Clusters commonly provide environment modules:

```bash
module avail
module list
module load gcc
g++ --version
```

Record the loaded modules with every benchmark. Loading a different compiler or MPI implementation can change both correctness and performance.

## Submit a Slurm job

Many clusters use Slurm. A minimal CPU job script looks like this:

```bash
#!/usr/bin/env bash
#SBATCH --job-name=hpc-starter
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=4
#SBATCH --time=00:05:00
#SBATCH --output=results/%x-%j.out

set -euo pipefail
hostname
srun ./build/benchmark
```

Submit and inspect it:

```bash
sbatch scripts/run.slurm
squeue --me
sacct -j JOB_ID
```

The exact partitions, accounts, and GPU flags differ across systems. Treat local documentation as authoritative.

## Data discipline

Home directories are usually backed up but small. Scratch filesystems are large and fast but may be purged. Keep source code and small results in Git; keep large generated data in the appropriate project or scratch space. Do not commit credentials, private keys, or proprietary data.

## Exercise

Create a job that records `hostname`, `lscpu`, loaded modules, and the values of relevant Slurm variables. Compare the output from the login node and compute node. In three sentences, explain why performance work belongs on allocated compute nodes.

**Next:** [C++ and build tools](/hpc-starter/cpp-build-tools/)

