# day01 

## 1.开班

- 讲师：武沛齐

- 助教：晓强

- Python介绍

  ```
  优点：
  	- 简洁，100行代码实现，用Python10行。
  	- 类库齐全，“自然生长”第三方提供的包或类库非常多。
  缺点：
  	- 慢（GIL锁，Python在多线程情况下无法使用计算机多核优势）
  		- asyncio
  		- uvloop	
  		
  最后：程序慢？不是取决于编程语言，而是取决于程序员。
  ```

- 课程相关（线上）

  ```
  - 腾讯会议，9点30之前我会在群里发邀请码。
  - 腾讯文档，课堂交互。
  - 路飞学城，交作业（先注册）。
  ```

## 2.学前必备

### 2.1 typora

markdown格式语法，在任何平台写笔记。

typora软件，本地电脑上。

- 安装：window、mac

- 基本语法

  ```
  # 内容       -> 标题
  
  - 下下下      -> 列表
  1. xxx       -> 带序号的列表
  
  ​```python    -> 存放代码
  放代码
  ​```
  ```

- 图片配置
  <img src="assets/image-20200705102900917.png" alt="image-20200705102900917" style="zoom:25%;" />
  以后可以复制图片 + 截图，直接粘贴到笔记中。

### 2.2 编译器和解释器

![image-20200705110038631](assets/image-20200705110038631.png)

编译器，Go编译器、Java编译器。（非实时编译），假设：通过Go编写了1000代码，先编译器成某个文件，再讲编译好的文件交给计算机去执行。【快】【修改代码不方便】

- 写完了1000行代码
- 编译5分钟：编译成二进制文件。
- 计算机在运行二进制文件 3秒执行。 

解释器，Python解释器。(实时翻译)，假设：通过python编写了1000行代码，解释器会逐行执行。【慢】【修改代码方便】

- 写完代码1000行代码。
- 解释器去执行代码并转换成计算机能听懂的语言 3分钟。

### 2.3 编码相关

别人给你发了文档，别人电脑打开没问题，在我们的电脑打开出现 “乱码“。

- 计算机的底层本质上都是进行二进制的运算：010101010101
- 我们平时在电脑上任何文本等信息最终都会转换成二进制再操作（对照表）。

```go
我对照表 = 你的对照表(编码)
武   01111111 00011010 010110110
沛   01001111 10010000 001110100
齐   11111111 00000000 010101010
```

```
我对照表 != 你的对照表
武   01111111 00011010 010110110
沛   01001111 10010000 001110100
齐   11111111 00000000 010101010

你的对照表
武   01111111 11111000
沛   01001111 11111111
齐   11111111 11000011
```

举例：我写论文用utf-8编码保存，在内部会根据utf-8对照表将文本转换成二进制并保存到电脑上。

```
01111111 00011010 01011011 001001111 10010000 00111010 011111111 00000000 010101010
```

以后我再打开文件时，一定需要用utf-8编码打开，如果用其他编码打开那么就可能会造成乱码。

注意：文件以什么编码方式保存，那就用什么编码方式打开即可。



## 3.Python解释器安装

操作系统基本上：window & mac 。

### 3.1 下载解释器

建议大家使用：3.x （3.5+）

注意：目前对你而言装3.x的版本都是可以，但如果以后去公司一定要多加注意。

![image-20200705114244357](assets/image-20200705114244357.png)

### 3.2 安装

