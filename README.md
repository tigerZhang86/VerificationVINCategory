# VerificationVINCategory
验证车辆识别代号


### 算法根源
>车辆识别代号的第9位是检验位，检验位可用0—9中任一数字或字母“X”表示。其它位置的数字和字母代表的意义个厂家含义可能不同，但在VIN码的其他16位字码确定后，按以下方法计算得出第九位的检验位。

![MacDown Screenshot](http://www.wendangku.net/pic/view?ih=99&rn=1&doc_id=0ed617ca5fbfc77da269b143&o=jpg_6_0_______&pn=1&iw=642&ix=0&sign=7784feb87df851cecacc1ec6ed512da3&type=1&iy=0&aimw=642&app_ver=2.9.8.2&ua=bd_800_800_IncredibleS_2.9.8.2_2.3.7&bid=1&app_ua=IncredibleS&uid=&cuid=&fr=3&Bdi_bear=WIFI&from=3_10000&bduss=&pid=1&screen=800_800&sys_ver=2.3.7)

>首先将其它16位中的字母按上图关系转换成数字： 

>A=1 B=2 C=3 D=4 E=5 F=6 G=7 H=8 J=1 K=2 L=3 M=4 N=5 P=7 R=9 S=2 T=3 U=4 V=5 W=6 X=7 Y=8 Z=9 

>每个位置都有个加权数： 

>位置：1 2 3 4 5 6 7 8  9 10 11 12 13 14 15 16 17
 
>权数：8 7 6 5 4 3 2 10 *  9  8  7  6  5  4  3  2 

>最后将检验位之外的16位每一位的加权系数乘以此位的对应值，再将各乘积相加，求得的和除以11，所得的余数就是检验位的数值。如果余数为10，则检验位为字母“X”。