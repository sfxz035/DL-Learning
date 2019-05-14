## Detection markers

### 问题
1. opencv uint8格式问题  
   255的image读取进来除以255进行归一化，格式变成了float，乘以255后无法直接运用opencv。  
   需要现对除以255后的对象，乘以255后，在astype成uint8格式才可以。而且不能
2. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMjk1MDU5NTNdfQ==
-->