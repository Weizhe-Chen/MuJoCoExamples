# Installation
1. Download the MuJoCo version 2.1 binaries for [Linux](https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz) or [OSX](https://mujoco.org/download/mujoco210-macos-x86_64.tar.gz).
2. Extract the downloaded `mujoco210` directory into `~/.mujoco/mujoco210`.
3. Append the following lines to `~/.bashrc` and `source ~/.bashrc`
```bash
# MuJoCo
export LD_LIBRARY_PATH=$HOME/.mujoco/mujoco210/bin
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so
```

### Create a Python virtual environment
```bash
# mamba is the same as conda but much faster
mamba create -n mujoco python=3.8
mamba activate mujoco
```

### Install `mujoco_py`
```bash
pip install -U 'mujoco-py<2.2,>=2.1'
```

### Troubleshooting
If you encounter the following error thrown by `mujoco_py`
```python
FileNotFoundError: [Errno 2] No such file or directory: 'patchelf'
```
Please install the package `patchelf` via
```bash
sudo apt install patchelf
```
