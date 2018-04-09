

1练习
#强化
**R-1.1** Write a short Python function, is multiple(n, m), that takes two integer values and returns True if n is a multiple of m, that is, n = mi for some integer i, and False otherwise. 

写一个短的python函数，is_multiple（m，n）并且如果n是m的倍数返回True，否则返回False。

```
def is_multiple(m,n):
	if n%m == 0 :
		return True
	else:
		return False
```

**R-1.2** Write a short Python function, is even(k), that takes an integer value and returns True if k is even, and False otherwise. However, your function cannot use the multiplication, modulo, or division operators. 
写一个短的python函数，is_even（k），如果k是偶数返回True，否则返回False，但是函数不能使用乘法、除法或者模等操作。

```
def is_even(k):
	if k%2 == 0:
		return True
	else :
		return False
```

**R-1.3** Write a short Python function, minmax(data), that takes a sequence of one or more numbers, and returns the smallest and largest numbers, in the form of a tuple of length two. Do not use the built-in functions min or max in implementing your solution. 
写一个短的python函数，minmax(data)，给一个或者多个数字序列，返回最大或者最小的值，值在长度为2的元组的值。不能使用内置的min或max函数。

```
def minmax(data):
	a = length(data)
	max1 = data[0]
	min1 = data[0]
	for i in range(a):
		if max1 <data[i]:
			max1 = data[i]
		if min1 > data[i]:
			min1 = data[i]
	return max1,min1
```

**R-1.4** Write a short Python function that takes a positive integer n and returns the sum of the squares of all the positive integers smaller than n 
写一个短的python函数，取一个正整数n返回所有小于n的数的平方的和。

```
def factorial(n):
	value = 1
	a = n
	while a > 1:
		a = a-1
		value = value*a
	return value
```

**R-1.5** Give a single command that computes the sum from Exercise R-1.4, relying on Python’s comprehension syntax and the built-in sum function. 
给一个单独的命令计算1.4练习的和，只依靠python的语法和内置函数。

```
x = 4
value = sum([i**2 for i in range(x)])
```

**R-1.6** Write a short Python function that takes a positive integer n and returns the sum of the squares of all the odd positive integers smaller than n.

写一个短的python函数，给一个正整数n，返回所有小于n的奇数的平方和。

```
def factorial(n):
	value = 0
	a = n
	while a > 1:
		a = a-1
		if a%2 != 0:
			value = value+a**2
	return value
```

**R-1.7** Give a single command that computes the sum from Exercise R-1.6, relying on Python’s comprehension syntax and the built-in sum function. 
给一个单独的命令计算1.4练习的和，只依靠python的语法和内置函数。

```
x = 4
value = sum([i**2 for i in range(x) if i%2 != 0])
```

**R-1.8** Python allows negative integers to be used as indices into a sequence,such as a string. If string s has length n, and expression s[k] is used for index -n ≤ k < 0, what is the equivalent index j ≥ 0 such that s[j] references the same element? 
Python允许负数在序列中作为索引，例如：字符串。如果字符串s长度为n，表达式s[k]用于索引-n=<k<0,那么索引值j>0时，与s[j]相等的元素是什么？

```
s[j] == s[j-n]
```
**R-1.9** What parameters should be sent to the range constructor, to produce a range with values 50, 60, 70, 80?
应该将哪些参数发送给范围构造函数，以生成一个值为50,60,70,80的范围？

