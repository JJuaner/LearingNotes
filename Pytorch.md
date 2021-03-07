Pytorch核心是tensor<br>
重点理解tensor本身及其操作，理解区别数据与数据描述<br>
真实的一堆数据（个数，存储数据本身意义）<br>
数据的组织（维度，形状）

>tensor维度理解
>>a.shape=tensor.Size([4,3,28,28])
>>>真实数据[[[],[],[]],[[],[],[]],[[],[],[]],[[],[],[]]]+维度[dim0,dim1,dim2,dim3]<br>
>>>认知：4张照片,3通道,28行,28列<br>
>>>a[0].shape=tensor.Size([3,28,28])<br>
>>>a[0,0].shape=tensor.Size([28,28])

>dimension与shape
>>[[x,x,x]] [1,3]二维，形状1,3<br>
>>数据与描述数据如何组织
>>>[4,3,28,28] [4张照片,3通道,28行,28列]<br>
>>>[4,50,8] [class,student,score]<br>


>索引
>>`...`是`:,:`的匹配缩写，具体有多少个，由系统自适应<br>
>>数据索引：[0,1,2,3,4][-5,-4,-3,-2,-1]都是对应的位置


broadcast=unsqueeze+expand

tensor零填充
>>1.0tensor cat  
>>2.pytorch中最常用的零填充函数是nn.ZeroPad2d，也就是对Tensor使用0进行边界填充，我们可以指定tensor的四个方向上的填充数，比如左边添加1dim、右边添加2dim、上边添加3dim、下边添加4dim，即指定paddin参数为（1，2，3，4），如下：  
>>>pad = nn.ZeroPad2d(padding=(1, 2, 3, 4))  
>>>y = pad(x)  
>>>得到的y是x在四个方向上按照（1，2，3，4）进行的补零操作

[[][],[][]] 实际数据  
[a,b,c,d]   shape  
dim0 dim1 dim2 dim3  
dimx 意义 个数a  


实际数据 维度axis与中括号
我们把中括号想像成一个个的箱子。  
增加维度无非是增加中括号的意思，至于在哪里加中括号，取决于axis等于几。  
