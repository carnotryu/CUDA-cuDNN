
### Environment
* Ubuntu 18.04.3
* 2019/8/28

### cuda 10.1
```bash
https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal
```
* target_type=deblocal
```basg
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-ubuntu1804.pin
sudo mv cuda-ubuntu1804.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-1-local-10.1.243-418.87.00/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```
### cudnn 7.6.3.30
```bash
sudo dpkg -i <library_name>.deb
```

```bash
sudo dpkg -i libcudnn7_7.6.3.30-1+cuda10.1_amd64.deb
sudo dpkg -i libcudnn7-dev_7.6.3.30-1+cuda10.1_amd64.deb
```
* dev는 runtime에 의존. 따라서 위의 순서대로 설치
* See https://askubuntu.com/a/916667


### ~/.bashrc 
*이전 PC에서 가져옴.
```bash
export CUDA_HOME=/usr/local/cuda
export CUDA_ROOT=/usr/local/cuda
export PATH=$PATH:$CUDA_ROOT/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CUDA_ROOT/lib64:$CUDA_ROOT/extras/CUPTI/lib64
```