```
#参数范围为50-90
#参数的取值为10个单位。
range(50,90,10)
```
**R-1.10** What parameters should be sent to the range constructor, to produce a range with values 8, 6, 4, 2, 0, −2, −4, −6, −8?
应该将哪些参数发送给范围构造函数，以生成一个值为的范围8, 6, 4, 2, 0, −2, −4, −6, −8？
```
#参数范围是8，-10
#参数的取值为-2各单位
range(8,-10,-2)
```
**R-1.11** Demonstrate how to use Python’s list comprehension syntax to produce the list [1, 2, 4, 8, 16, 32, 64, 128, 256].
展示一下怎样使用列表语法去产生列表 [1, 2, 4, 8, 16, 32, 64, 128, 256]。
```
list1 = [2**i for i in range(9)]
print(list1)
```
**R-1.12** Python’s random module includes a function choice(data) that returns a random element from a non-empty sequence. The random module includes a more basic function randrange, with parameterization similar to the built-in range function, that return a random choice from the given range. Using only the randrange function, implement your own version of the choice function.
Python的random模块有一个choice（data）函数，能从一个非空序列返回一个随机元素。这个random模块包含了一个更基础的randrange函数，参数化与内置函数很相似，能从给的序列中返回一个随机选择。仅仅使用这个randrange函数完成你自己的选择函数。
```
data = [1,3,7,9,10,15]
import random
def minmax(data):
	a = len(data)
	max1 = data[0]
	min1 = data[0]
	for i in range(a):
		if max1 <data[i]:
			max1 = data[i]
		if min1 > data[i]:
			min1 = data[i]
	return max1,min1
def choice(data):
	max1,min1 = minmax(data)
	while True :
		a = random.randrange(min1,max1+1)
		if a in data:
			break
	return a 
print(choice(data))
```
#创造
**C-1.13** Write a pseudo-code description of a function that reverses a list of n integers, so that the numbers are listed in the opposite order than they were before, and compare this method to an equivalent Python function for doing the same thing.
写一个转置n的整数的列表函数的伪随机代码，让这个列表顺序与原来相反。对比这个方法与python函数的方法。
```
data = [1,2,3,4,5,6,7,8,9,0]
data1 = [i for i in data]

for i in range(len(data)):
	data1[len(data)-i-1] = data[i]

data.reverse()
data2 = data
if data1 == data2:
	print('yes')
else:
	print('no')
```
在这个过程中遇到一个问题，就是``` data2 = data.reverse() ```
这个方法是错的，因为reverse（）他操作的对象上data本身，所以此时data2返回的是一个None值。

**C-1.14** Write a short Python function that takes a sequence of integer values and determines if there is a distinct pair of numbers in the sequence whose product is odd.
写一个短的python函数。给一个整数值序列，请你判断，是否有两个不同的数，他们的乘积是奇数。
```
data = [1,2,3,4,5,6,7,8,9,0]
c = 0
for i in range(len(data)-1):
	a = data[i]
	for j in range(i+1,len(data)):
		b = data[j]
		if (a*b)%2 !=0:
			c = 1
			break
	if c == 1:
		print('yes')
		break

```
**C-1.15** Write a Python function that takes a sequence of numbers and determines
if all the numbers are different from each other (that is, they are distinct).
写一个python函数，去确定所有的数之间相互都是不同的：
```
data = [1,2,3,4,5,6,7,8,9,9]
c = 0
for i in range(len(data)-1):
	a = data[i]
	for j in range(i+1,len(data)):
		b = data[j]
		if a == b :
			c = 1
			break
	if c == 1:
		print('yes')
		break
```
**C-1.16** In our implementation of the scale function (page 25), the body of the loop executes the command data[j] = factor. We have discussed that numeric types are immutable, and that use of the = operator in this context causes the creation of a new instance (not the mutation of an existing instance). How is it still possible, then, that our implementation of scale changes the actual parameter sent by the caller?
在25页scale函数的实现中，循环体执行了命令```data[j] = factor ```  我们讨论数字类型是不可变的，在这种情况下我们使用=运算符产生了一个新的实例。不是现有实例的变化。那么，我们的scale如何实现改变调用者发送的实际参数呢？
```
data = [1,2,3,4,5,6,7,8,9,9]
factor = 3
def scale(data, factor):
	for i in range(len(data)):
		data.insert(i,data[i+i]*3)
	for i in range(int(len(data)/2)):
		data.pop()
scale(data,factor)
print(data)

```
**C-1.17** Had we implemented the scale function (page 25) as follows, does it work properly?
```
def scale(data, factor):
	for val in data:
		val *= factor
```
Explain why or why not.
我们如果按照这个方法完成scale函数，她能正常工作吗？解释为什么：
答：不能正常工作；
		我感觉是创建了一个新的标示符，标示符对应的值会重新创建，而不是改变list的内容。

**C-1.18** Demonstrate how to use Python’s list comprehension syntax to produce
the list [0, 2, 6, 12, 20, 30, 42, 56, 72, 90].
展示一下，怎样用python列表语法生成一个 [0, 2, 6, 12, 20, 30, 42, 56, 72, 90]的列表。
```

lst = [2*sum(i for i in range(x))  for x in range(1,11)]
print(lst)
```
**C-1.19** Demonstrate how to use Python’s list comprehension syntax to produce the list [ a , b , c , ..., z ], but without having to type all 26 such characters literally.
展示一下，怎样用列表语法生成一个[ a , b , c , ..., z ]的列表，但是不能输入直接输入这26个字母。
```
lst = [chr(x)  for x in range(97,123)]
print(lst)
```
**C-1.20** Python’s random module includes a function shuffle(data) that accepts a list of elements and randomly reorders the elements so that each possible order occurs with equal probability. The random module includes a more basic function randint(a, b) that returns a uniformly random integer from a to b (including both endpoints). Using only the randint function, implement your own version of the shuffle function.
python的随机模块包含了一个shuffle（data）函数，接受一个元素列表，并且随机的排序列表元素的位置，是每一种出现的可能想等。这个随机模块包含一个更基础的randint（a，b）他随机返回一个a与b之间的值，使用基础的函数完成我自己的shuffle函数。

