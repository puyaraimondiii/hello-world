# hello-world

It's my first repository.
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
