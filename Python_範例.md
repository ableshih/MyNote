# Python 範例


****
### if
    
```
    if 判断条件1:

        执行语句1……

    elif 判断条件2:

        执行语句2……

    elif 判断条件3:

        执行语句3……

    else:

        执行语句4……
```
```
if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3
```    
```
#!/usr/bin/python3
 
var1 = 100
if var1:
    print ("1 - if 表达式条件为 true")
    print (var1)
 
var2 = 0
if var2:
    print ("2 - if 表达式条件为 true")
    print (var2)
print ("Good bye!")


执行以上代码，输出结果为：
1 - if 表达式条件为 true
100
Good bye!
```
### while
```
#!/usr/bin/env python3
 
n = 100
 
sum = 0
counter = 1
while counter <= n:
    sum = sum + counter
    counter += 1
 
print("1 到 %d 之和为: %d" % (n,sum))

执行结果如下：
1 到 100 之和为: 5050
```
```
无限循环
我们可以通过设置条件表达式永远不为 false 来实现无限循环，实例如下：

实例
#!/usr/bin/python3
 
var = 1
while var == 1 :  # 表达式永远为 true
   num = int(input("输入一个数字  :"))
   print ("你输入的数字是: ", num)
 
print ("Good bye!")

执行以上脚本，输出结果如下：
输入一个数字  :5
你输入的数字是:  5
输入一个数字  :
```


### pass 
```
pass 语句

Python pass 是空语句，是为了保持程序结构的完整性。



pass 不做任何事情，一般用做占位语句。



def function():

  # 在Python3.x的时候pass可以写或不写

  pass
```
```
Python pass是空语句，是为了保持程序结构的完整性。

pass 不做任何事情，一般用做占位语句，如下实例

实例
>>>while True:
...     pass  # 等待键盘中断 (Ctrl+C)
```

```
以下实例在字母为 o 时 执行 pass 语句块:

实例
#!/usr/bin/python3
 
for letter in 'Runoob': 
   if letter == 'o':
      pass
      print ('执行 pass 块')
   print ('当前字母 :', letter)
 
print ("Good bye!")

执行以上脚本输出结果为：
当前字母 : R
当前字母 : u
当前字母 : n
执行 pass 块
当前字母 ​: o
执行 pass 块
当前字母 ​: o
当前字母 : b
Good by!
```
### 函数
```
语法
Python 定义函数使用 def 关键字，一般格式如下：

def 函数名（参数列表）:
    函数体
默认情况下，参数值和参数名称是按函数声明中定义的顺序匹配起来的。

实例
让我们使用函数来输出"Hello World！"：

#!/usr/bin/python3

def hello() :
    print("Hello World!")

hello()
```
```
更复杂点的应用，函数中带上参数变量:

实例 
比较两个数，并返回较大的数:

#!/usr/bin/python3
 
def max(a, b):
    if a > b:
        return a
    else:
        return b
 
a = 4
b = 5
print(max(a, b))

以上实例输出结果： 5
```

```
计算面积函数:

#!/usr/bin/python3
 
# 计算面积函数
def area(width, height):
    return width * height
 
def print_welcome(name):
    print("Welcome", name)
 
print_welcome("Runoob")
w = 4
h = 5
print("width =", w, " height =", h, " area =", area(w, h))

以上实例输出结果：
Welcome Runoob
width = 4  height = 5  area = 20
```
```
函数调用
定义一个函数：给了函数一个名称，指定了函数里包含的参数，和代码块结构。

这个函数的基本结构完成以后，你可以通过另一个函数调用执行，也可以直接从 Python 命令提示符执行。

如下实例调用了 printme() 函数：

实例(Python 3.0+)
#!/usr/bin/python3
 
# 定义函数
def printme( str ):
   # 打印任何传入的字符串
   print (str)
   return
 
# 调用函数
printme("我要调用用户自定义函数!")
printme("再次调用同一函数")

以上实例输出结果：
我要调用用户自定义函数!
再次调用同一函数
```
### return语句
```
return语句
return [表达式] 语句用于退出函数，选择性地向调用方返回一个表达式。不带参数值的return语句返回None。之前的例子都没有示范如何返回数值，以下实例演示了 return 语句的用法：

实例(Python 3.0+)
#!/usr/bin/python3
 
# 可写函数说明
def sum( arg1, arg2 ):
   # 返回2个参数的和."
   total = arg1 + arg2
   print ("函数内 : ", total)
   return total
 
# 调用sum函数
total = sum( 10, 20 )
print ("函数外 : ", total)

以上实例输出结果：
函数内 :  30
函数外 :  30
```

