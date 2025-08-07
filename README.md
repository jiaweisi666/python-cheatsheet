# Python 常用函数与方法速查手册

本文档汇集了 Python 中常用的内置函数和对象方法，旨在为开发者提供一个快速参考，以便于检索和理解。

## 目录

- [1. 字符串 (String) 方法](#1-字符串-string-方法)
- [2. 列表 (List) 方法与相关函数](#2-列表-list-方法与相关函数)
- [3. 字典 (Dictionary) 方法](#3-字典-dictionary-方法)
- ... (以此类推)

---

## 1. 字符串 (String) 方法

字符串方法作用于一个字符串对象，并返回一个新的字符串，原始字符串不会被修改。

### `str.title()`

*   **描述**: 返回字符串的标题化版本，即每个单词的首字母大写，其余字母小写。
*   **示例**:

    ```python
    name = "ade lovelace"
    print(name.title())
    # 输出: Ade Lovelace
    ```

### `str.upper() / str.lower()`

*   **描述**: 分别返回将字符串中所有字母转换为大写或小写的版本。
*   **示例**:

    ```python
    message = "Hello World"
    print(message.upper())
    # 输出: HELLO WORLD
    
    print(message.lower())
    # 输出: hello world
    ```

### `str.strip() / rstrip() / lstrip()`

*   **描述**: 
    *   `strip()`: 移除字符串两端的空白字符。
    *   `rstrip()`: 只移除字符串末尾的空白字符。
    *   `lstrip()`: 只移除字符串开头的空白字符。
*   **示例**:

    ```python
    text = "  python  "
    print(f"'{text.strip()}'")
    # 输出: 'python'
    ```

---
