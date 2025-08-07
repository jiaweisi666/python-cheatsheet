python-cheatsheet
本文档汇集了 Python 中常用的内置函数和对象方法，旨在为开发者提供一个快速参考，以便于检索和理解
目录

字符串 (String) 方法
列表 (List) 方法与相关函数
字典 (Dictionary) 方法
文件处理 (File I/O)
数据序列化 (JSON)
面向对象 (OOP)
常用内置函数
标准库模块示例
单元测试断言方法

1. 字符串 (String) 方法
字符串方法作用于一个字符串对象，并返回一个新的字符串，原始字符串不会被修改。
str.title()

描述: 返回字符串的标题化版本，即每个单词的首字母大写，其余字母小写。
示例:
name = "ade lovelace"
print(name.title())
# 输出: Ade Lovelace



str.upper() / str.lower()

描述: 分别返回将字符串中所有字母转换为大写或小写的版本。
示例:
message = "Hello World"
print(message.upper()) # 输出: HELLO WORLD
print(message.lower()) # 输出: hello world



str.strip() / rstrip() / lstrip()

描述:
strip(): 移除字符串两端的空白字符（包括空格、换行符、制表符）。
rstrip(): 只移除字符串末尾（右侧）的空白字符。
lstrip(): 只移除字符串开头（左侧）的空白字符。


示例:
text = "  python  "
print(f"'{text.strip()}'")  # 输出: 'python'
print(f"'{text.rstrip()}'")  # 输出: '  python'
print(f"'{text.lstrip()}'")  # 输出: 'python  '



str.split(separator)

描述: 根据指定的分隔符 separator 将字符串分割成一个列表。如果未指定分隔符，则默认按所有空白字符分割。
示例:
csv_line = "apple,banana,orange"
fruits = csv_line.split(',')
print(fruits)
# 输出: ['apple', 'banana', 'orange']



str.replace(old, new)

描述: 返回字符串的副本，其中所有的子字符串 old 都被替换为 new。
示例:
sentence = "I like cats."
new_sentence = sentence.replace('cats', 'dogs')
print(new_sentence)
# 输出: I like dogs.



separator.join(iterable)

描述: 将一个可迭代对象（如列表）中的所有元素连接成一个单一的字符串，元素之间用指定的 separator 字符串分隔。
示例:
words = ['Python', 'is', 'fun']
sentence = ' '.join(words)
print(sentence)
# 输出: Python is fun



2. 列表 (List) 方法与相关函数
list.append(element) (方法)

描述: 在列表的末尾添加一个元素。此方法会就地修改列表。
示例:
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.append('ducati')
print(motorcycles)
# 输出: ['honda', 'yamaha', 'suzuki', 'ducati']



list.insert(index, element) (方法)

描述: 在列表的指定 index 位置插入一个元素。此方法会就地修改列表。
示例:
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.insert(0, 'ducati')
print(motorcycles)
# 输出: ['ducati', 'honda', 'yamaha', 'suzuki']



list.pop(index) (方法)

描述: 移除并返回列表中指定 index 位置的元素。如果 index 未指定，则默认移除并返回最后一个元素。
示例:
motorcycles = ['honda', 'yamaha', 'suzuki']
last_owned = motorcycles.pop()
print(f"The last motorcycle I owned was a {last_owned.title()}.") # 输出: The last motorcycle I owned was a Suzuki.
print(motorcycles) # 输出: ['honda', 'yamaha']



list.remove(value) (方法)

描述: 移除列表中第一个出现的指定 value。如果该值不存在，则会引发 ValueError。
示例:
motorcycles = ['honda', 'yamaha', 'suzuki', 'yamaha']
motorcycles.remove('yamaha')
print(motorcycles)
# 输出: ['honda', 'suzuki', 'yamaha']



list.sort() (方法) vs sorted() (函数)

list.sort() (方法)
描述: 对列表进行永久性排序（就地修改）。默认升序。可通过 reverse=True 参数进行降序排序。
示例:
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort(reverse=True) # 降序排序
print(cars)
# 输出: ['toyota', 'subaru', 'bmw', 'audi']




sorted(iterable) (内置函数)
描述: 返回一个新的、已排序的列表，不修改原始的可迭代对象。
示例:cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:", cars)
print("Here is the sorted list:", sorted(cars))
print("Here is the original list again:", cars)
# 输出:
# Here is the original list: ['bmw', 'audi', 'toyota', 'subaru']
# Here is the sorted list: ['audi', 'bmw', 'subaru', 'toyota']
# Here is the original list again: ['bmw', 'audi', 'toyota', 'subaru']





list.reverse() (方法)