```
import random
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 15]


def minmax(data):
    a = len(data)
    max1 = data[0]
    min1 = data[0]
    for i in range(a):
        if max1 < data[i]:
            max1 = data[i]
        if min1 > data[i]:
            min1 = data[i]
    return max1, min1


def shuffle(data):
	max1, min1 = minmax(data)
	for i in range(len(data)):
		while True:
			a =random.randint(min1,max1)
			if a in data:
				data.remove(a)
				data.append(a)
				break
shuffle(data)
print(data)
```

**C-1.21** Write a Python program that repeatedly reads lines from standard input until an EOFError is raised, and then outputs those lines in reverse order (a user can indicate end of input by typing ctrl-D).
写一个程序，重复读取标准输入的行数，直到出现一个EOFError，然后以相反的循序输出这些值（用户可以通过输入ctrl-D来表示输入结束）
```
def numInput(numList):
    inpu = input("please input a num:" )
    if inpu!='ctrl-D':
        num = inpu
        numList.append(num)
        numInput(numList)
    else:
        for i in numList:
            print (i)
        return True

numInput(numList=[])
```
**C-1.22** Write a short Python program that takes two arrays a and b of length n storing int values, and returns the dot product of a and b. That is, it returns an array c of length n such that c[i] = a[i] · b[i], for i = 0,...,n− 1.
写一个短的python程序，给两个长度为n的整数数组，返回两个a和b的点积，返回数组c的长度也为n，c[i] = a[i] · b[i], for i = 0,...,n− 1.
```
a = [1,2,3,4,5,6]
b = [7,8,9,10,11,12]
c = []
for i in range(len(a)):
	d = a[i]*b[i]
	c.append(d)
print(c)
```

**C-1.23** Give an example of a Python code fragment that attempts to write an element to a list based on an index that may be out of bounds. If that index is out of bounds, the program should catch the exception that results, and print the following error message:  
“Don’t try buffer overflow attacks in Python!”
给一个python代码片段的例子，尝试写一个基于索引给列表写一个元素这个索引可能超出边界，如果超出边界这个索引可能会捕获一个异常结果，并且打印异常信息：“Don’t try buffer overflow attacks in Python!”
```
def numInput(numList, dat):
    inpu = input("请输入索引地址:")
    inpu2 = input("请输入想输入的信息：")
    try:
    	print(inpu)
    	num = int(inpu)
    	dat.insert(inpu,inpu2)
    	numInput(numList)
    except ValueError:
        print('invalid value')
        numInput(numInput, dat)
    except:
        print("Don't try buffer overflow attacks in Python!")
        numInput(numInput, dat)


data = [1, 3, 7, 9, 10, 15]
numList=[]
numInput(numList,  data)
```
这个程序不知道为什么一直执行错误。
**C-1.24** Write a short Python function that counts the number of vowels in a given character string.
写一个短的python函数然后统计给定的单词的元音字母的个数。
```
a = input('随便写个单词：')
num = 0

b = str(a)
for i in range(len(b)):
	if b[i] in ['a','e','i','o','u']:
		num += 1
print(num)
```
**C-1.25** Write a short Python function that takes a string s, representing a sentence, and returns a copy of the string with all punctuation removed. For example, if given the string "Let s try, Mike.", this function would return "Lets try Mike".
写一个短的python函数，给一个字符串s来代表一个句子，然后返回一个去掉标点的字符串副本，例如给你一个"Let s try, Mike."然后返回一个"Lets try Mike".
```
import string
a = "Let's try, Mike."
delset = string.punctuation
b = a.translate(delset)
print(b)
```
不知道为什么这个方法不好使，头疼！

