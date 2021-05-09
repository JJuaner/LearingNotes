python解释执行原理  
https://www.zhihu.com/question/401754962   
https://www.zhihu.com/question/414256612  

在Python中有两种函数，一种是def定义的函数，另一种是lambda函数
>>lambda函数也叫匿名函数,即函数没有具体的名称->函数极简模式
>>>why lambda：不用费神地去命名一个函数的名字，可以快速的实现某项功能，减少了代码的冗余  
>>>语法：lambda argument_list:expersion 只能由一条表达式组成
***

list常用操作
>>！！切片操作！！  
>>倒序/反转字符串：s[::-1]

***
判断None
>>1.if X is None  
>>2.if not X:当X为None,  False, 空字符串"", 0, 空列表[], 空字典{}, 空元组()这些时，not X为真，即无法分辨出他们之间的不同。  
>>3.if not X is None

***
C语言的指针表示的是数据的地址,首先要理解这一点  
python当中是没有办法直接使用地址的,这是本质上的区别  

***

在python中，个人理解为栈可以用列表来代替  
stack = []  
stack.append(<item>)  
stack.pop(-1)#FILO  
stack.pop(0)#FIFO

***
return与yield  
yield与生成器  
带yield的函数是一个生成器，而不是一个函数。生成器有一个next函数。

***
pythonGC机制
数据是保存在内存中，而变量只是一个链接，指向内存地址，而变量的赋值的本质是，新的变量也指向内存中的相同地址，只有所有链接都被删除了，那块内存才会被回收，那块内存区域中保存的数据就不复存在了

## pandas
### DataFrame
pandas的DataFrame对象，本质上是二维矩阵，跟常规二维矩阵的差别在于前者额外指定了每一行和每一列的名称。
这样内部数据抽取既可以用“行列名称（对应.loc[]方法）”，也可以用“矩阵下标（对应.iloc[]方法）”两种方式进行。
DataFrame对象的.loc[,]和.iloc[,]方法用于抽取数据，.loc[,]用行列的标签名作为参数，.iloc[,]用二维矩阵元素的网格下标作为参数。
