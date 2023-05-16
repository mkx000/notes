## 离线安装 GPU 版本 Pytorch

### 1、安装 miniconda

### 2、确定 Nvidia GPU 驱动版本
使用 nvidai-smi.exe 命令：
``` powershell
nvidia-smi.exe # 或者 nvidia-smi -a 
```

可以看到下图：
<img src="E:\courses\notes\miscellaneous\pictures\GPU.PNG" alt="GPU" style="zoom: 80%;" />

## 3、下载相关的包
在这个网站上下载相关的包，https://download.pytorch.org/whl/torch_stable.html
包 : torch，torchaudio，torchvision

``` python
pip install "xxx.whl" -i https://pypi.tuna.tsinghua.edu.cn/simple/
```

## 4、验证成功安装

``` python
import torch
torch.cuda.is_available()
# True代表成功安装GPU版本的pytorch
```