### from … import 
```
from … import 语句
Python 的 from 语句让你从模块中导入一个指定的部分到当前命名空间中，语法如下：

from modname import name1[, name2[, ... nameN]]
例如，要导入模块 fibo 的 fib 函数，使用如下语句：

>>> from fibo import fib, fib2
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
这个声明不会把整个fibo模块导入到当前的命名空间中，它只会将fibo里的fib函数引入进来。
```
### from … import * 
```
from … import * 语句
把一个模块的所有内容全都导入到当前的命名空间也是可行的，只需使用如下声明：

from modname import *
这提供了一个简单的方法来导入一个模块中的所有项目。然而这种声明不该被过多地使用。
```

### __name__
```
__name__属性
一个模块被另一个程序第一次引入时，其主程序将运行。如果我们想在模块被引入时，模块中的某一程序块不执行，我们可以用__name__属性来使该程序块仅在该模块自身运行时执行。

#!/usr/bin/python3
# Filename: using_name.py

if __name__ == '__main__':
   print('程序自身在运行')
else:
   print('我来自另一模块')
运行输出如下：

$ python using_name.py
程序自身在运行
$ python
>>> import using_name
我来自另一模块
>>>
```
### 读取键盘输入
```
读取键盘输入
Python 提供了 input() 内置函数从标准输入读入一行文本，默认的标准输入是键盘。

实例
#!/usr/bin/python3

str = input("请输入：");
print ("你输入的内容是: ", str)
这会产生如下的对应着输入的结果：

请输入：菜鸟教程
你输入的内容是:  菜鸟教程
```
### 读和写文件
```
读和写文件
open() 将会返回一个 file 对象，基本语法格式如下:

open(filename, mode)
```
```
#!/usr/bin/python3

# 打开一个文件
f = open("/tmp/foo.txt", "w")

f.write( "Python 是一个非常好的语言。\n是的，的确非常好!!\n" )

# 关闭打开的文件
f.close()
```
### continue
```
continue 语句

Python continue 语句跳出本次循环，而break跳出整个循环。



continue 语句用来告诉Python跳过当前循环的剩余语句，然后继续进行下一轮循环。



continue语句用在while和for循环中。



#!/usr/bin/python

# -*- coding: UTF-8 -*-



n = 0

while n < 10:

  n = n + 1

  if n % 2 == 0:   # 如果n是偶数，执行continue语句

    continue    # continue语句会直接继续下一轮循环，后续的print()语句不会执行

  print(n)
```
### break
```
Python break 语句

Python break语句，就像在C语言中，打破了最小封闭for或while循环。



break语句用来终止循环语句，即循环条件没有False条件或者序列还没被完全递归完，也会停止执行循环语句。



break语句用在while和for循环中。



如果您使用嵌套循环，break语句将停止执行最深层的循环，并开始执行下一行代码。





#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

for letter in 'Python':   # 第一个实例

  if letter == 'h':

   break

  print '当前字母 :', letter

  

var = 10          # 第二个实例

while var > 0:        

  print '当前变量值 :', var

  var = var -1

  if var == 5:  # 当变量 var 等于 5 时退出循环

   break

 

print "Good bye!"


```


### b
```
#!/usr/bin/python3
 
count = 0
while count < 5:
   print (count, " 小于 5")
   count = count + 1
else:
   print (count, " 大于或等于 5")
执行以上脚本，输出结果如下：

0  小于 5
1  小于 5
2  小于 5
3  小于 5
4  小于 5
5  大于或等于 5
```
### while 循环使用 else 语句
```
如果 while 后面的条件语句为 false 时，则执行 else 的语句块。

语法格式如下：

while <expr>:
    <statement(s)>
else:
    <additional_statement(s)>


expr 条件语句为 true 则执行 statement(s) 语句块，如果为 false，则执行 additional_statement(s)。

循环输出数字，并判断大小：

实例
#!/usr/bin/python3
 
count = 0
while ​count < 5:
  ​print (count, " 小于 5")
  ​count = count + 1
else:
  ​print ​(count, " 大于或等于 5

执行以上脚本，输出结果如下：
0  小于 5
1  ​小于 5
2  ​小于 5
3  ​小于 5
4  ​小于 5
5  ​大于

```


