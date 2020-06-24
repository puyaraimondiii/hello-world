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
```python
def rev(poem):
    list1 = list(poem)
    list2 = reversed(list1)
    if list1 == list(list2):
        print("厉害了！！！回文联！！！")
    else:
              print("平平无奇,不是回文联！")
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
```python
def calc(*word):
    length = len(word)
    for i in range(length):
        alp = 0
        num = 0
        space = 0
        other = 0
        for each in word[i]:
            if each.isalpha():
                alp += 1
            elif each.isspace():
                space += 1
            elif each.isdigit():
                num += 1
            else:
                other += 1
        print("第%d字符串共有：英文字母%d个，数字%d个，空格%d个，其他字符%d个。" % (i+1,alp,num,space,other))
```
## Lesson 20
测试题：  
0.如果希望在函数中修改全局变量的值，应该使用什么关键字？  
global
1.在嵌套的函数中，如果希望在内部函数修改外部函数的局部变量，应该使用什么关键字？  
nonlocal
2.Python的函数可以嵌套，但要注意访问的作用域问题哦。请问以下代码存在什么问题呢？  
```Python
def outside():
    print('I am outside!')
    def inside():
        print('I am inside!')

inside()
```
内嵌函数只有外层函数可以调用
3.请问为什么代码A没有报错，但代码B却报错了？应该如何修改？  
代码A：  
```python
def outside():
    var = 5
    def inside():
        var = 3
        print(var)
    inside()
outside()
```
代码B：
```python
def outside():
    var = 5
    def inside():
        print(var)
        var = 3
        
    inside()
outside 
```
```python
def outside():
    var = 5
    def inside():
        nonlocal var
        print(var)
        var = 3
        
    inside()
outside()
```  
4.请问如何访问funIn()呢？ 
```python
def funOut():
    def funIn():
        print('冰果！你成功访问到我啦！') 
    return funIn()
```
funOut()
5.请问如何访问funIn()呢？  
```python
def funOut():
    def funIn():
        print('冰果~你成功访问到我啦！')
    return funIn
```
funOut()()
6.以下是“闭包”的一个例子，请你目测下会打印什么内容？  
```python
def funX():
    x = 5
    def funY():
        nonlocal x
        x +=1
        return x
    return funY
    
a = funX()
print(a())
print(a())
print(a())
```
6  
7  
8  
**动动手：**   
0.请用已学过的只是编写程序，统计下边这个长字符串中各个字符出现的次数并找到小甲鱼送给大家的一句话。  
（由于我们还没有学习到文件读取方法，大家下载后拷贝过去即可）  
请下载字符串文件：string1.txt  
1.请用已学过的知识编写程序，找到小甲鱼藏在下边这个长字符串中的密码，密码的埋藏点符合以下规律：  
a)每位密码为单个小写字母  
b)每位密码的左右两边均有且只有三个大写字母  
(由于我们还没有学习到文件读取方法，大家下载后拷贝过去即可)    
请下载字符串文件：string2.txt  
## Lesson 21
0.请使用lambda表达式将下边函数转变为匿名函数？  
```python
def fun_A(x,y=3):
    return x * y
```
```python
lambda x,y = 3:x * y
```
1.请将下边的匿名函数转变为普通的屌丝函数？  
```python
lambda x : x if x % 2 else None
```
```python
def fun1(x):
	if x % 2:
		return x
	else:
		return None
```
2.感受一下使用匿名函数后给你的编程生活带来的变化？  

3.你可以利用filter()和lambda表达式快速求出100以内所有3的倍数吗？  
```python
list(filter(lambda x:not(x % 3),range(1,100)))
```
4.还记得列表推导式吗？完全可以使用列表推导式代替filter()和lambda组合，你可以做到吗？  
```python
[i for i in range(1,100) if not(i%3)]
```
5.还记得zip吗？使用zip会将两数以元祖的形式绑定在一块，例如：    
```python
>>> list(zip([1,3,5,7,9,],[2,4,6,8,10]))
[(1,2),(3,4),(5,6),(7,8),(9,10)]
```
但如果我希望打包的形式是灵活多变的列表而不是元组（希望是[[1,2],[3,4],[5,6],[7,8],[9,10]]这种形式），你能做到吗？（采用map和lambda表达式）  
```python
list(map(lambda x,y:[x,y],[1,3,5,7,9],[2,4,6,8,10]))
```
6.请目测以下表达式会打印什么？  
```python
def make_repeat(n):
    return lambda s : s * n
    
