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

在python中，个人理解为栈可以用列表来代替  
stack = []  
stack.append(<item>)  
stack.pop(-1)#FILO  
stack.pop(0)#FIFO