描述: 永久性地反转列表元素的顺序。
示例:
cars = ['bmw', 'audi', 'toyota']
cars.reverse()
print(cars)
# 输出: ['toyota', 'audi', 'bmw']



3. 字典 (Dictionary) 方法
dict.get(key, default)

描述: 返回指定 key 对应的 value。如果 key 不存在，不会报错，而是返回指定的 default 值（如果未提供 default，则返回 None）。
示例:
alien_0 = {'color': 'green', 'speed': 'slow'}
points = alien_0.get('points', 'No points assigned.')
print(points)
# 输出: No points assigned.



dict.items() / keys() / values()

描述:
items(): 返回一个包含所有 (键, 值) 元组的视图对象。
keys(): 返回一个包含所有键的视图对象。
values(): 返回一个包含所有值的视图对象。


示例:
user_profile = {'username': 'jdoe', 'first': 'john', 'last': 'doe'}

# 遍历所有键值对
for key, value in user_profile.items():
    print(f"Key: {key}, Value: {value}")

# 遍历所有键
for key in user_profile.keys():
    print(f"Key: {key}")

# 遍历所有值
for value in user_profile.values():
    print(f"Value: {value}")



4. 文件处理 (File I/O)
open(file, mode) (内置函数)

描述: 打开一个文件，并返回对应的文件对象。推荐使用 with 语句来自动管理文件的关闭。
模式 (mode):
'r': 读取模式 (默认)。
'w': 写入模式 (会覆盖已有文件)。
'a': 附加模式 (在文件末尾追加内容)。
'r+': 读写模式。


示例:
# 写入文件
with open('greeting.txt', 'w') as f:
    f.write("Hello, Python!")

# 读取整个文件
with open('greeting.txt', 'r') as f:
    contents = f.read()
    print(contents) # 输出: Hello, Python!



文件对象的读取方法

file.read(): 读取文件的全部内容，返回一个字符串。
file.readlines(): 读取所有行并返回一个列表，列表中的每个元素是文件的一行。
file.readline(): 读取文件中的下一行。

5. 数据序列化 (JSON)
需要先 import json。
json.dump(data, file_object)

描述: 将 Python 对象（如列表、字典）序列化为 JSON 格式的字符串，并将其写入一个文件对象中。
示例:
import json
numbers = [2, 3, 5, 7, 11, 13]
with open('numbers.json', 'w') as f:
    json.dump(numbers, f)



json.load(file_object)

描述: 从一个文件对象中读取 JSON 格式的数据，并将其反序列化为 Python 对象。
示例:
import json
with open('numbers.json') as f:
    numbers = json.load(f)
print(numbers)
# 输出: [2, 3, 5, 7, 11, 13]



6. 面向对象 (OOP)
super() (内置函数)

描述: 在子类中，调用父类（超类）的方法。常用于 __init__ 方法中，以确保父类的初始化逻辑被执行。
示例:
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

class ElectricCar(Car):
    def __init__(self, make, model, battery_size):
        # 调用父类的__init__方法
        super().__init__(make, model)
        self.battery_size = battery_size



7. 常用内置函数
这些函数是 Python 内置的，可以直接在任何地方使用。

len(s): 返回对象（字符串、列表、字典等）的长度或元素个数。
range(start, stop, step): 生成一个整数序列。
list(iterable): 将一个可迭代对象（如 range 对象或字符串）转换为列表。
int(x): 将一个字符串或数字转换为整数。
input(prompt): 显示提示 prompt，并等待用户输入，返回一个字符串。
min(iterable) / max(iterable) / sum(iterable): 分别返回数字列表中的最小值、最大值和总和。
set(iterable): 从一个可迭代对象创建一个集合，用于去重等操作。

8. 标准库模块示例
需要先
import 相应模块。
random 模块

random.randint(a, b): 返回一个 [a, b] 范围内的随机整数（包含 a 和 b）。
random.choice(sequence): 从一个非空序列（如列表或元组）中随机返回一个元素。
示例:import random
print(random.randint(1, 6)) # 随机输出 1 到 6 的整数
players = ['charles', 'martina', 'michael', 'florence']
first_up = random.choice(players)
print(first_up.title()) # 随机输出一个名字



9. 单元测试断言方法
这些方法属于 unittest.TestCase 类，用于编写测试用例。

assertEqual(a, b): 验证 a == b。
assertNotEqual(a, b): 验证 a != b。
assertTrue(x): 验证 x 为 True。
assertFalse(x): 验证 x 为 False。
assertIn(item, list): 验证 item 在 list 中。
assertNotIn(item, list): 验证 item 不在 list 中。