double = make_repeat(2)
print(double(8))
print(double('FishC'))
```
16  
FishCFishC  

## Lesson 22
0.递归在编程上的形式是如何表现的呢？  
调用函数本身的行为。  
1.递归必须满足哪两个基本条件？  
1）函数调用自身  
2）设置了正确的返回条件  

2.思考一下，按照递归的特性，在编程中有没有不得不使用递归的情况？  
3.用递归法去计算阶乘问题和斐波那契数列是很糟糕的算法，你知道为什么吗？  
4.请聊一聊递归的优缺点（无需官方陈词，想到什么就写什么就可以）  
5.拿手机拍一张“递归自拍照片”  
**动动手：**  
0.使用递归编写一个power()函数模拟内建函数pow(),即power(x,y)为计算并返回x的y次幂的值。  
```python
def power(x,y):
    if y == 0:
        return 1
    else:
       return x * power(x,y-1) 
```
1.使用递归编写一个函数，利用欧几里得算法求最大公约数，例如gcd(x,y)返回值为参数x和参数y的最大公约数。
```python
def gcd(x,y):
    if x <= y:
        x,y = y,x
    if x % y == 0:
        return y
    else:
        return gcd(x,x%y)
```
## Lesson 23 & 24  
动动手：  
0.使用递归编写一个十进制转换为二进制的函数（要求采用“取2取余”的方式，结果与调用bin()一样返回字符串形式）。  
```python
def nbin(x):
    result = ''
    if x:
        result = nbin(x//2)
        return result +  str(x%2)
    else:
        return result
```
1.写一个函数get_digits(n),将参数n分解出来每个位的数字并按顺序存放到列表中。举例：get_digits(12345)==>[1,2,3,4,5]  
```python
result = []
def get_digits(n):
    if n > 0:
        result.insert(0,n%10)
        get_digits(n//10)
get_digits(12345)
print(result)
```
2.还记得求回文字符串那道题吗？现在让你使用递归的方式来求解，亲还能骄傲的说我可以吗？
```python
def is_palindrome(n,start,end):
    if start > end:
        return 1
    else:
        return is_palindrome(n,start+1,end-1) if n[start] == n[end] else 0
string = input("请输入一串字符串：")
length = len(string)-1

if is_palindrome(string,0,length):
               print('\"%s\"是回文字符串！' % string)
else:
               print('\"%s\"不是回文字符串！' % string)
```
3.使用递归编程求解一下问题：  
  有5个人坐在一起，问第五个人多少岁？他说比第4个人大2岁，问第4个人岁数，他说比第3个人大2岁。问第三个人，又说比第2个人大2岁。问第2个人，说比第1个人大2岁。最后问第一个人，他说他10岁。请问第5个人多大？ 
```python
def howold(n,y):
    if n == 1:
        return y
    else:
        return howold(n-1,y+2)
print(howold(5,10))
```
## Lesson 25  
测试题：  
0.当你听到小伙伴们在讨论“映射”、“哈希”、“散列”或者“关系数组”的时候，事实上他们就是在讨论什么呢？  
1.尝试一下将数据('F':70,'C':70,'h':70,'i':70,'s':70)创建为一个字典并访问键'C'对应的值？  
2.用方括号("[]")括起来的数据我们叫列表，那么使用大括号("{}")括起来的数据我们就叫字典，对吗？  
3.你如何解释有些东西字典做得到，但“万能的”列表却难以实现？  
4.下边这些代码，他们都在执行一样的操作吗？你看得出差别吗？  

