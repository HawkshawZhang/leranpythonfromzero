# 1-Python的数据类型

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

  

## 列表（元组）的操作及其它的内置函数

### 列表（元组）操作符

#### len在列表与元组上的使用

```python
names = ['xiaomu', 'James', 'xiaowang']
length = len(names)
print(length)
OUT:3
```

+ len函数可以计算出除数字类型外，所有数据类型的长度。

#### 列表（元组）之间累加和乘法

+ 累加累乘生成新的列表

```python
names = ['xiaomu', 'James', 'xiaowang']
new_names = names + names
print(new_names)
OUT:['xiaomu', 'James', 'xiaowang','xiaomu', 'James', 'xiaowang']
new_names = names * 2
print(new_names)
OUT:['xiaomu', 'James', 'xiaowang','xiaomu', 'James', 'xiaowang']
```

#### in 和 not in 在列表和元组的用法

+ in是判断某个成员（元素）是否在此数据结构中。
+ not in 就说判断某个成员（元素）是否不在此数据结构中。

### 列表的append()

#### 功能

+ 将一个元素添加到当前列表中。

#### 用法

+ list.append(new_item)
+ new_item:添加进列表中新的元素（成员）

```python
names = ['xiaomu']
names.append('James')
print(names)
OUT:['xiaomu', 'James']
```

#### 注意事项

+ append添加的元素添加至末尾
+ append函数是在原有列表上添加，不需要额外添加新的变量。

### 列表insert

#### 功能

+ 将一个元素添加到当前列表的指定位置中。

#### 用法

+ list_insert(index, new_iterm)
+ 参数： index ----> 新元素放到哪个位置， new_iterm----->添加的新元素（成员）

#### insert()与append()的区别

+ append智能添加到列表的结尾，而insert可以选择任何一个位置。
+ 如果insert传入的位置在列表中并不存在，则将新元素添加至列表结尾。
+ 字符串，元组，列表元素位置从0开始运算

### 列表中的count()

#### 功能

+ 返回当前列表中某个成员的个数。

#### 用法

+ inttype = list.count(iterm)
+ iterm:想要查询个数的元素

#### 注意事项

+ 如果查询的成员不存在，则返回0
+ 列表指挥检查完整元素是否存在，并计算内容的数量

### 列表的remove()

#### 功能

+ 删除列表中的某个元素

#### 用法

+ list.remove(item)
+ iterm:准备删除的列表元素

#### 注意事项

+ 如果删除的元素不存在，程序会直接报错。
+ 如果删除的元素有多个，只会删除第一个。
+ remove()不会返回一个新的列表，而在原先列表中对元素进行删除。

#### 内置函数del()

+ 将整个变量完全在内存中删除。

### 列表中的reverse()

#### 功能

+ 将当列表中的成员顺序颠倒

#### 使用方法

+ list.reverse()
+ 无参数传递

### Sort()函数

#### 功能

对当前列表按照一定规律进行排序

#### 用法

+ list.sort(key=None, reverse=False)
+ key -- 参数比较
+ reverse-- 排序规则，reverse=True降序，reverse=False升序（默认）

#### 注意事项

+ 列表中的元素类型必须相同，否则无法排序（报错)

### 列表的clear()

#### 功能

将当前列表所有数据清空

#### 用法

+ list.clear()----->该函数无参数，无返回值。

### 列表的copy()

#### 功能

将当前的列表复制一份相同的列表，新列表与旧列表内容相同，但内存空间不同。

#### 用法

+ list.copy()---->该函数无参数，返回一个一摸一样的列表。

#### copy与2次赋值的区别

+ 二次赋值与原始变量有相同的内存空间--->快捷方式
+ copy函数创建的新列表与原始列表不是一个内存空间，不同享数据变更。
+ copy()属于**浅拷贝**

#### 浅拷贝

+ 有一个列表a,列表a里的元素还是列表，对a进行拷贝出新列表b后，无论a还是b的内部的列表中的数据发生变化后，a、b之间都受到了影响。



```python
a = [[1,2,3],[5,6,7]]
b = a.copy(a)
b[0].append(10)
print(b)
print(a)
OUT: [[1,2,3,10],[5,6,7]]
OUT: [[1,2,3,10],[5,6,7]]
```

#### 深拷贝

+ 不仅仅是对第一层数据进行了copy,对深层数据也进行copy，原始变量和新变量完全不共享数据。类似于软连接和硬链接，归根到底共享内存地址。

```python
a = [[1,2,3],[5,6,7]]
b = a.deepcopy(a)
b[0].append(10)
print(b)
print(a)
OUT: [[1,2,3,10],[5,6,7]]
OUT: [[1,2,3],[5,6,7]]
```

### 列表的extend()

#### extend()的功能

将其他列表或者元组中的元素依次导入当前列表中。

#### extend()的用法

+ list.extend(iterable)
+ 参数：iterable:代表列表或者元组，该函数无返回值。

```python
students = ['james', 'xiaomu', 'xiaowang']
new_students = ['xiaogang', 'xiaohong']
students.extend(new_students)
print(students)
OUT: ['james', 'xiaomu', 'xiaowang','xiaogang', 'xiaohong']
```

### 列表的索引

#### 什么是索引

+ 字符串，列表，元组
+ 从最左边记录的位置就说索引
+ 索引用数字表示，起始从0开始
+ 最大索引是长度-1

#### 什么是切片

+ 索引是对单个元素进行访问，切片则是对一定范围的元素进行访问。
+ 切片是通过冒号在中括号内把相隔的两个索引查找出来 [0:10]
+ 切片的规则：左含，右不含。

