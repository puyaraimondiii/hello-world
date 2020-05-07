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
```python
def findstr(strs,strt):
    if len(strs) != 2:
        strs = input("输入错误，请再次输入子字符串(两个字符)：")
    count = 0
    length = len(strt)
    if strs not in strt:
        print("在目标字符串中未找到子字符串")
    else:
        for each1 in range(length-1):
            if strt[each1] == strs[0]:
                if strt[each1+1] == strs[1]:
                    count += 1
        print('子字符串在目标字符串出现%d次' % count)
```
## Lesson 19
0.下边程序会输入什么？
```python
def next():
    print('我在next()函数里...)
    pre()
    
def pre():
    print('我在pre()函数里...')
next()
```
1.请问一下这个函数有返回值吗？
```python
def hello():
    print('Hello FishC!')
```
2.请问python的return语句可以返回多个不同类型的值吗？
3.目测以下程序会打印什么内容：
```python
def fun(var):
    var = 1314
    print(var,end="")
var=520
fun(var)
print(var)
```
4.目测以下程序会打印什么内容？
```python
var = 'Hi'
def fun1():
    global var
    var = 'Baby'
    return fun2(var)
def fun2(var):
    var += 'I Love You'
    fun3(var)
    return var
def fun3(var):
    var = '小甲鱼'
print(fun1())
```
动动手：
0.编写一个函数，判断传入的字符串参数是否为“回文联”（回文联即用回文形式写成的对联，既可顺读，也可倒读。例如：上海自来水来自上海）
程序执行结果如图：
```python
>>>============================RESTART============================
>>>
请输入一句话：上海自来水来自上海
是回文联！
>>>============================RESTART============================
>>>
请输入一句话：萨芬看阿尕灵粹煎熬
不是回文联！
>>>
```
1.编写一个函数，分别统计出传入字符串参数（可能不只一个参数）的英文字母、空格、数字和其他字符的个数。
程序执行结果如图：
```python
>>>============================RESTART============================
>>>count("I Love fishc.com","I Love you, you love me.")
第1个字符串共有：英文字母13个,数字0个，空格2个，其他字符2个。
第2个字符串共有：英文字母17个，数字0个，空格5个，其他字符2个。
>>>
```
