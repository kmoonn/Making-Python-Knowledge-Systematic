# Py Quick Grammar Check

# 变量

```python
chr()  #int 👉 char
ord()  #char 👉 int
```

## 字符串

转义 **\**

去转义 **r“\”** 表示路径

```python
str.capitalize() # 首字母大写
str.title() # 单词首字母大写
str.upper() # 字母大写
str.find("") # 查找子串位置 无子串返回-1
str.index("") # 查找子串 无子串引发异常
str.startswith()
str.endswith() # 检查开头、结尾字符串
str.isdigit() # 检查是否由数字构成
str.isalpha() # 检查是否由字母构成
str.isalnum() # 检查是否由数字、字母构成
```

# 运算

```python
~ # 按位取反
>> << # 移位
& # 按位与
^ # 按位异或
|\ # 按位或

```

# 判断&循环

## i**f语句**与**elif语句**的区别

1. if语句只能有一个，而elif语句可以有零个或多个。
2. if语句在所有条件满足时仅执行一次，而elif语句在它的条件满足时执行，并且在前面的条件不满足时才判断。
3. **if语句在条件为真时执行后，立即跳出整个if-elif-else语句，而elif语句在条件为真时执行后，会继续判断其他的elif条件。**

## range

默认从0开始 到N-1 左闭右开

步长 可正可负 取奇偶数

# 容器

## list

- 连接合并列表

```python
list1.extend(list2)
```

- pop函数

接收被删除的返回值

- 遍历

通过enumerate函数处理列表之后再遍历可以同时获得元素索引和值

```python
for index, elem in enumerate(list1):
    print(index, elem)
```

- 排序

sorted函数返回列表排序后的拷贝不会修改传入的列表 默认字母表排序

排序规则 参数key、参数reverse

sort函数直接在列表上进行排序 修改列表

## tuple

tuple在创建时间和占用空间上面都优于list

![tuple-list time](https://image.kmoon.fun//images/202407291016985.png)

- 创建元组

```python
tup1 = 4,5,6
tup2 = (6,7,8)
```

- 分解元组

```python
a,b,c = tup1
```

- 交换变量

```python
b,a = a,b
```

## str

- join 分隔符连接list/tuple

```python
', '**.**join([ 'v1', 'v2', 'v3']) **=>** 'v1, v2, v3'
```

## set

- 创建集合

```python
set1 = set([3,6,3])
set1 = {3,6,3}
set1 = {num for num in range(1, 100) if num % 3 == 0 or num % 5 == 0}
```

- 集合操作

```python
set1.add()
set1.update([])
set1.discard()
set1.remove()
set1.pop()
```

- 判断集合包含关系

```python
set1.issubset(set2) #set1∈set2
set1.issuperset(set1) #set2∈set1
```

- 交集、并集、差集等

```python
set1 & set2
set1 | set2
set1 - set2
set1 ^ set2 # 移除两个集合中都存在的元素
set1 <= set2 # 判断子集和超集
```

## dict

- 构造器语法

```python
dict1= dict(one=1, two=2, three=3, four=4)
```

- 字典操作

```python
dict1.update(one='1', two='2') # 更新字典元素
dict1.popitem() # 删除字典元素、返回键值对
dict1.pop() # 删除字典元素、返回值
```

- 通过zip函数将两个序列压成字典

```python
dict1 = dict(zip(keyList,valueList))
```

- 更改Values

```python
dict1.update(dict2)
```

# 格式化

- format

```python
string1= 'My name is {0} {name}'
newString1= string1. format('Sean', name= 'Chen')
```

- %占位符

```python
%d # int
%lf # float
%s # str
%% # 百分号
```

- f 语法糖

```python
print(f'{f:.1f}华氏度 = {c:.1f}摄氏度')
```

- 0填充

```python
month= '5'
month.zfill(2)=> '05'
month= '12'
month.zfill(2)=> '12'
```

- 字符串填充

```python
str.center(50,'*') # 指点宽度居中、空白填充字符
str.rjust(50,'*') # 居左 填充
```

# 函数

## 参数

可变参数

```python
def add(*args): # 可以传入0或多个参数
	total = 0
	for val in args:
	total += val
return total
```

## 作用域

局部

嵌套 nonlocal

全局 global

内置

# 模块

module

```python
__name__是Python中一个隐含的变量 代表模块名
只有被Python解释器直接执行的模块的名字才是__main__
```