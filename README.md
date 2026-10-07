# CUDA JOURNEY
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) ![Scope: Educational journey](https://img.shields.io/badge/Scope-Educational%20journey-blue.svg) ![IDE: Colab](https://img.shields.io/badge/IDE-Colab-purple.svg)

This repository is a simply journey to learn CUDA programming language based on Google Colab Workspace.

## Some info
### 📁 Repository
Each folder contains at least three files: `<README-file>.md`, `<jupiter-notebook-file>.ipynb` and `<cuda-file>.cu`.

### ⚙️ System used
- **IDE:** I use Google Colab workspace, and this is the answer about why I have different jupiter notebooks, but you are free to use the CUDA files also locally on your computer if you are rich enough to have a NVIDIA GPU in 2026
  - You are free to give me a free NVIDIA GPU for Christmas! xD
- **DEVICE:** because I am poor, each CUDA program was compiled on a GPU T4
- **NVIDIA System Management Interface:**
  ```text
  +-----------------------------------------------------------------------------------------+
  | NVIDIA-SMI 580.82.07              Driver Version: 580.82.07      CUDA Version: 13.0     |
  +-----------------------------------------+------------------------+----------------------+
  | GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
  | Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
  |                                         |                        |               MIG M. |
  |=========================================+========================+======================|
  |   0  Tesla T4                       Off |   00000000:00:04.0 Off |                    0 |
  | N/A   45C    P8             10W /   70W |       0MiB /  15360MiB |      0%      Default |
  |                                         |                        |                  N/A |
  +-----------------------------------------+------------------------+----------------------+
  
  +-----------------------------------------------------------------------------------------+
  | Processes:                                                                              |
  |  GPU   GI   CI              PID   Type   Process name                        GPU Memory |
  |        ID   ID                                                               Usage      |
  |=========================================================================================|
  |  No running processes found                                                             |
  +-----------------------------------------------------------------------------------------+
  ```

### 📝 How to use Google Colab Workspace (only for this journey)
If you are poor like me you can learn, without any problems, free on Colab.

1. Open [Colab](https://colab.research.google.com/) from your browser
2. Login with your Google account
3. Now you have two ways to start a jupiter notebook
     - you can start a new one by clicking the button `+ New notebook`
     - or you can upload one of mine jupiter notebooks by clicking the button `Upload notebook`
5. Change the hardware accelerator in `Runtime/Change runtime type/` with the `T4 GPU` (let the runtime type or change it in `Python 3`)
6. Run these commands on the jupiter notebook to check the hardware and download the `cuda toolkit`
   ```bash
   !nvidia-smi
   !apt-get update
   !apt-get install cuda-toolkit-11-2
   !nvcc --version
   ```

   The final output must be something like this:
   ```text
   Hit:1 https://cli.github.com/packages stable InRelease
   Get:2 https://cloud.r-project.org/bin/linux/ubuntu noble-cran40/ InRelease [3,631 B]
   Get:3 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
   Get:4 https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64  InRelease [1,578 B]
   Get:5 https://r2u.stat.illinois.edu/ubuntu noble InRelease [9,161 B]
   Hit:6 http://archive.ubuntu.com/ubuntu noble InRelease
   Get:7 https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu noble InRelease [17.8 kB]
   Get:8 http://archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
   Get:9 https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64  Packages [1,886 kB]
   Get:10 https://r2u.stat.illinois.edu/ubuntu noble/main amd64 Packages [3,047 kB]
   Hit:11 https://ppa.launchpadcontent.net/graphics-drivers/ppa/ubuntu noble InRelease
   Get:12 https://r2u.stat.illinois.edu/ubuntu noble/main all Packages [10.3 MB]
   Get:13 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Packages [1,545 kB]
   Get:14 http://archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
   Get:15 https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu noble/main amd64 Packages [52.1 kB]
   Get:16 http://security.ubuntu.com/ubuntu noble-security/main amd64 Packages [1,323 kB]
   Get:17 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [1,701 kB]
   Get:18 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [2,165 kB]
   Get:19 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Packages [2,138 kB]
   Fetched 24.6 MB in 3s (7,129 kB/s)
   Reading package lists... Done
   W: Skipping acquire of configured file 'main/source/Sources' as repository 'https://r2u.stat.illinois.edu/ubuntu noble InRelease' does not seem to provide it (sources.list entry misspelt?)
   Reading package lists... Done
   Building dependency tree... Done
   Reading state information... Done
   E: Unable to locate package cuda-toolkit-11-2
   nvcc: NVIDIA (R) Cuda compiler driver
   Copyright (c) 2005-2025 NVIDIA Corporation
   Built on Wed_Aug_20_01:58:59_PM_PDT_2025
   Cuda compilation tools, release 13.0, V13.0.88
   Build cuda_13.0.r13.0/compiler.36424714_0
   ```
7. Select the folder section on the left side
8. Right click on the void of the panel and choose if you want to upload one of mine CUDA files or you want to create a new one from zero

Now you are ready to work and become a master CUDA programmer 🎉

When you are already to run your program, you can run these commands on the jupiter notebook to create the CUDA executable file and to run it.
   ```bash
   !nvcc -arch=sm_75 -o <executable-filename> <cuda-filename>.cu
   !./<executable-filename>
   ```
> [!IMPORTANT]
> Colab workspace doesn't save your files! So, before reload or close the page, you must save your files locally on your computer.
