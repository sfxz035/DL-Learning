


- 遇到问题  
  超分辨网络输出的结果图片有光斑。  
  - 原因  
    因为网络的输出图像数组中值的范围并不全是(0，255)内，一些值超出了这个范围，大于255或小于0。
  - 解决方法  
    需要对输出的图像数组进行np.clip(img,0,255) ，将所有值转换到(0，255)范围内。
   - 图示  
     光斑  
     ![enter image description here](https://github.com/sfxz035/DL-Learning/raw/master/picture/gb.png)   
     clip后无光斑图  
     ![enter image description here](https://github.com/sfxz035/DL-Learning/raw/master/picture/wgb.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTY5ODA4NTcxLDUwOTg1MjA3NiwtNzc3OT
cxNDI3LC02MzI5MjgyNDBdfQ==
-->