### for
```
for <variable> in <sequence>:
    <statements>
else:
    <statements>

```

```
#!/usr/bin/python3
 
sites = ["Baidu", "Google","Runoob","Taobao"]
for site in sites:
    if site == "Runoob":
        print("菜鸟教程!")
        break
    print("循环数据 " + site)
else:
    print("没有循环数据!")
print("完成循环!")

执行脚本后，在循环到 "Runoob"时会跳出循环体：
循环数据 Baidu
循环数据 Google
菜鸟教程!
完成循环!
```

```
for 循环嵌套语法：







for iterating_var in sequence:



 for iterating_var in sequence:



  statements(s)



 statements(s)

  

  



#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

fruits = ['banana', 'apple', 'mango']

for index in range(len(fruits)):

  print ('当前水果 : %s' % fruits[index])

 

print ("Good bye!")


```

```
#!/usr/bin/python

# -*- coding: UTF-8 -*-

for num in range(10,20):  # 迭代 10 到 20 之间的数字

   for i in range(2,num): # 根据因子迭代

      if num%i == 0:      # 确定第一个因子

         j=num/i          # 计算第二个因子

         print ('%d 等于 %d * %d' % (num,i,j))

         break            # 跳出当前循环

   else:                  # 循环的 else 部分

      print ('%d 是一个质数' % num)
```
### range
```
range()函数
如果你需要遍历数字序列，可以使用内置range()函数。它会生成数列，例如:

实例
>>>for i in range(5):
...     print(i)
...
0
1
2
3
4

你也可以使用range指定区间的值：

实例
>>>for i in range(5,9) :
    print(i)
 
    
5
6
7
8
>>>

也可以使range以指定数字开始并指定不同的增量(甚至可以是负数，有时这也叫做'步长'):

实例
>>>for i in range(0, 10, 3) :
    print(i)
 
    
0
3
6
9
>>>
```
### while
```
while 循环嵌套语法：



while expression:

  while expression:

   statement(s)

  statement(s)

  



#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

i = 2

while(i < 100):

  j = 2

  while(j <= (i/j)):

   if not(i%j): break

   j = j + 1

  if (j > i/j) : print i, " 是素数"

  i = i + 1

 

print "Good bye!"


```
### 类对象
```
类对象
类对象支持两种操作：属性引用和实例化。

属性引用使用和 Python 中所有的属性引用一样的标准语法：obj.name。

类对象创建后，类命名空间中所有的命名都是有效属性名。所以如果类定义是这样:

实例(Python 3.0+)
#!/usr/bin/python3
 
class MyClass:
    """一个简单的类实例"""
    i = 12345
    def f(self):
        return 'hello world'
 
# 实例化类
x = MyClass()
 
# 访问类的属性和方法
print("MyClass 类的属性 i 为：", x.i)
print("MyClass 类的方法 f 输出为：", x.f())
以上创建了一个新的类实例并将该对象赋给局部变量 x，x 为空的对象。

执行以上程序输出结果为：

MyClass 类的属性 i 为： 12345
MyClass 类的方法 f 输出为： hello world
```
### self代表类的实例
```
self代表类的实例，而非类
类的方法与普通的函数只有一个特别的区别——它们必须有一个额外的第一个参数名称, 按照惯例它的名称是 self。

class Test:
    def prt(self):
        print(self)
        print(self.__class__)
 
t = Test()
t.prt()
以上实例执行结果为：

<__main__.Test instance at 0x100771878>
__main__.Test
```
### 类的方法
```
类的方法
在类的内部，使用 def 关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 self, 且为第一个参数，self 代表的是类的实例。

实例(Python 3.0+)
#!/usr/bin/python3
 
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
# 实例化类
p = people('runoob',10,30)
p.speak()
执行以上程序输出结果为：

runoob 说: 我 10 岁。
```
### 继承
```
#!/usr/bin/python3
 
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构函
        people.__init__(self,n,a,w)
        self.grade = g
    #覆写父类的方法
    def speak(self):
        print("%s 说: 我 %d 岁了，我在读 %d 年级"%(self.name,self.age,self.grade))
 
 
 
s = student('ken',10,60,3)
s.speak()
执行以上程序输出结果为：

ken 说: 我 10 岁了，我在读 3 年级
```

