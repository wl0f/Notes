# @tf.function()的作用

一开始不知道@运算符的作用，网上查了之后才知道是装饰器，也就是对函数进行包装，基本用法如下：
```
def decorator1(func):
    def dec(*args):
        print 'pre action'
        result = func(*args)
        print 'post action'
        return result
    return dec
 
@decorator1
def test_f1(name):
    print name
    return None
 
test_f1('name1') #out: preaction/name1/post action
test_f1('name2') #out: preaction/name2/post action
```
而tensorflow中@tf.function()的作用是能够根据程序生成图，从而获得更好地性能。
