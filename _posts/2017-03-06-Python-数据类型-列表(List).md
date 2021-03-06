---
layout: post
title: Python-数据类型-列表(List)
categories: Python语法
description: Python-数据类型-列表(List)
keywords: Python语法
---

# Python高级变量类型列表详解

### 列表的定义

- List(列表)是Python中使用最频繁的数据类型，在其他语言中通常叫做**数组**

- 列表是有序的集合

- 定义列表使用  **[ ]** 定义，数据之间使用 **,** 分割

  ```python
  name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]
  ```

- 列表的**索引**从 **0** 开始：

  - **索引**就是数据在**列表**中的位置编号，索引又可以被称为**下标** 

- 【注意】: 从列表中取值时,如果超出索引范围,程序会产生异常

  ```
  IndexError: list index out of range
  ```

### 列表的常用操作

#### 增加

- 列表名.insert(index, 数据)：在指定位置插入数据(位置前有空元素会补位)

  ```python
  # 往列表name_list下标为0的地方插入数据
  In [3]: name_list.insert(0, "Sasuke")

  In [4]: name_list
  Out[4]: ['Sasuke', 'zhangsan', 'lisi', 'wangwu', 'zhaoliu']

  # 现有的列表下标是0-4，如果我们要在下标是6的地方插入数据，那个会自动插入到下标为5的地方，也就是
  # 插入到最后
  In [5]: name_list.insert(6, "Tom")

  In [6]: name_list
  Out[6]: ['Sasuke', 'zhangsan', 'lisi', 'wangwu', 'zhaoliu', 'Tom']
  ```

- 列表名.append(数据)：在列表的末尾追加数据(最常用的方法)

  ```python
  In [7]: name_list.append("Python")

  In [8]: name_list
  Out[8]: ['Sasuke', 'zhangsan', 'lisi', 'wangwu', 'zhaoliu', 'Tom', 'Python']
  ```

- 列表.extend(Iterable)：将可迭代对象中的元素追加到列表。

  ```python
  # 有两个列表 a 和 b a.extend(b) 会将b中的元素追加到列表a中
  In [10]: a = [11, 22, 33]

  In [11]: b = [44, 55, 66]

  In [12]: a.extend(b)

  In [13]: a
  Out[13]: [11, 22, 33, 44, 55, 66]
  # 有列表c  和 字符串 d  c.extend(d)  会将字符串d中的每个字符拆开作为元素插入到列表c
  In [14]: c = ['j', 'a', 'v', 'a']

  In [15]: d = "python"

  In [16]: c.extend(d)

  In [17]: c
  Out[17]: ['j', 'a', 'v', 'a', 'p', 'y', 't', 'h', 'o', 'n']
  ```

#### 取值和修改

- 取值：列表名[index] ：根据下标来取值

  ```python
  In [19]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]

  In [20]: name_list[0]
  Out[20]: 'zhangsan'

  In [21]: name_list[3]
  Out[21]: 'zhaoliu'
  ```

- 修改：列表名[index] = 数据：修改指定索引的数据

  ```python
  # 将列表中下标为0的值 zhangsan  修改为  Sasuke
  In [22]: name_list[0] = "Sasuke"

  In [23]: name_list
  Out[23]: ['Sasuke', 'lisi', 'wangwu', 'zhaoliu']
  ```

#### 删除

- del 列表名[index]：删除指定索引的数据

  ```python
  In [25]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]
  # 删除索引是 1 的数据
  In [26]: del name_list[1]

  In [27]: name_list
  Out[27]: ['zhangsan', 'wangwu', 'zhaoliu']
  ```

- 列表名.remove(数据)：删除第一个出现的指定数据

  ```python
  In [30]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu", "lisi"]
  # 删除 第一次出现的 lisi 的数据
  In [31]: name_list.remove("lisi")

  In [32]: name_list
  Out[32]: ['zhangsan', 'wangwu', 'zhaoliu', 'lisi']
  ```

- 列表名.pop()：删除末尾的数据,**返回值**: 返回被删除的元素

  ```python
  In [33]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]
  # 删除最后一个元素  zhaoliu  并将元素 zhaoliu 返回
  In [34]: name_list.pop()
  Out[34]: 'zhaoliu'

  In [35]: name_list
  Out[35]: ['zhangsan', 'lisi', 'wangwu']
  ```

- 列表名.pop(index)：删除指定索引的数据，返回被删除的元素

  ```python
  In [36]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]
  # 删除索引为 1 的数据 lisi
  In [37]: name_list.pop(1)
  Out[37]: 'lisi'

  In [38]: name_list
  Out[38]: ['zhangsan', 'wangwu', 'zhaoliu']
  ```

- 列表名.clear()：清空整个列表的元素

  ```python
  In [40]: name_list = ["zhangsan", "lisi", "wangwu", "zhaoliu"]

  In [41]: name_list.clear()

  In [42]: name_list
  Out[42]: []
  ```

#### 排序

- 列表名.sort()：升序排序  从小到大

  ```python
  In [43]: a = [33, 44, 22, 66, 11]

  In [44]: a.sort()

  In [45]: a
  Out[45]: [11, 22, 33, 44, 66]
  ```

- 列表名.sort(reverse=True)：降序排序 从大到小

  ```python
  In [46]: a = [33, 44, 22, 66, 11]

  In [47]: a.sort(reverse=True)

  In [48]: a
  Out[48]: [66, 44, 33, 22, 11]
  ```

- 列表名.reverse()：列表逆序、反转

  ```python
  In [50]: a = [11, 22, 33, 44, 55]

  In [51]: a.reverse()

  In [52]: a
  Out[52]: [55, 44, 33, 22, 11]
  ```

#### 统计相关

- len(列表名)：得到列表的长度

  ```python
  In [53]: a = [11, 22, 33, 44, 55]

  In [54]: len(a)
  Out[54]: 5
  ```

- 列表名.count(数据)：数据在列表中出现的次数

  ```python
  In [56]: a = [11, 22, 11, 33, 11]

  In [57]: a.count(11)
  Out[57]: 3
  ```

- 列表名.index(数据)：数据在列表中首次出现时的索引，没有查到会报错。

  ```python
  In [59]: a = [11, 22, 33, 44, 22]

  In [60]: a.index(22)
  Out[60]: 1
  ```

- if  数据  in 列表： 判断列表中是否包含某元素。

  ```python
  a = [11, 22, 33, 44 ,55]
  if 33 in a:
  	print("找到了....")
  ```

#### 循环遍历

- 使用while循环：

  ```python
  a = [11, 22, 33, 44, 55]

  i = 0

  while i < len(a):
  	print(a[i])
  	i += 1
  ```

- 使用for循环：

  ```python
  a = [11, 22, 33, 44, 55]

  for i in a:
  	print(i)
  ```

  ​