### 判斷式
#### try except 錯誤與異常
```
while True:
    try:
        x = int(input("请输入一个数字: "))
        break
    except ValueError:
        print("您输入的不是数字，请再次尝试输入！")
```
```
import sys

try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
except OSError as err:
    print("OS error: {0}".format(err))
except ValueError:
    print("Could not convert data to an integer.")
except:
    print("Unexpected error:", sys.exc_info()[0])
    raise
```
```
for arg in sys.argv[1:]:
    try:
        f = open(arg, 'r')
    except IOError:
        print('cannot open', arg)
    else:
        print(arg, 'has', len(f.readlines()), 'lines')
        f.close()
```

### 多继承
```
#!/usr/bin/python3
 
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构函
        people.__init__(self,n,a,w)
        self.grade = g
    #覆写父类的方法
    def speak(self):
        print("%s 说: 我 %d 岁了，我在读 %d 年级"%(self.name,self.age,self.grade))
 
#另一个类，多重继承之前的准备
class speaker():
    topic = ''
    name = ''
    def __init__(self,n,t):
        self.name = n
        self.topic = t
    def speak(self):
        print("我叫 %s，我是一个演说家，我演讲的主题是 %s"%(self.name,self.topic))
 
#多重继承
class sample(speaker,student):
    a =''
    def __init__(self,n,a,w,g,t):
        student.__init__(self,n,a,w,g)
        speaker.__init__(self,n,t)
 
test = sample("Tim",25,80,4,"Python")
test.speak()   #方法名同，默认调用的是在括号中参数位置排前父类的方法
执行以上程序输出结果为：

我叫 Tim，我是一个演说家，我演讲的主题是 Python
```



### 获取格式化的时间
```



获取格式化的时间

你可以根据需求选取各种格式，但是最简单的获取可读的时间模式的函数是asctime():



实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

import time

 

localtime = time.asctime( time.localtime(time.time()) )

print "本地时间为 :", localtime

以上实例输出结果：



本地时间为 : Thu Apr 7 10:05:21 2016



#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

import time

 

# 格式化成2016-03-20 11:45:39形式

print time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()) 

 

# 格式化成Sat Mar 28 22:24:24 2016形式

print time.strftime("%a %b %d %H:%M:%S %Y", time.localtime()) 

  

# 将格式字符串转换为时间戳

a = "Sat Mar 28 22:24:24 2016"

print time.mktime(time.strptime(a,"%a %b %d %H:%M:%S %Y"))

以上实例输出结果：



2016-04-07 10:25:09

Thu Apr 07 10:25:09 2016

1459175064.0




```

### 模組import
#### 日期和时间
##### 获取当前时间
```
获取当前时间

从返回浮点数的时间戳方式向时间元组转换，只要将浮点数传递给如localtime之类的函数。



实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

import time

 

localtime = time.localtime(time.time())

print "本地时间为 :", localtime
```
### 获取某月日历
```
获取某月日历

Calendar模块有很广泛的方法用来处理年历和月历，例如打印某月的月历：



实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

import calendar

 

cal = calendar.month(2016, 1)

print "以下输出2016年1月份的日历:"

print cal
```

### 函式
```
def functionname( parameters ):

   "函数_文档字符串"

   function_suite

   return [expression]
```

```
#!/usr/bin/python

# -*- coding: UTF-8 -*-

# 定义函数

def printme( str ):

   "打印任何传入的字符串"

   print str

   return

# 调用函数

printme("我要调用用户自定义函数!")

printme("再次调用同一函数")
```

```
传不可变对象实例

实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

def ChangeInt( a ):

  a = 10

 

b = 2

ChangeInt(b)

print b # 结果是 2
```

