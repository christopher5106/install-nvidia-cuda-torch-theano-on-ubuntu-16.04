```bash
sudo apt-get update
sudo apt-get install -y nvidia-361

wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.44-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604_8.0.44-1_amd64.deb
sudo apt-get update

sudo apt-get install -y cuda

# download CUDNN on your laptop and upload to your server
# scp cudnn-8.0-linux-x64-v5.1.tgz root@s4:
tar xvzf cudnn-8.0-linux-x64-v5.1.tgz
sudo cp -r /usr/local/cuda-8.0 /usr/local/cuda-8.0-cudnn-5.1
sudo cp cuda/include/cudnn.h /usr/local/cuda-8.0-cudnn-5.1/include/
sudo cp cuda/lib64/* /usr/local/cuda-8.0-cudnn-5.1/lib64/
rm -r cuda
rm cudnn-8.0-linux-x64-v5.1.tgz
rm cuda-repo-ubuntu1604_8.0.44-1_amd64.deb

sudo apt-get install -y git
git clone https://github.com/torch/distro.git ~/torch --recursive
cd ~/torch; bash install-deps;
./install.sh
```
