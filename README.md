![banner](https://user-images.githubusercontent.com/107757/119279427-9150eb80-bbe0-11eb-88d3-9e54e03b8020.jpg)

# cloutreactor (alpha)

cloutreactor is an *experimental* Bitclout miner and PPLNS pool.

- This is *alpha* software. You are an alpha tester. The miner may crash, shares may not be counted correctly. Please create an issue if you are having trouble and it will be addressed ASAP.
- Work is tracked on the pool server: balance computation is experimental and will be confirmed before first payouts are issued manually.
- Please watch the repo: new versions may come at any time.

### Pool
- Pool statistics, miner management, and payouts will soon be enabled on cloutreactor.com via Bitclout Identity.
- 10% of payouts will be invested into [@cloutreactor](https://bitclout.com/u/cloutreactor) on BitClout (50% FR)

### Miner
- NVIDIA CUDA is currently supported
  - OpenCL support coming soon

## Running via Docker (Recommended)

*We recommend running via Docker on both Windows and Linux. Binary distributions are offered for x86 Windows and Linux machines for convenience.

### Linux

1) Install Docker
    - For Ubuntu: https://docs.docker.com/engine/install/ubuntu/

2) Install the [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) for your platform

3) At a command prompt, run cloutreactor with all GPUs:

```Shell
# Run in-process:
docker run --rm --name cloutreactor --gpus all --runtime nvidia cloutreactor/cuda:v0.0.1 --public-key="BC1YLhL2beeonivCELUydf1Dt4LFPxuNbSrz5GRmzKxdCxDDutiuFp9"

# Or as a daemon:
docker run --rm -d --name cloutreactor --gpus all --runtime nvidia cloutreactor/cuda:v0.0.1 --public-key="BC1YLhL2beeonivCELUydf1Dt4LFPxuNbSrz5GRmzKxdCxDDutiuFp9"
docker logs -f cloutreactor
```

### Windows via WSL

1) Install NVIDIA WSL CUDA drivers, WSL (Ubuntu 18.04), and Docker
    - https://docs.nvidia.com/cuda/wsl-user-guide/index.html

2) At a command prompt, run cloutreactor with all GPUs:

```Shell
docker run --rm -t -i --gpus all --runtime nvidia cloutreactor/cuda:v0.0.1 --public-key="BC1YLhL2beeonivCELUydf1Dt4LFPxuNbSrz5GRmzKxdCxDDutiuFp9"
```

## Running compiled binaries

1) Install [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html) for your platform

2) Download the [latest release](https://github.com/cloutreactor/release/releases)

3) At a command prompt, run the server binary:

```Shell
# Linux
./cloutreactor --public-key="BC1YLhL2beeonivCELUydf1Dt4LFPxuNbSrz5GRmzKxdCxDDutiuFp9"

# Windows
./cloutreacto.exe --public-key="BC1YLhL2beeonivCELUydf1Dt4LFPxuNbSrz5GRmzKxdCxDDutiuFp9"
```

## Coming Soon

- cloutreactor.com
  - Bitclout Identity support
  - Payouts
  - Miner management
- OpenCL
- Prometheus metrics