```
传可变对象实例

实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

# 可写函数说明

def changeme( mylist ):

  "修改传入的列表"

  mylist.append([1,2,3,4])

  print "函数内取值: ", mylist

  return

 

# 调用changeme函数

mylist = [10,20,30]

changeme( mylist )

print "函数外取值: ", mylist

实例中传入函数的和在末尾添加新内容的对象用的是同一个引用，故输出结果如下：



函数内取值: [10, 20, 30, [1, 2, 3, 4]]

函数外取值: [10, 20, 30, [1, 2, 3, 4]]
```

```
#!/usr/bin/python

# -*- coding: UTF-8 -*-

#可写函数说明

def printme( str ):

   "打印任何传入的字符串"

   print str

   return

#调用printme函数

printme()
```

```
关键字参数

关键字参数和函数调用关系紧密，函数调用使用关键字参数来确定传入的参数值。

使用关键字参数允许函数调用时参数的顺序与声明时不一致，因为 Python 解释器能够用参数名匹配参数值。

以下实例在函数 printme() 调用时使用参数名：

实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

#可写函数说明

def printme( str ):

   "打印任何传入的字符串"

   print str

   return

#调用printme函数

printme( str = "My string")

以上实例输出结果：



My string
```




### print
```
print ("Hello, Python!")
```

```
符串，如下实例：



实例(Python 2.0+)

#!/usr/bin/python

 

var1 = 'Hello World!'

var2 = "Python Runoob"

 

print "var1[0]: ", var1[0]

print "var2[1:5]: ", var2[1:5]





字符串连接

我们可以对字符串进行截取并与其他字符串进行连接，如下实例：



实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

var1 = 'Hello World!'

 

print "输出 :- ", var1[:6] + 'Runoob!'

以上实例执行结果



输出 :- Hello Runoob!



转义字符

在需要在字符中使用特殊字符时，python 用反斜杠 \ 转义字符。如下表：



转义字符	描述

\(在行尾时)	续行符

\\	反斜杠符号

\'	单引号

\"	双引号

\a	响铃

\b	退格(Backspace)

\e	转义

\000	空

\n	换行

\v	纵向制表符

\t	横向制表符

\r	回车

\f	换页

\oyy	八进制数，y 代表 0~7 的字符，例如：\012 代表换行。

\xyy	十六进制数，以 \x 开头，yy代表的字符，例如：\x0a代表换行

\other	其它的字符以普通格式输出







字符串运算符

下表实例变量 a 值为字符串 "Hello"，b 变量值为 "Python"：



操作符	描述	实例

+	字符串连接	

>>>a + b

'HelloPython'

*	重复输出字符串	

>>>a * 2

'HelloHello'

[]	通过索引获取字符串中字符	

>>>a[1]

'e'

[ : ]	截取字符串中的一部分	

>>>a[1:4]

'ell'

in	成员运算符 - 如果字符串中包含给定的字符返回 True	

>>>"H" in a

True

not in	成员运算符 - 如果字符串中不包含给定的字符返回 True	

>>>"M" not in a

True

r/R	原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母"r"（可以大小写）以外，与普通字符串有着几乎完全相同的语法。	

>>>print r'\n'

\n

>>> print R'\n'

\n

%	格式字符串	请看下一章节



符串格式化符号:



  符  号	描述

   %c	 格式化字符及其ASCII码

   %s	 格式化字符串

   %d	 格式化整数

   %u	 格式化无符号整型

   %o	 格式化无符号八进制数

   %x	 格式化无符号十六进制数

   %X	 格式化无符号十六进制数（大写）

   %f	 格式化浮点数字，可指定小数点后的精度

   %e	 用科学计数法格式化浮点数

   %E	 作用同%e，用科学计数法格式化浮点数

   %g	 %f和%e的简写

   %G	 %F 和 %E 的简写

   %p	 用十六进制数格式化变量的地址

格式化操作符辅助指令:



符号	功能

*	定义宽度或者小数点精度

-	用做左对齐

+	在正数前面显示加号( + )

<sp>	在正数前面显示空格

#	在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')

0	显示的数字前面填充'0'而不是默认的空格

%	'%%'输出一个单一的'%'

(var)	映射变量(字典参数)

m.n.	m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)

Python2.6 开始，新增了一种格式化字符串的函数 str.format()，它增强了字符串格式化的功能。



Python 三引号

Python 中三引号可以将复杂的字符串进行赋值。



Python 三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。



三引号的语法是一对连续的单引号或者双引号（通常都是成对的用）。



 >>> hi = '''hi 

there'''

>>> hi  # repr()

'hi\nthere'

>>> print hi # str()

hi 

there  








```

