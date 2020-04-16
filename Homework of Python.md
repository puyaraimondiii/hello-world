## Lesson 18
0.编写一个符合以下要求的函数：  
a）计算打印所有参数的和乘以基数（base=3）的结果  
b）如果参数最后一个参数为（base=5），则设定基数为5，基数不参与求和计算  
```python
def mFun(*param,base=3):
    'a)计算打印所有参数的和乘以基数的结果\nb)如果参数最后一个参数为5,则设定基数为5，基数不参与求和计算'
    if param[-1] == 5:
            result = 0
            for each in param:
                    result += each
            result = (result-5)*5
    else:
            result = 0
            for each in param:
                    result += each
            result *= base
    print("结果是：",result)
```
1.寻找水仙花数  
如果一个3位数等于其各个位数的立方和，则称这个为水仙花数。例如153=1<sup>3</sup>+5<sup>3</sup>+3<sup>3</sup>，因此153是一个水仙花数。编写一个程序，找出所有的水仙花数。
```python
def nar():
    '寻找水仙花数'
    print("所有的水仙花数分别是：",end="")
    for each in range(100,1000):
        temp = each
        sum = 0 
        sum = (temp//100)**3 + (temp//10%10)**3+ (temp%10)**3
        if sum == each:
            print(each,end=" ")
```
```python
def nar():
    for each in range(100,1000):
        temp = each
        sum = 0
        while temp:
            sum = sum + (temp%10)**3
            temp = temp // 10
        if sum == each:
            print(each,end="\t")
print("all nar are",end="")
```
2.编写一个函数findstr(),该函数统计一个长度为2的子字符串在另一个字符串中出现的次数。例如：假定输入的字符串为“You cannot improve your past, but you can improve your future. Once time is wasted, life is wasted.”，字符串为“im”，函数执行后打印“子字符串在目标字符串中共出现了3次”。  
```python
执行程序效果：
>>>-----------------RESTART-----------------  
请输入目标字符串：You cannot improve your past, but you can improve your future. Once time is wasted, life is wasted.
请输入子字符串（两个字符）：im
子字符串怎目标字符串中共出现3次
>>>
```