**C-1.26** Write a short program that takes as input three integers, a, b, and c, from the console and determines if they can be used in a correct arithmetic formula (in the given order), like “a+ b = c,” “a = b− c,” or “a∗ b = c.”
写一个短的程序，输入三个整数a，b，c。从控制台确定是否可以使用正确的算术公式（按照给定的顺序），如“a+b=c”、“a=b-c”或“a* b=c”。
```
a = 3
b = 4
c = 5
if a+b == c:
	print('yes')
elif b-c == a:
	print('yes')
elif a*b == c:
	print('yes')
else:
	print('no')
```
**C-1.27** In Section 1.8, we provided three different implementations of a generator that computes factors of a given integer. The third of those implementations, from page 41, was the most efficient, but we noted that it did not yield the factors in increasing order. Modify the generator so that it reports factors in increasing order, while maintaining its general performance advantages.
在1.8节中我们完成了三个不同的计算整数因数的生成器，这第41页的第三个完成的是最高效，但是我们注意到他并没有增加秩序的因数，修改生成器让他能在保持总体性能优势的同时 报告增加次序的因数。
```
def factors(n): # generator that computes factors
	k = 1
	while k*k < n: # while k < sqrt(n)
		if n % k == 0:
			yield k
			k += 1
		if k k == n: # special case if n is perfect square
			yield k
	while k k < n: # while k < sqrt(n)
		if n % k == 0:
			yield k//n
			k += 1
		
```
C-1.28 The p-norm of a vector v = (v1,v2,...,vn) in n-dimensional space is defined as 
![这里写图片描述](https://img-blog.csdn.net/20180323001212899?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2tsaW5naHVp/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
For the special case of p = 2, this results in the traditional Euclidean norm, which represents the length of the vector. For example, the Euclidean norm of a two-dimensional vector with coordinates (4,3) has a Euclidean norm of √42 + 32 = √16+ 9 = √25 = 5. Give an implementation of a function named norm such that norm(v, p) returns the p-norm value of v and norm(v) returns the Euclidean norm of v. You may assume that v is a list of numbers.
一个向量的p范数，定义为：如图，对于特殊的的例子p=2时叫欧几里得范数，代表着向量的长度，例如：（4,3）的欧几里得范数为5，给一个函数命名为norm，norm（v，p）返回p-返回，norm（v）返回欧几里得范数，你应该假定v是列表。
```
def norm(v,p = 2):
	a = 0
	for i in v:
		a += i**p
	b = pow(a,1/p)
	return b

v = [1,34,6,4,3,23]
c = norm(v,3)
print(c)
```
#项目
**P-1.29** Write a Python program that outputs all possible strings formed by using the characters c , a , t , d , o , and g exactly once.
写一个程序输出只包含一次 c , a , t , d , o , 和 g所有可能的字符串。
```
import random
lst = ['c', 'a', 't', 'd', 'o', 'g']


def output_lst(lst):
    s = ''
    for i in lst:
        s = s + i
    return s


def factorial(n):
    value = 1
    a = n
    while a > 1:
        a = a - 1
        value = value * a
    return value


def output(lst, str_lst):
    while True:
        random.shuffle(lst)
        string = output_lst(lst)
        if string not in str_lst:
            str_lst.append(string)
        if len(str_lst) == factorial(len(lst)):
        	break
    return str_lst


str_lst = []
print(output(lst, str_lst))
```

**P-1.30** Write a Python program that can take a positive integer greater than 2 as input and write out the number of times one must repeatedly divide this number by 2 before getting a value less than 2.
写一个python程序，给一个比2大的正整数作为输入，并写出在得到小于2的值之前必须重复将该数字除以2的次数。
```
def write():
	n = 0
	a = int(input('随便输入一个数：'))
	if a > 2:
		while a > 2 or a == 2:
			a = a/2
			n = n+1
	else:
		print('输入的值小于2')
		write()
	return n

print(write())
```
**P-1.31** Write a Python program that can “make change.” Your program should take two numbers as input, one that is a monetary amount charged and the other that is a monetary amount given. It should then return the number of each kind of bill and coin to give back as change for the difference between the amount given and the amount charged. The values assigned to the bills and coins can be based on the monetary system of any current or former government. Try to design your program so that it returns as few bills and coins as possible.
写一个能“找钱 “的python程序，你的程序应该给两个值作为输入，一个是收的钱另一个是花的钱，他应该返回需要找钱的货币和硬币的数量，这个纸币和硬币可以基于当前任何一个国家的体系，尝试着设计一个尽可能少的货币和硬币的数量。
```
def make_change():
	money_type = [100,50,20,10,5,2,1,0.5,0.1]
	m = float(input('收款金额：'))
	n = float(input('应收金额：'))
	if m == n:
		print('不用找钱')
	elif m-n < 0.1 or m-n ==0.1:
		print('没法找钱')
	elif m > n:
		a = m-n
		for money in money_type:
			a = return_change(a,money)
	
def return_change(m,n):
	num = 0
	return_money = 0
	if m > n or m == n:
		num = m//n
		return_money = m-num*n
		b = str(n)
		c = int(num)
		print("找 %s元，%d张" % (b,c))
		return return_money
	else:
		return m


make_change()
```
**P-1.32** Write a Python program that can simulate a simple calculator, using the console as the exclusive input and output device. That is, each input to the calculator, be it a number, like 12.34 or 1034, or an operator, like + or =, can be done on a separate line. After each such input, you should output to the Python console what would be displayed on your calculator.
写一个像计算器一样的程序，使用这个控制器作为单独的输入和输出设备，计算器的每次输入一个数字像：12.34、1034或者一个运算符像+或者-，都可以在单独的一行中完成。然后在你的计算器中显示出来。 
```
def divide(x,y):
    #相除
    if y ==0:
        print('0不能做为分母')
        return
    else:
        return x/y

choice =input("请选择运算:\n+,相加\n-,相减\n*,相乘\n/,相除\n请输入运算(+/-/*//):")
num1 = float(input("请输入第一个数:"))
num2 = float(input("请输入第二个数:"))
if choice is '+':
    print("{}+{}={}".format(num1,num2,num1+num2))
elif choice is '-':
    print("{}-{}={}".format(num1,num2,num1-num2))
elif choice is '*':
    print("{}x{}={}".format(num1,num2,num1*num2))
elif choice is '/':
    print("{}/{}={}".format(num1,num2,divide(num1,num2)))
else:
    print("选择的运算为非法输入")
```
**P-1.33** Write a Python program that simulates a handheld calculator. Your program should process input from the Python console representing buttons that are “pushed,” and then output the contents of the screen after each operation is performed. Minimally, your calculator should be able to process the basic arithmetic operations and a reset/clear operation.
写一个python程序，类似于手持计算器，你的程序能正常的输入内容并在并目中显示出来每一步的操作，你的计算器能支持基本的算法和重置、清除的操作。
```
好吧，这个好像要弄什么东西，我还不太会。
```

**P-1.34** A common punishment for school children is to write out a sentence multiple times. Write a Python stand-alone program that will write out the following sentence one hundred times: “I will never spam my friends again.” Your program should number each of the sentences and it should make eight different random-looking typos.
老师对学生的一个常见的惩罚就是罚写，编写一个python的独立的程序，写“I will never spam my friends again.”一百遍，你的程序对着每一个句子进行编号他应该由八种不同的拼写错误。
```
def output(sentence):
	for i in range (100):
		if i % 12 == 0:
			sentence2 = sentence[:int(i*3/12)+2]+sentence[int(i*3/12+4):]
			print(sentence2)
		else:
			print(sentence)

sentence = 'I will never spam my friends again.'
output(sentence)

```

**P-1.35** The birthday paradox says that the probability that two people in a room will have the same birthday is more than half, provided n, the number of people in the room, is more than 23. This property is not really a paradox, but many people find it surprising. Design a Python program that can test this paradox by a series of experiments on randomly generated birthdays, which test this paradox for n = 5,10,15,20,... ,100.
生日驳论说，在同一个屋子里人数超过23人任意有两个人同一天生日的可能性过半，这并不真的是一个驳论，但许多人会觉得这很奇妙，设计一个python程序他可以随机生成一系列的生日来测试这个驳论，测n = 5,10,15,20,... ,100。
```
import random
n = [i*5 for i in range(1,21)]

def probability(person_num):
	count = 0
	for i in range(100):
		all_birthday = []
		for i in range(person_num):
			birthday = random.randint(1,366)
			if birthday not in all_birthday:
				all_birthday.append(birthday)
			else:
				count+=1
				break
	prob = count/100
	if prob>0.5:
		print("当人数为%d时，假设为真"% person_num)
	else:
		print("当人数为%d时，假设为假"% person_num)

for num in n:
	probability(num)
```
**P-1.36** Write a Python program that inputs a list of words, separated by white space, and outputs how many times each word appears in the list. You need not worry about efficiency at this point, however, as this topic is something that will be addressed later in this book.
写一个python程序，输入一个由空格分割的单词列表，并输出每个单词在列表中出现了多少次，你不需要担心效率，这个主题会在后面展开。
```
input1 = input('你想输入的一系列单词')
input2 = input1.split(' ')
myset = set(input2)
for word in myset:
	print('the %s has found  %d'% (word,input2.count(word)))
```



