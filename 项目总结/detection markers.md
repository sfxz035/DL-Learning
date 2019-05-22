## Detection markers

### 数据
- 原图  
  原图数据为16位的short型数据。
  - int 255  
    将原图每一张分别进行标准化，截取-0.75，0.75范围的数据（data2）,再进行最大最小值归一化到0，255范围，并`cv.cvtColor(img,cv.COLOR_GRAY2BGR)`成三通道
  - -0.75，0.75  
    将原图进行标准化，截取-0.75，0.75范围的数据--（data3）
  - 0，1
    将原图直接除以（256*256）,映射到（0，1）范围--（data4）
   
-   png图片
  输入直接是原图经过窗位窗宽调整过后的png图片。

### 注意  
金标检测的图像分为png和原图，png是原图经过窗位窗宽调整后得到的图片，为uint8格式，而原图为16为float图。
一般都是对原图进行一定范围的截取，然后将该范围的值映射到一定范围，用该范围的值对应全部灰阶成为的图像。

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
2. 原图问题  
   - 差别小，导致肉眼无法识别的金标。
   - 金标小，小物体分割。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwOTIwNjk4OTAsMTE2OTM2MzAyNCwtMT
gxMTg3MzU5LDY2NDk4OTE5OSwxODM1NDAwNTkzLC0xMDQ5ODI4
NjExXX0=
-->