### 元组
```

Python的元组与列表类似，不同之处在于元组的元素不能修改。



元组使用小括号，列表使用方括号。



元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。



如下实例：



实例(Python 2.0+)

tup1 = ('physics', 'chemistry', 1997, 2000)

tup2 = (1, 2, 3, 4, 5 )

tup3 = "a", "b", "c", "d"





#!/usr/bin/python

 

tup1 = ('physics', 'chemistry', 1997, 2000)

tup2 = (1, 2, 3, 4, 5, 6, 7 )

 

print "tup1[0]: ", tup1[0]

print "tup2[1:5]: ", tup2[1:5]

以上实例输出结果：



tup1[0]: physics

tup2[1:5]: (2, 3, 4, 5)
```

### 字典(Dictionary)
```
字典(Dictionary)

字典是另一种可变容器模型，且可存储任意类型对象。



字典的每个键值 key=>value 对用冒号 : 分割，每个键值对之间用逗号 , 分割，整个字典包括在花括号 {} 中 ,格式如下所示：



d = {key1 : value1, key2 : value2 }

注意：dict 作为 Python 的关键字和内置函数，变量名不建议命名为 dict。



键一般是唯一的，如果重复最后的一个键值对会替换前面的，值不需要唯一。



>>> tinydict = {'a': 1, 'b': 2, 'b': '3'}

>>> tinydict['b']

'3'

>>> tinydict

{'a': 1, 'b': '3'}

值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。



一个简单的字典实例：



tinydict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}

也可如此创建字典：



tinydict1 = { 'abc': 456 }

tinydict2 = { 'abc': 123, 98.6: 37 }
```
### return 
```
return 语句

return语句[表达式]退出函数，选择性地向调用方返回一个表达式。不带参数值的return语句返回None。之前的例子都没有示范如何返回数值，下例便告诉你怎么做：

实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

# 可写函数说明

def sum( arg1, arg2 ):

   # 返回2个参数的和."

   total = arg1 + arg2

   print "函数内 : ", total

   return total

# 调用sum函数

total = sum( 10, 20 )

以上实例输出结果：



函数内 :  30
```

### 全局变量和局部变量
```
全局变量和局部变量

定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域。



局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。调用函数时，所有在函数内声明的变量名称都将被加入到作用域中。如下实例：



实例(Python 2.0+)

#!/usr/bin/python

# -*- coding: UTF-8 -*-

 

total = 0 # 这是一个全局变量

# 可写函数说明

def sum( arg1, arg2 ):

  #返回2个参数的和."

  total = arg1 + arg2 # total在这里是局部变量.

  print "函数内是局部变量 : ", total

  return total

 

#调用sum函数

sum( 10, 20 )

print "函数外是全局变量 : ", total

以上实例输出结果：



函数内是局部变量 : 30

函数外是全局变量 : 0
```

## JSON 



```
#!/usr/bin/python3
 
import json
 
# Python 字典类型转换为 JSON 对象
data = {
    'no' : 1,
    'name' : 'Runoob',
    'url' : 'http://www.runoob.com'
}
 
json_str = json.dumps(data)
print ("Python 原始数据：", repr(data))
print ("JSON 对象：", json_str)
执行以上代码输出结果为：

Python 原始数据： {'url': 'http://www.runoob.com', 'no': 1, 'name': 'Runoob'}
JSON 对象： {"url": "http://www.runoob.com", "no": 1, "name": "Runoob"}
```



