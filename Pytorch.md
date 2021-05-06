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


实际数据 盒子模型
维度axis/中括号/箱子 最外层是0，第一个是1，向箱子里面寻找
我们把中括号想像成一个个的箱子。  
增加维度无非是增加中括号的意思，至于在哪里加中括号，取决于axis等于几。  

python基本数据结构：列表、元组、字典、集合
python自带list/numpy的数组array
python没有数组但可以用list做数组，list中的数据类不必相同的（因为在list 中保存的是数据的存放的地址，即指针，并非数据。），而array的中的类型必须全部相同  
list有逗号，array无逗号分隔有shape   
array的* 就是对应元素相乘，如果行或列数不匹配会自动补全，这就是numpy的”广播” 
array想要实现矩阵相乘，使用np.dot(array1, array2)  


***
可以通过Model.parameters()获取网络参数  
具体实现：parameters->named_parameters->类成员变量->有序字典->register_parameter  
参考：https://blog.csdn.net/idwtwt/article/details/82195000

***
踩坑交叉熵
**F.cross_entropy()**
1.F.Cross_entropy(input, target)函数中包含了softmaxsoftmax和log的操作，即网络计算送入的input参数不需要进行这两个操作。并且这两个操作不影响tensor维度。
2.在one-hot编码的前提下，在pytorch代码中target不需要以one-hot形式表示，而是直接用scalar，scalar的值则是真实类别的index。  
https://blog.csdn.net/wuliBob/article/details/104119616  
F.Cross_entropy输出模式的控制（reduction）  
https://blog.csdn.net/goodxin_ie/article/details/89645358  

**nn.CrossEntropyLoss()**
pytorch中计算的是batch-loss是平均值  
https://blog.csdn.net/weixin_41122036/article/details/103270152?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control

