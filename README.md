# pytorch_radon
Pytorch implementation of scikit-image's radon function and more

修改涉及 torch.rfft() 部分，高版本使用 torch.fft.ftt() 代替此函数。
[参考链接](https://zhuanlan.zhihu.com/p/422962341)

示例：
```python
import torch
import pytorch_radon as pr

radon = pr.Radon(in_size=512, theta=torch.arange(0, 1080)).cuda()
iradon = pr.IRadon(out_size=512, theta=torch.arange(0, 1080)).cuda()

img = torch.randn((1,1,512,512))
sino = radon(u.cuda())
img_2 = iradon(sino)
```