[https://pythonav.com/wiki/detail/1/1/#3.1%20%E5%AE%89%E8%A3%85CPython%E8%A7%A3%E9%87%8A%E5%99%A8](https://pythonav.com/wiki/detail/1/1/#3.1 安装CPython解释器)

### 3.3 写个代码运行

#### 3.3.1 新建文件（文本文档）

在自己的电脑的某个目录创建一个 .py 后缀的文件。

s29.py

```python
print("叫爸爸")
```

#### 3.3.2 运行

用刚才安装好的Python解释器去运行 s29.py 的文件。

- 打开终端

  - mac
    <img src="assets/image-20200705115055734.png" alt="image-20200705115055734" style="zoom:50%;" />

  - win

    ![image-20200705115131287](assets/image-20200705115131287.png)

- 用解释器去运行代码

  - mac

    ```go
    Python的安装目录： /Library/Frameworks/Python.framework/Versions/3.8/
    Python解释器： /Library/Frameworks/Python.framework/Versions/3.8/bin/python3.8
    
    >>> 解释器路径 代码路径
    /Library/Frameworks/Python.framework/Versions/3.8/bin/python3.8  /Users/wupeiqi/s19.py
    ```

  - win

    ```python
    Python的安装目录： C:\Python36
    Python的解释器： C:\Python36\python.exe
        
    >>> "C:\Python36 \python.exe" D:\s29.py
    ```

  

  ## 小结

  1. Python语言的优缺点。

  2. 编码相关：

     - 编码就是一个二进制和文字的对照表。
     - 一定要遵循 写 + 读 要使用同一种编码。

  3. 解释器和编译器

     - 解释器：Python、PHP、Ruby。
     - 编译型：C、C++、Golang、" Java "。

     注意：学习任何一门编程语言本质安装编译器或解释器 + 学习语法并写代码 => 编译器或解释器运行代码

  4. 安装Python解释器

     - 版本

       - 3.x，建议
       - 2.x，不建议

       注意：自己电脑安装那个版本都行，公司开发必须按照公司的版本。

     - 一定要知道自己把Python解释器安装到了那些目录？

  5. 解释器去运行Python代码

     - 打开终端

     - 在终端输入

       ```
       解释器路径 代码文件路径
       ```

       ```
       mac: /Library/Frameworks/Python.framework/Versions/bin/python3.8
       win: C:\python36\python.exe
       ```

  

  问题：请问以后我再去编写其他python代码后，想要运行是不是每次都要。

  ```
  /Library/Frameworks/Python.framework/Versions/bin/python3.8   s99.py
  ```

  

  

## 4. 环境变量

让你在计算机中存储一个路径，以后再去这个路径下找内容时，不需要再去写前面的路径。

```
C:\Python36\python.exe D:\s29.py
```

在python开发中如果将Python安装目录添加到环境变量，以后再去运行python解释器时，就可以如下：

```
python D:\s29.py
```

### 4.1 win下设置环境变量

![image-20200705142057644](assets/image-20200705142057644.png)



![image-20200705142151798](assets/image-20200705142151798.png)

![image-20200705142449648](assets/image-20200705142449648.png)



注意事项：配置环境变量之后一定要重新打开一下终端才能生效。



### 4.2 mac下环境变量设置

去修改当前登录用户下的 `~/.bash_profile`一个文件。

```
# Setting PATH for Python 3.8
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.8/bin:${PATH}"
export PATH
```

- 第一步：执行vim命令
  ![image-20200705142957415](assets/image-20200705142957415.png)

- 第二步：将内容粘贴到文件中

  ![image-20200705143109562](assets/image-20200705143109562.png)

  

- 第三步：保存
  - 按 esc
  - 按 :wq 

当设置上环境变量之后，再去找python解释器就非常方便了。 

扩展：

- 添加变量，以后方便找到解释器（MySQL）。
- 解释器安装时，Python默认设置了环境变量。

​	

## 5.运行python方式

### 5.1 代码写入文件

当你把代码写入文件之后，用解释器 + 代码路径就可以了。

```python
python C:\s20.py
```

### 5.2 交互式

一般用于平时写简单python语法和测试用。 

![image-20200705144806004](assets/image-20200705144806004.png)



## 6.IDE

基于IDE（集成开发环境）来进行Python程序的开发，大大的提高我们开发效率。

- eclipce，开发Java程序。
- pycharm，写python程序最好用的工具（专业收费、社区版免费）。
- vscode，微软开发免费的编辑器 + 第三方组件 = > 比较好用的工具。

### 6.1 下载安装

![image-20200705145809543](assets/image-20200705145809543.png)



### 6.2 试用

- 试用30天
- 支持正版，可以去买。
- 网络上找注册码（不好用）
- 破解
  <img src="assets/image-20200705150050598.png" alt="image-20200705150050598" style="zoom:50%;" />



### 6.3 Pycharm开发py代码

- 创建文件夹（项目）![image-20200705152707438](assets/image-20200705152707438.png)
  
- 找到解释器路径
  ![image-20200705153046475](assets/image-20200705153046475.png)
  注意：创建项目之后，项目（文件件）和解释器关联起来了。



- 创建python文件

  ![image-20200705153329994](assets/image-20200705153329994.png)

- 编写代码并运行
  ![image-20200705153528894](assets/image-20200705153528894.png)
  ![image-20200705153659502](assets/image-20200705153659502.png)



### 6.4 Pycharm配置

如果是windows系统，在左上角找到 【File】-> 【settings】进行配置。

#### 6.4.1 字体大小

![image-20200705154002453](assets/image-20200705154002453.png)



#### 6.4.2 编码

![image-20200705154222718](assets/image-20200705154222718.png)



#### 6.4.3 解释器

![image-20200705154615528](assets/image-20200705154615528.png)



## 7.python默认解释器编码

```python
# -*- coding:utf-8 -*- 

print("Hello")
```

在Python3之后，都可以不带这个解释器的头部 `# -*- coding:utf-8 -*- `

Python的版本一般有两大类：

- 2.x，python解释器默认使用ascii编码（只包含字母、数字、英文标点）

  s1.py

  ```python
  print("alex 叫爸爸") # 报错
  print("alex dsb") # 不报错
  ```

  当Python解释器运行：`python2.7 s1.py`

  s11.py

  ```python
  # -*- coding:utf-8 -*- 
  
  print("alex 叫爸爸") # 不报错
  print("alex dsb") # 不报错
  ```

  当Python解释器运行：`python2.7 s1.py`

- 3.x，python解释器默认使用utf-8编码（所有文字都可以包含）
  s2.py

  ```python
  print("alex 叫爸爸") # 不报错
  print("alex dsb") # 不报错
  ```

  当Python解释器运行：`python3.8 s2.py`

注意：文件存储编码需要是utf-8，python解释器是utf-8编码。



扩展，如果你的程序想不是用utf-8编码，换成另外一种编码。

- 文件存储：gbk编码

- 文件头：python解释器改成gbk编码

  ```python
  # -*- coding:gbk -*- 
  
  print("alex 叫爸爸") # 不报错
  print("alex dsb") # 不报错
  ```



结论：以后在Python3开发时，不需要再加编码头了。



## 8.输出

```python
# 1. 输出并在末尾添加换行符（输出）
print("alex sb")
print("alex sb")

# 2. 去掉末尾默认添加的换行符
print("alex db", end="")
print("alex db", end="")

# 3. 让print输入多个值
print("alex", "eric", "tony")
print("alex eric tony")
```



## 9.初识数据类型

- 小时候学中文，曾经学过：数字、汉字、词语、成语、文言文，写作文或写文章，对文章进行评分。
- 现在学Python，学习各种各样的数据类型    ，写程序，程序交给解释器去运行。



### 9.1 整型

就是我们在汉语中常说的整数，在程序中这种类型用于表示：年龄、大小、尺寸...

```python
# 创建整型 666，并使用并使用print输出
print(666)

# 计算 2 加 10 的结果，并使用print输出
v1 = 2 + 10
print(v1)

print( 2+10 )

# 计算 2 乘以 10 的结果，并使用print输出
print( 2*10 )

# 计算 10 除以 2 的结果，并使用print输出
print( 10/2 )

# 计算 10 除以 3 得的余数，并使用print输出
print( 12%3 )
# 扩展：可以基于求余来判断一个整数是否是奇数、偶数
# print( 12%2 )
# print( 11%2 )

# 计算 2 的 4 次方，并使用print输出
print( 2**4 )
```

### 9.2 字符类型

一般在程序中用于表示文本信息，例如：姓名、女优、地址。

```python
"武沛齐"
'武沛齐'

"武沛'齐"
'武沛"齐'
```

```python
# 创建字符串"武沛齐"，并使用print输出
print("武沛齐")

# 创建字符串 "中国北京昌平区"，并使用print输出
print("中国北京昌平区")

# 创建字符串 "我是谁？我是永远都得不到的爸爸呀！"，并使用print输出
print( "我是谁？我是永远都得不到的爸爸呀！" )
```

```python
# 字符串拼接（相加）
print( "alex" + "你是金角大王吧" )

# 字符串拼接（相乘）
print("alex" + "alex" + "alex" + "alex")
print("alex" * 4)
```

注意事项：整型和整型自己可以相互加减乘除，字符串和字符串只能自己相加（字符串相乘例外）。

### 练习题

```python
print( "alex" + "sb" )
print( "alex" + 'db' )
print( 10 + 10 )
print( 10 + "alex" ) # 错误
print( "2" + '2' ) # 结果："22"
print( 2 + 2 )     # 结果：4
```

### 9.3 布尔类型

真True、假False。

```python
1 > 2 
1 == 1
```

```python
print(True)  # 真
print(False)  # 假

print( 1 > 2 )
print( 11 > 2 )
print( 1 == 1 )
print( 1 != 1 )
print( 1 >= 1 )

print( "alex" == "sb" )
print( "alex" == "alex" )
```

```python
name = input("请输入用户名：")

if name == "alex":
    print("大屌丝")
else:
    print("小崽子")
```



### 9.4 数据类型转换

#### 9.4.1 转换为整型【 int(其他)】

- 字符串转整型

  ```python
  "asdf"    98989     -> 报错
  "109"     int("109")   109
  ```

  ```python
  print("10" + "10")  # 1010
  print(10 + 10)  # 20
  print(10 + int("666"))  # 676
  ```

- 布尔值转整型

  ```python
  True
  False 
  ```

  ```python
  print(True)
  print(False)
  
  print( int(True) )  # 1
  print( int(False) ) # 0
  
  print( int(True) + 5 )  # 6
  print( int(False) + 5 ) # 5
  ```

  

#### 9.4.2 转换为字符串【str(其他) 】

- 整型转换为字符串

  ```python
  19       str(19)     "19"
  ```

  ```python
  print("10" + "10") # 1010
  print(10 + 10) # 20
  print(  str(10) + str(10)  ) # 1010
  ```

- 布尔类型转换为字符串

  ```python
  True
  False 
  ```

  ```python
  print(str(True) + "ub")
  print(str(False) + "db")
  print(str(1 > 3) + "db")
  ```

  

#### 9.4.3 转换为布尔值【bool(其他)】

- 整型转换为布尔值

  ```python
  1       True
  2       True
  -1      True
  0       True
  ```

  ```python
  print(  bool(9)  ) # True
  print(  bool(-2)  ) # True
  print(  bool(1)  ) # True
  print(  bool(0)  ) # False
  
  注意：只有0会转换为False，其他都是True
  ```

- 字符串转换为布尔值

  ```python
  "alex"    bool("alex")    True
  "武沛齐"   bool("武沛齐")    True
  ""        bool("")       False
  " "       bool(" ")       True
  "999"     bool("999")    True
  "0"       bool("0")    True
  ```

  

### 练习题

1. 计算整型50乘以10再除以5的商并使用print输出。

   ```python
   print(50*10/5)
   ```

2. 判断整型8是否大于10的结果并使用print输出。

   ```python
   print( 8>10)
   ```

3. 计算整型30除以2得到的余数并使用print输出。

   ```
   print( 30 % 2 )
   ```

4. 使用字符串乘法实现 把字符串”我爱我的祖国”创建三遍并拼接起来最终使用print输出。

   ```python
   print( "我爱我的祖国" * 3 )
   ```

5. 判断 字符串”wupeiqi”和”alex”是否相等的结果并使用print输出。

   ```python
   print( "wupeiqi" == "alex" )
   ```

6. 判断 整型666和整型666是否相等的结果并使用print输出。

   ```python
   print( 666==666)
   ```

7. 判断 字符串”666”和整型666是否相等的结果并使用print输出。

   ```python
   print( 666 == "666" )
   ```

8. 看代码写结果（禁止运行代码）：

   ```python
   print( int("100")*3 ) # 300
   print( int("123") + int("88") ) # 211
   print( str(111) + str(222) ) # 111222
   print( str(111)*3 ) # 111111111
   print( int("8") > 7 ) # True
   print( str(111) == 111 ) # False
   print( bool(-1) ) # True
   print( bool(0) ) # False
   print( bool("") ) # False 
   print( bool("你好") ) # True
   print( True == True) # True
   print( True == False) # False
   print( bool("") == bool(0) ) True
   ```

注意：类型转换不是改变原来值，实际在底层是新创建了一个值。例如有整数注意：类型转换不是改变原来值，而是新创建了一个新的值。例如有整数 6 ，然后使用 str(6) 转化了一下得到 “6”,实际上这个字符串”6”是依据整数6新创建的。

## 10.变量

变量，其实就是我们生活中起别名和外号，让变量名指向某个值，格式为： 【变量名 = 值】，以后可以通过变量名来操作其对应的值。例如：

```python
age = 18
length = 20
data = age + length

name = "武沛齐"
email = "xxx@live.com"
message = name + "的邮箱是" + email 

flag = 1 > 18
```

### 10.1 变量名

三个要求：

- 变量只能包含：字母、数字、下划线

- 数字不能开头

- 不能使用Python内置的关键字。

  *[‘and’, ‘as’, ‘assert’, ‘break’, ‘class’, ‘continue’, ‘def’, ‘del’, ‘elif’, ‘else’, ‘except’, ‘exec’, ‘finally’, ‘for’, ‘from’, ‘global’, ‘if’, ‘import’, ‘in’, ‘is’, ‘lambda’, ‘not’, ‘or’, ‘pass’, ‘print’, ‘raise’, ‘return’, ‘try’, ‘while’, ‘with’, ‘yield’]*

两个建议（可以不遵循，不专业）：

- 多单词表示的变量名都是通过下划线+小写拼接

  ```python
  user_name
  oldboy_user_age = 18
  ```

- 见名知意

  ```
  age = 18
  size = 99
  ```

### 练习题

```python
name = "吉诺比利"
name0 = "帕克"
name_1 = "邓肯"
_coach = "波波维奇"
_ = "卡哇伊"
1_year = "1990"  # 错误
year_1_ = "1990"
_1_year = "1990"
nba-team = "马刺" # 错误
new*name = "伦纳德" # 错误
```

### 综合小结

```python
name = "alex"
age = 18

data = name + str(18)
print(data) # alex18
```

### 10.2 内存指向

[https://pythonav.com/wiki/detail/1/79/#5.2%20%E5%86%85%E5%AD%98%E6%8C%87%E5%90%91](https://pythonav.com/wiki/detail/1/79/#5.2 内存指向)



## 11.输入

```python
# 第一步：执行 input('请输入用户名：') ，输出区域 会提示用户来输入"请输入用户名"
# 第二步：在下方任意输入，输入之后点击回车；之后会讲输入的内容赋值给name变量，name就代指你输入的内容
name = input("请输入用户名--->")  # name = "alex"

# 第三步：输出name变量代指的值，即：输出刚才输入的内容
message = name + "大帅比"

print(message)
```

注意：通过input用户输入的值永远是字符串类型。

```python
n1 = input("请输入一个数字：")
n2 = input("请再输入一个数字：")

n3 = n1 + n2
print(n3) # 1112
```

```python
n1 = input("请输入一个数字：")
n2 = input("请再输入一个数字：")

n3 = int(n1) + int(n2)
print(n3) # 23
```



## 12.条件语句

### 12.1 基本条件语句

```python
if 条件 :
	条件成立则执行这个缩进中的代码
else:
    条件不成立，则执行这个缩进中的代码
```

```python
name = input("请输入用户名:")

if name == "alex":
    print("登录成功")
else:
    print("登录失败")
```

```python
name = input("请输入用户名:")
password = input("请输入密码:")

print("开始")

if name == "alex" and password == "123":
    print("登录成功")
    print("登录成功")
    print("登录成功")
    print("登录成功")
    print("登录成功")
    print("登录成功")
else:
    print("用户名或密码错误")
    print("用户名或密码错误")

print("结束")
```





### 12.3 条件语句的结构

```python
if 条件:
    ...
else:
    ...
```

```python
if 条件:
    ...
```

```python
if 条件A:
    条件A成立则执行此处代码
elif 条件B:
    条件A不成立，条件B成立，则执行此处代码
elif 条件C:
    条件A/B都不成立，条件C成立，则执行此处代码
...
else:
    以上条件都不成立，则执行此处代码（如果没有功能，也可以把else省略）
```

[https://pythonav.com/wiki/detail/1/79/#8.%20%E6%9D%A1%E4%BB%B6%E8%AF%AD%E5%8F%A5](https://pythonav.com/wiki/detail/1/79/#8. 条件语句)



### 12.3 嵌套

```python
if 条件A:
    ....
    if 条件B:
        ...
	else:
        ...
else:
    ....
```

示例：模拟10086客服提醒。

```python
print("欢迎致电10086，我们提供了如下服务： 1.话费相关；2.业务办理；3.人工服务")

n1 = input("请选择要咨询的服务序号") # 1/2/3
number = int(n1)

if number == 1:
    cost = input("查询花费请按1；交话费请按2；")
    if cost == "1":
        print("话费剩余100元")
    elif cost == "2":
        print("缴纳话费10000元成功")
    else:
        print("输入错误")
elif number == 2:
    cost = input("宽带业务请按1；协议款余额请按2；")
    if cost == "1":
        print("已免费给你家装宽带了")
    elif cost == "2":
        print("协议款余额为0")
    else:
        print("输入错误")
elif number == 3:
    print("客服007号为您服务")
else:
    print("序号输入错误，没有相关服务器")
```



## 今日总结

1. 今日涉及知识点罗列出来
   - 自己罗列
   - 参考笔记
   - 看视频（非常浪费时间）
2. 练习题
   [https://pythonav.com/wiki/detail/1/79/#7.2%20%E6%9D%A1%E4%BB%B6%E8%AF%AD%E5%8F%A5%E5%B5%8C%E5%A5%97](https://pythonav.com/wiki/detail/1/79/#7.2 条件语句嵌套)
3. 作业（今晚发到群里）





































































































































































































































































































































































































`















