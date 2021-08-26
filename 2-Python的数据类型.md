# 2-Python的数据类型

## Python的对象

#### 对象是什么

对象的概念类似于身份，人类是变量，高级动物就说对象。对象就说一类事物的共同特征。

+ 一切皆对象
+ 每个对象都有各自的属性和方法
+ 对象的特点就说它的属性，对象的功能就说它的方法

## 字符串操作及其他的内置函数

#### capitalize函数

+ 作用

  + 将字符串的首字母大写，其他部分变成小写

+ 用法

  newstr = string.capitalize()

  + 括号内什么都不用填写，无参数。

+ 注意事项

  + 只对第一个字母有效
  + 只对字母有效，其他字符无效
  + 首字母已经是大写，则无效。

  ```python
  # coding:utf-8
  
  name = 'xiao mu'
  info = 'Hello 小穆'
  _info = '小穆 hello'
  number_str = '1234'
  
  new_name = name.capitalize()
  new_info = info.capitalize()
  _new_info = _info.capitalize()
  new_number_str = number_str.capitalize()
  
  print(new_name)
  print(new_info)
  print(_new_info)
  print(new_number_str)
  ```

  

## 字符串的操作以及其他的内置函数

#### casefold 与lower

+ 将字符串全体小写

##### casefold与lower的用法

newstr = string.casefold()  -->括号内什么都不用写

newstr = string.lower() 	---> 括号内什么都不用写

##### casefold与lower的注意事项

+ 只对字符串中的字母有效

+ 已经是小写，则无效

+ lower()和casefold()方法使用空字符串是不会报错的。

+ 区别

  + lower()方法一直存在
  + casefold()新的用法，更多语种小写，比如德语。

  

  ```python
  # coding:utf-8
  
  message_en = "How are you? Xiaomu."
  message_cn = "你好啊，小穆。"
  message_mix = '你好啊，Xiaomu.'
  
  message_en_lower = message_en.lower()
  message_en_casefold = message_en.casefold()
  
  message_cn_lower = message_cn.lower()
  message_cn_casefold = message_cn.casefold()
  
  message_mix_lower = message_mix.lower()
  message_mix_casefold = message_mix.casefold()
  
  if __name__ == '__main__':
      print(message_en_lower)
      print(message_en_casefold)
      print("++++++++++")
      print(message_cn_lower)
      print(message_cn_casefold)
      print("++++++++++")
      print(message_mix_lower)
      print(message_mix_casefold)
  ```

#### upper()

##### upper()功能

  + 与lower()功能相反，将全体字符串大写

##### upper()用法

  + big_str = string.upper()
  + 参数：括号内什么都不用写

##### upper()注意事项

  + 只对字符串中的字母有效
  + 已经是大写，则无效。

#### swapcase()

##### swapcase()功能

  + 将字符串中的大小写进行转换，小写变大写，大写变小写。

##### swapcase()用法

  + newstr = string.swapcase()
  + 参数：括号内什么都不用填写

  ##### swapcase()注意事项

  + 只对字符串中的字母有效

  ```python
  # coding:utf-8
  
  info_one = 'Python Code Is Good.'
  info_two = 'PYTHON DJANGO FLASK.'
  info_three = 'python web so easy.'
  
  info_one_new = info_one.swapcase()
  info_two_new = info_two.swapcase()
  info_three_new = info_three.swapcase()
  
  if __name__ == '__main__':
  
      print(info_one_new)
      print(info_two_new)
      print(info_three_new)
  ```

  

#### zfill()

##### 功能

+ 为字符串定义长度，如不满足，缺少部分用0补齐。

##### 用法

+ newstr = string.zfill(width)
+ 参数：新字符串希望的宽度

##### 注意事项

+ 与字符串的字符无关

+ 如果定义的长度小于当前字符串长度，则不会发生变化。

  ```python
  # coding:utf-8
  
  heart = 'love'
  
  
  if __name__ == '__main__':
      print(' t  ' + heart)
      print('t     ' + heart)
      print(heart.zfill(10))
      print(heart.zfill(9))
      print(heart.zfill(8))
      print(heart.zfill(6))
      print(heart.zfill(4))
  ```

#### count()

##### count()功能

+ 返回当前字符串中某个成员出现的次数。

##### count()用法

+ inttype = string.count(item)
+ item:查询个数的元素

##### count()注意事项

+ 如果查询元素不存，则返回0。
+ 列表（元组）的操作以及其他的内置函数

#### startswith()和endswith()

##### 功能

+ startswith判断字符串开始位置是否是某成员
+ endswith判断字符串结尾是否是某成员。

##### 用法

+ string.startswith(item) ----> item:想查询匹配的元素，返回一个布尔值。
+ string.endswith(item) -----> item:想查询匹配的元素，返回一个布尔值。

#### find()和index()

##### 功能

