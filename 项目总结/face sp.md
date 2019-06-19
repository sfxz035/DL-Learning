


- 遇到问题  
  超分辨网络输出的结果图片有光斑。  
  - 原因  
    因为输出的图像数组中值的范围并不全是(0，255)内，一些值超出了这个范围，大于255或小于0。需要对输出的图像数组进行np.clip(img,0,255) 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2MzkyNTY4MSwtNjMyOTI4MjQwXX0=
-->