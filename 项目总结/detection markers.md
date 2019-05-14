## Detection markers

### 问题
1. opencv uint8格式问题  
   255的image和label读取进来除以255进行归一化，再放入网络训练。  
   输入的image除以255归一化后格式变成了float，乘以255后无法直接运用opencv。  
   需要现对除以255后的对象，乘以255后，再astype成uint8格式才可以。而且不能先astype成uint8格式再乘以255
2. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbODg1OTgyMjA2XX0=
-->