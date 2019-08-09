# How-to-set-up-tensorflow-gpu
for RTX 2080ti on ubuntu 16.0.4

Target: 
  - cuda10.1.168
  - cudnn7.6.0
  - python 3.7.3
  - tensorflow-gpu == 1.14.0
  - driver version 418
  





# 1、先更新一下系统：建议将源换成aliyun的源
  sudo apt-get update
  sudo apt-get dist-upgrade
 

# 2、安装RTX2080显卡驱动

2.1添加开源显驱仓库 
    sudo add-apt-repository ppa:graphics-drivers/ppa
    sudo apt-get update
2.2安装一些依赖
    sudo apt-get install dkms synaptic build-essential
    
2.3 打开系统的 Software & Update 工具，选择 Additional Drivers选择 418 版本，选择更新即可，这个过程耗时10-40分钟，取决于下载时的网速，更新完后系统会提示重启电脑，点击重启即可。

2.4 测试显卡是否安装成功可打开终端（terminal）依次输入下面两个命令测试
    nvidia-smi
    nvidia-settings
    
# 3 安装Cuda和cudnn

除非你打算安装CUDA 10.0并自行编译 TensorFlow 或 PyTorch ，否则不要自行安装 CUDA 和 cuDNN！因为版本兼容问题是个大坑，而网上很多教程却避而不谈。其实最简单稳妥的办法就是通过 Anaconda 安装 TensorFlow ，让它来安装正确的依赖 —— 例如 CUDA 和 cuDNN。

3.1 安装anaconda

Anaconda 是数据科学家的必备神器，而我们使用它安装 TensorFlow 的原因是：

    自动安装正确版本的依赖；

    环境管理 —— PyTorch 和 TensorFlow 依赖的CUDA版本不一致也没关系；

    这个安装方法太简单了！

首先下载 Anaconda。目前官方默认提供 Python 3.7 版的安装包
    bash ./#Anaconda.sh#
 
# 4  使用anaconda安装tenforflow_gpu版本(强烈推荐)，终端输入下面命令即可
    
 