+ find和indx都是返回想寻找某成员的位置。

##### 用法

+ string.find(item)    -------------->item:想查询的元素，返回一个整型。
+ string.index(item)------------------>item:想查询的元素，返回一个整型。
+ 字符串的位置都是从左向右，从0开始的。

##### 区别

+ find找不到元素，会返回-1
+ index找不到元素，会导致程序报错。

#### 字符串strip()函数

##### 功能

去掉字符串的指定元素，默认去掉空格。

##### 用法

+ newstr = string.strip(item)
+ 参数：括号里是传入想去掉的元素，可以不填。

##### strip扩展知识

+ 传入的元素如果不在开头或者结尾，则无效。
+ lstrip仅去掉开头的指定元素或者空格。
+ rstrip仅去掉字符串结尾的指定元素和空格。

#### replace()

##### 功能

+ 将字符串中old(旧元素)替换成new(新元素),并能指定替换的数量。

##### 用法

+ newstr = string.replace(old, new, max)
+ old:被替换的元素。
+ new:替代old的新元素。
+ max：可选，代表替换几个，默认全部替换全部匹配的old元素。



#### 字符串返回bool类型的函数集合

##### isspace()

##### 功能

判断字符串是否是由空格组成的字符串

##### 用法

+ booltype = string.issapace()              ---------->无参数可传，返回一个布尔值。
+ 由空格组成的字符串不是空字符串。

```python
IN：' '.sispace()
OUT: True
In: 'Hello xiaomu'.isspace()
OUT: False

```

#### istitle()

##### 功能

istitle()函数判断字符串是否是一个标题类型

##### 用法

+ booltype = String.istitle()         -------->无参数可传，返回一个布尔值。
+ 该函数只应用于英文

```python
IN: 'Hello Xiaomu'.istitle()
OUT: True
IN: 'hello xiaomu'.istitle()
OUT:False
```

#### isupper()与islower()

##### 功能

+ isupper判断字符串中的字母是否都是大写。
+ islower判断字符串中的字母是否都是小写。

##### 用法

+ booltype = string.isupper()		------>无参数可传，返回一个布尔类型。
+ booltype = string.islower()        -------->无参数可传，返回一个布尔类型
+ 只检测字符串里的字母，其他字符不做判断。



#### 字符串的编码格式

##### 什么是编码格式

谍战中的电报，编码格式类似，编码格式有以下特点：

+ 有一定规则的规则。
+ 使用了这种规则，我们就能知道传输的信息是什么。

##### 常见的编码格式

+ gbk中文编码
+ ascii英文编码

##### 通用的编码格式

+ utf-8是一种国际通用的编码格式。

#### 字符串格式化

##### 什么是格式化

+ 定义：一个固定的字符串中有部分元素是根据变量的值而改变的字符串。

##### 格式化的场景和目的

+ 发送邮件时
+ 发送短音时
+ APP上发送推送的时候

##### 格式化的三种方式

+ 根据类型定义的格式化

  + 字符串格式化使用操作符%来实现
  + 'my name is %s, my age is %s' %("James",33)
  + 格式化字符串与格式化变量之间用一个%连接，%两边有个空格。
  + 对应格式符的变量，变量和格式符按照一一对应，数量保持一致，超过1个格式化变量用小括号包裹。
+ 字符串格式化函数-format
  + string.format函数用来格式化字符串
  + 使用format的字符串主题使用{}大括号来替代格式符。
  + string.format(data,data,data....)

+ Python3.6加入的新格式化方案-f.strings
  + 定义一个变量
  + 字符串主体前加f符号
  + 需要格式化的位置使用{变量名}

```python
In: f'hello' {name}
OUT: 'hello 小穆'
```



#### 字符串格式化的符号们

##### 格式化符号

+ %s---->格式化字符串，通用类型。
+ %d----->格式化整型。
+ %f----->格式化浮点型。
+ %u----->格式化无符号整型（正整型）
+ %c----->格式化字符



#### 字符串的转义字符

##### 什么时转义字符

+ 字符要转成其他含义的功能，所以叫他转义字符。
+ \\ +字符

##### Python中的转义字符

| 符号 | 说明                                   |
| ---- | -------------------------------------- |
| \n   | 换行                                   |
| \t   | 横向制表符（可以认为是一个间隔符）     |
| \v   | 纵向制表符                             |
| \a   | 响铃                                   |
| \b   | 退格符，将光标迁移，覆盖（删除前一个） |
| \r   | 回车                                   |
| \f   | 翻页                                   |
| \\'  | 转义字符中的单引号                     |
| \\"  | 转义字符中的双引号                     |
| \\\\ | 转义斜杠                               |



##### 转义无效符

+ 在字符串中加r来讲字符串的转义字符无效化

  ```python
  IN: print(r'hello \f')
  OUT: hello \f
  ```

  







### 字典的操作以及其他的内置函数