```
#!/usr/bin/python3
 
import json
 
# Python 字典类型转换为 JSON 对象
data1 = {
    'no' : 1,
    'name' : 'Runoob',
    'url' : 'http://www.runoob.com'
}
 
json_str = json.dumps(data1)
print ("Python 原始数据：", repr(data1))
print ("JSON 对象：", json_str)
 
# 将 JSON 对象转换为 Python 字典
data2 = json.loads(json_str)
print ("data2['name']: ", data2['name'])
print ("data2['url']: ", data2['url'])
执行以上代码输出结果为：

Python 原始数据： {'name': 'Runoob', 'no': 1, 'url': 'http://www.runoob.com'}
JSON 对象： {"name": "Runoob", "no": 1, "url": "http://www.runoob.com"}
data2['name']:  Runoob
data2['url']:  http://www.runoob.com
```


```
# 写入 JSON 数据
with open('data.json', 'w') as f:
    json.dump(data, f)
 
# 读取数据
with open('data.json', 'r') as f:
    data = json.load(f)
```


## 线程优先级队列（ Queue）
```
#!/usr/bin/python3

import queue
import threading
import time

exitFlag = 0

class myThread (threading.Thread):
    def __init__(self, threadID, name, q):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.q = q
    def run(self):
        print ("开启线程：" + self.name)
        process_data(self.name, self.q)
        print ("退出线程：" + self.name)

def process_data(threadName, q):
    while not exitFlag:
        queueLock.acquire()
        if not workQueue.empty():
            data = q.get()
            queueLock.release()
            print ("%s processing %s" % (threadName, data))
        else:
            queueLock.release()
        time.sleep(1)

threadList = ["Thread-1", "Thread-2", "Thread-3"]
nameList = ["One", "Two", "Three", "Four", "Five"]
queueLock = threading.Lock()
workQueue = queue.Queue(10)
threads = []
threadID = 1

# 创建新线程
for tName in threadList:
    thread = myThread(threadID, tName, workQueue)
    thread.start()
    threads.append(thread)
    threadID += 1

# 填充队列
queueLock.acquire()
for word in nameList:
    workQueue.put(word)
queueLock.release()

# 等待队列清空
while not workQueue.empty():
    pass

# 通知线程是时候退出
exitFlag = 1

# 等待所有线程完成
for t in threads:
    t.join()
print ("退出主线程")
以上程序执行结果：

开启线程：Thread-1
开启线程：Thread-2
开启线程：Thread-3
Thread-3 processing One
Thread-1 processing Two
Thread-2 processing Three
Thread-3 processing Four
Thread-1 processing Five
退出线程：Thread-3
退出线程：Thread-2
退出线程：Thread-1
退出主线程
```


## 正则表达式
```
Python3 正则表达式
正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。

Python 自1.5版本起增加了re 模块，它提供 Perl 风格的正则表达式模式。

re 模块使 Python 语言拥有全部的正则表达式功能。

compile 函数根据一个模式字符串和可选的标志参数生成一个正则表达式对象。该对象拥有一系列方法用于正则表达式匹配和替换。

re 模块也提供了与这些方法功能完全一致的函数，这些函数使用一个模式字符串做为它们的第一个参数。

本章节主要介绍 Python 中常用的正则表达式处理函数，如果你对正则表达式不了解，可以查看我们的 正则表达式 - 教程。

re.match函数
re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none。

函数语法：

re.match(pattern, string, flags=0)
```

```
#!/usr/bin/python3
import re
 
line = "Cats are smarter than dogs"
# .* 表示任意匹配除换行符（\n、\r）之外的任何单个或多个字符
# (.*?) 表示"非贪婪"模式，只保存第一个匹配到的子串
matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if matchObj:
   print ("matchObj.group() : ", matchObj.group())
   print ("matchObj.group(1) : ", matchObj.group(1))
   print ("matchObj.group(2) : ", matchObj.group(2))
else:
   print ("No match!!")
以上实例执行结果如下：

matchObj.group() :  Cats are smarter than dogs
matchObj.group(1) :  Cats
matchObj.group(2) :  smarter
```

```
#!/usr/bin/python3
 
import re
 
print(re.search('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.search('com', 'www.runoob.com').span())         # 不在起始位置匹配
以上实例运行输出结果为：

(0, 3)
(11, 14)
```