#### 列表的索引，获取与修改

获取完整列表的方法

+ numbers[:]
+ numbers[0:]

除最后一个元素获取不到

+ numbers[:-1]

列表的反序

+ numbers[::-1]

通过步长，跳跃获取

+ numbers[0:8:2]

切片生成空列表

+ number[0:0]

通过索引修改列表

+ list[index] = new_item。
+ 数据的修改只能存在于索引范围内。
+ 列表无法通过添加新的索引的方式赋值
+ list.inde(item)

#### 通过pop()删除索引

+ 通过索引弹出（删除并获取）列表的元素。
+ list.pop(index)
+ index:删除列表的第几个索引



#### 通过del()删除索引

+ del list[index]
+ 直接删除，无返回值
+ 如果index不存在，则报错

#### 索引在元组中的特殊性

+ 可以和列表一样获取索引和切片索引
+ 元组函数index和列表用法完全一致
+ 无法通过索引修改与删除元素

### 列表之字符串切片

#### 字符串的索引与切片

+ 字符串索引规则和列表相同
+ 切片和索引的获取与列表相同
+ 无法通过索引修改和删除
+ 字符串不可修改

#### find()和inde()

+ 功能：获取元素的索引位置
+ string.index(item)  --->item:查询个数的元素，返回索引位置。
+ string.find(item)    ----->item:查询个数的元素，返回索引位置。
+ find()找不到返回-1，找到返回1

## 字典的操作以及其他的内置函数

### 字典中添加数据的方法

#### []处理法

+ 字典里没有索引
+ dict['name'] = 'James'
+ 添加或者修改，根据key是否存在决定

#### 字典内置函数update

+ 添加新的字典，新字典中的key和原字典相同，则key的value会被新字典value覆盖。
+ dict.update(new_dict) ------------> 该函数无返回值
+ new_dict: 新的字典

#### 字典的内置函数setdefault

+ 可以获取某个key的value，如果key不存在于字典中，将会添加key并将value设置为默认值。
+ dict.setdefault(key, value)
+ key ---> 需要获取的key, value ----> 如果key不存在，对应的key存入字典的默认值。

#### 注意事项

+ 字典中每个key都是唯一的
+ 字典中的数据量没有限制的
+ 字典中的value是可以是任何Python的内置数据类型的对象和自定义对象（函数）。

### 字典中的Keys函数

#### 功能

获取当前字典中所有的键（key)

#### 用法

+ dict.keys()  ------> 无需传参，返回一个key集合的伪列表
+ 伪列表，无法操作列表的所有功能。

```python
my_dict = {'name': 'James', 'age':33}
my_dict.keys()
OUT: dict_keys(['name', 'age'])
    
key_list = list(my_dict.keys())
print(key_list)
OUT:['name', 'age']
```

### 字典中的values()

#### 功能

获取字典中所有键值对中的值（value)

#### 用法

+ dict.values()         --------> 无须传参，返回一个value集合的伪列表

### 字典key的获取



#### []的获取方法

```python
my_dict = {'name': 'James', 'age': 33}
name = my_dict['name']
print(name)
OUT:	James
```

+ 字典+中括号内传key，不进行赋值操作即为获取。
+ 返回key对应的value值

#### 字典内置函数get获取方法

获取字典中指定的key的value

+ dict.get(key, default=None)
+ key:需要获取value的key,default:key不存在则返回默认值，默认是None,我们也可以自定义。

```python
my_dict = {'name': 'James', 'age':33}
name = my_dict.get('name')
print(name)
OUT: James
```

#### [] 与 get的区别

+ []如果获取的key不存在，则直接报错。
+ get如果获取的key不存在，则返回默认值。
+ 开发中，优先使用get函数

### 字典的删除

#### clear()的功能与用法

清空当前字典中所有的数据

+ dict.clear()			-------> 无参数，无返回值。

#### pop()的功能与用法

删除字典中指定的key，并将其结果返回，如果key不存在则报错。

+ dict.pop(key)			------> key希望被删除的键
+ 返回这个key对应的值（value)

#### del()函数的功能和用法

```python
my_dict = {'name': 'James', 'age':33}
del my_dict['name']
print(my_dict)
OUT: {'age':33}	
    
del my_dict			#删除整个字典
print(my_dict)
```

### 字典的copy()

#### copy()的功能

将当前字典复制一个新字典

#### copy()的用法

dict.copy()--------> 该函数无参数，返回一个一摸一样的内存地址不同的字典。

### 字典中的成员判断

#### in、not in 在字典中的用法



#### 字典内置的get



### 字典中的末尾删除函数popitem()

#### popitem的功能

删除当前字典里末尾一组键值对，并将其返回

#### popitem的用法

+ dict.popitme() 		------> 	无需传参
+ 返回被删除的键值对，用元组包裹0索引是key,1索引是value。

#### 注意事项

+ 如果字典为空，直接报错。

### 所有数据类型与布尔值的关系

字符串，数字，列表，元组，字典，空类型与布尔值的关系总结。

+ 每一种数据类型，自身的值都有表示True与False。
+ not 对于一切结果取反。

| 数据类型 | 为True          | 为False               |
| -------- | --------------- | --------------------- |
| int      | 非0             | 0                     |
| float    | 非0.0           | 0.0                   |
| str      | len(str) != 0   | len(str) == 0，即""   |
| list     | len(list) != 0  | len(list) == 0, 即[]  |
| tuple    | len(tuple) != 0 | len(tuple) == 0, 即() |
| dict     | len(dict) != 0  | len(dict) == 0, 即{}  |
| None     | not None        | None                  |







































































