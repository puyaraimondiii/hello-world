## Lesson 19
0.编写一个符合以下要求的函数：  
a）计算打印所有参数的和乘以基数（base=3）的结果  
b）如果参数最后一个参数为（base=5），则设定基数为5，基数不参与求和计算  
```python
def mFun(*param,base=3)
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
如果一个3位数等于其各个位数的立方和，则称这个为水仙花数。例如153=1<sup>3</sup>+5<sup>3</sup>+3<sup>3</sup>,因此153是一个水仙花数。编写一个程序，找出所有的水仙花数。
```python

```