```
#!/usr/bin/python3
 
import re
 
line = "Cats are smarter than dogs"
 
searchObj = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if searchObj:
   print ("searchObj.group() : ", searchObj.group())
   print ("searchObj.group(1) : ", searchObj.group(1))
   print ("searchObj.group(2) : ", searchObj.group(2))
else:
   print ("Nothing found!!")
以上实例执行结果如下：
searchObj.group() :  Cats are smarter than dogs
searchObj.group(1) :  Cats
searchObj.group(2) :  smarter
```
## Python3 多线程
```
#!/usr/bin/python3

import _thread
import time

# 为线程定义一个函数
def print_time( threadName, delay):
   count = 0
   while count < 5:
      time.sleep(delay)
      count += 1
      print ("%s: %s" % ( threadName, time.ctime(time.time()) ))

# 创建两个线程
try:
   _thread.start_new_thread( print_time, ("Thread-1", 2, ) )
   _thread.start_new_thread( print_time, ("Thread-2", 4, ) )
except:
   print ("Error: 无法启动线程")

while 1:
   pass

执行以上程序输出结果如下：
Thread-1: Wed Apr  6 11:36:31 2016
Thread-1: Wed Apr  6 11:36:33 2016
Thread-2: Wed Apr  6 11:36:33 2016
Thread-1: Wed Apr  6 11:36:35 2016
Thread-1: Wed Apr  6 11:36:37 2016
Thread-2: Wed Apr  6 11:36:37 2016
Thread-1: Wed Apr  6 11:36:39 2016
Thread-2: Wed Apr  6 11:36:41 2016
Thread-2: Wed Apr  6 11:36:45 2016
Thread-2: Wed Apr  6 11:36:49 2016
执行以上程后可以按下 ctrl-c 退出。
```

## threading

```
使用 threading 模块创建线程
我们可以通过直接从 threading.Thread 继承创建一个新的子类，并实例化后调用 start() 方法启动新线程，即它调用了线程的 run() 方法：

实例
#!/usr/bin/python3

import threading
import time

exitFlag = 0

class myThread (threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter
    def run(self):
        print ("开始线程：" + self.name)
        print_time(self.name, self.counter, 5)
        print ("退出线程：" + self.name)

def print_time(threadName, delay, counter):
    while counter:
        if exitFlag:
            threadName.exit()
        time.sleep(delay)
        print ("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1

# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()
thread1.join()
thread2.join()
print ("退出主线程")
以上程序执行结果如下；

开始线程：Thread-1
开始线程：Thread-2
Thread-1: Wed Apr  6 11:46:46 2016
Thread-1: Wed Apr  6 11:46:47 2016
Thread-2: Wed Apr  6 11:46:47 2016
Thread-1: Wed Apr  6 11:46:48 2016
Thread-1: Wed Apr  6 11:46:49 2016
Thread-2: Wed Apr  6 11:46:49 2016
Thread-1: Wed Apr  6 11:46:50 2016
退出线程：Thread-1
Thread-2: Wed Apr  6 11:46:51 2016
Thread-2: Wed Apr  6 11:46:53 2016
Thread-2: Wed Apr  6 11:46:55 2016
退出线程：Thread-2
退出主线程
```
## 线程同步
```
#!/usr/bin/python3

import threading
import time

class myThread (threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter
    def run(self):
        print ("开启线程： " + self.name)
        # 获取锁，用于线程同步
        threadLock.acquire()
        print_time(self.name, self.counter, 3)
        # 释放锁，开启下一个线程
        threadLock.release()

def print_time(threadName, delay, counter):
    while counter:
        time.sleep(delay)
        print ("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1

threadLock = threading.Lock()
threads = []

# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()

# 添加线程到线程列表
threads.append(thread1)
threads.append(thread2)

# 等待所有线程完成
for t in threads:
    t.join()
print ("退出主线程")
执行以上程序，输出结果为：

开启线程： Thread-1
开启线程： Thread-2
Thread-1: Wed Apr  6 11:52:57 2016
Thread-1: Wed Apr  6 11:52:58 2016
Thread-1: Wed Apr  6 11:52:59 2016
Thread-2: Wed Apr  6 11:53:01 2016
Thread-2: Wed Apr  6 11:53:03 2016
Thread-2: Wed Apr  6 11:53:05 2016
退出主线程
```



