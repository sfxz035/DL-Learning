## Detection markers
### 注意  
金标检测的图像分为png和原图，png是原图经过窗位窗宽调整后得到的图片，为uint8格式，而原图为16为float图

### 问题
1. opencv uint8格式问题  
   255的image和label读取进来除以255进行归一化，再放入网络训练。  
   输入的image除以255归一化后格式变成了float。
   - image
	   - 错误  
	     1. 直接乘以255后无法直接运用opencv。  
	     2. 先astype成uint8格式再乘以255
	   - 正确  
	     需要先对除以255后的对象，乘以255后，再astype成uint8格式才可以。
    - 输出  
        - 错误  
          1. 直接乘以255后无法直接运用opencv。  
          2. 先乘以255再astype成uint8格式
        - 正确  
          先astype成uint8格式再乘以255  
    - 以上这两者原因还待深究
2. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4NjU2MzE2NiwxODM1NDAwNTkzLC0xMD
Q5ODI4NjExXX0=
-->