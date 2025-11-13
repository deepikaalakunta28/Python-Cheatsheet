## Python Dictionary Cheatsheet
Dictionaries are used to store data values in key:value pairs.
A dictionary is a collection which is ordered*, changeable and do not allow duplicates.
## Create and print a dictionary:
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
print(thisdict)

## Dictionary Length
print(len(thisdict))

## The dict() Constructor
 thisdict = dict(name = "John", age = 36, country = "Norway")
print(thisdict)

## Check if Key Exists
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
if "model" in thisdict:
  print("Yes, 'model' is one of the keys in the thisdict dictionary") 

  ## Update Dictionary
  **The update() method will update the dictionary with the items from the given argument.**
  thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
thisdict.update({"year": 2020}) 

# 🐍 Python Dictionary Methods Cheat Sheet

A complete reference for all **Python dictionary (`dict`) methods**, with syntax, descriptions, and short examples — clean and ready to use.

---

## 📘 Dictionary Methods Table

| Method | Description | Example |
|--------|--------------|----------|
| `d.clear()` | Removes all items from the dictionary | `d.clear()` → `{}` |
| `d.copy()` | Returns a shallow copy of the dictionary | `new_d = d.copy()` |
| `dict.fromkeys(seq, value)` | Creates a new dictionary from sequence with specified value | `dict.fromkeys(['a', 'b'], 0)` → `{'a': 0, 'b': 0}` |
| `d.get(key, default)` | Returns value for key, or default if key not found | `d.get('age', 0)` → `25` |
| `d.items()` | Returns key-value pairs view | `dict_items([('name', 'Alice'), ('age', 25)])` |
| `d.keys()` | Returns all keys | `dict_keys(['name', 'age'])` |
| `d.values()` | Returns all values | `dict_values(['Alice', 25])` |
| `d.pop(key, default)` | Removes key and returns its value | `d.pop('age')` → `25` |
| `d.popitem()` | Removes and returns the last inserted key-value pair | `d.popitem()` → `('age', 25)` |
| `d.setdefault(key, default)` | Returns value; inserts key with default if not present | `d.setdefault('city', 'NYC')` → `'NYC'` |
| `d.update(other)` | Merges another dictionary into current one | `d.update({'city': 'Paris'})` |
| `len(d)` | Returns the number of key-value pairs | `len(d)` → `2` |
| `key in d` | Checks if key exists in dictionary | `'name' in d` → `True` |
| `d[key]` | Access value for given key | `d['name']` → `'Alice'` |
| `d[key] = value` | Add or update key-value pair | `d['age'] = 26` |
| `del d[key]` | Delete a key-value pair | `del d['age']` |
| `for k in d:` | Iterates over dictionary keys | `for k in d: print(k)` |
| `for k, v in d.items()` | Iterates over key-value pairs | `for k, v in d.items(): print(k, v)` |

---

---

## 🧩 Quick Example

```python
d = {"name": "Alice", "age": 25}

# Access
print(d["name"])        # Alice
print(d.get("age", 0))  # 25

# Add / Update
d["city"] = "Paris"
d.update({"email": "alice@example.com"})

# Remove
d.pop("age")
d.popitem()

# Iterate
for k, v in d.items():
    print(k, v)


## Conversion Between Types
# List of tuples → dict
dict([("a", 1), ("b", 2)])

# Keys and values separately
keys = ["a", "b"]
vals = [1, 2]
dict(zip(keys, vals))

# Dict → list of keys
list(person.keys())

# Dict → list of values
list(person.values())

# Dict → list of tuples
list(person.items())
```
### 🏁 Dictionary Operations Summary

| Operation         | Description                     | Example                                   |     
| ----------------- | ------------------------------- | ----------------------------------------- | 
| **Create**        | Create a new dictionary         | `d = {"a": 1, "b": 2}`                    |     
| **Access**        | Retrieve values by key          | `d["a"]`, `d.get("a", 0)`                 |    
| **Add / Update**  | Add new or modify existing key  | `d["c"] = 3`, `d.update({"d": 4})`        |     
| **Remove**        | Delete items                    | `d.pop("a")`, `del d["b"]`, `d.popitem()` |     
| **Loop**          | Iterate through key-value pairs | `for k,v in d.items(): print(k,v)`        |     
| **Check Key**     | Check if key exists             | `'a' in d`                                |     
| **Copy**          | Shallow copy                    | `new_d = d.copy()`                        |     
| **Merge**         | Combine dictionaries            | `{**d1, **d2}` or `d1                     | 
| **Comprehension** | Create from expression          | `{k: v*2 for k,v in d.items()}`           |   


| Operation                       | Description                  | Example                                                                                        |
|---------------------------------|------------------------------|------------------------------------------------------------------------------------------------|
| **Create Nested Dict**          | Dictionary within dictionary | `student = {"name": "Alice", "details": {"age": 25}}`                                          |
| **Access Nested Value**         | Access deeper value          | `student["details"]["age"]`                                                                    |
| **Safe Access**                 | Avoid KeyError               | `student.get("details", {}).get("age", 0)`                                                     |
| **Add Nested Key**              | Add key inside inner dict    | `student["details"]["city"] = "Paris"`                                                         |
| **Update Nested Key**           | Modify nested value          | `student["details"]["age"] = 26`                                                               |
| **Delete Nested Key**           | Remove key from inner dict   | `del student["details"]["age"]`                                                                |
| **Pop Nested Key**              | Remove key safely            | `student["details"].pop("age", None)`                                                          |
| **Iterate Nested**              | Loop outer and inner keys    | `for k,v in student.items(): print(k,v)`                                                       |
| **Nested Loop**                 | Loop deeper dicts            | `for k,v in student.items():\n    if isinstance(v,dict):\n        for sk,sv in v.items(): print(sk,sv)` |
| **Check Nested Key**            | Key exists in inner dict     | `'city' in student["details"]`                                                                 |
| **Merge Nested Dicts**          | Merge inner dict values      | `student["details"].update({"grade":"A"})`                                                     |
| **Dynamic Create (setdefault)** | Auto-create nested dict      | `data.setdefault("user", {}).setdefault("info", {})["name"]="Alice"`                           |
| **Traverse Recursively**        | Print all nested levels      | `def traverse(d):\n    for k,v in d.items():\n        if isinstance(v,dict): traverse(v)\n        else: print(k,v)` |
| **Flatten Nested Dict**         | Multi-level → single-level   | `{'details.age':25}`                                                                           |
| **Unflatten Dict**              | Single-level → nested        | `{'details':{'age':25}}`                                                                       |
| **Pretty Print**                | Nicely format dict           | `import pprint; pprint.pprint(student)`                                                        |



### 🧠 Quick Example

```python
school = {
  "classA": {"student1": {"name": "Alice", "age": 25}},
  "classB": {"student2": {"name": "Bob", "age": 23}}
}

# Access nested value
print(school["classA"]["student1"]["name"])  # Alice

# Update nested dict
school["classB"]["student2"]["city"] = "Paris"

# Iterate deeply
for cls, students in school.items():
    for sid, info in students.items():
        print(cls, sid, info)
```

# 📚 Python Dictionary & Nested Dictionary References

### 📘 Official Documentation
- [Python Docs – Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)  
  Covers standard dictionary operations, including nested dictionaries examples.
- [Python dict Type Reference](https://docs.python.org/3/library/stdtypes.html#dict)  
  Complete list of dictionary methods, useful for nested dictionary operations.

### 📝 Tutorials & Guides
- [Real Python – Dictionaries 101](https://realpython.com/python-dicts/)  
  Comprehensive guide to Python dictionaries.
- [W3Schools – Python Dictionary](https://www.w3schools.com/python/python_dictionaries.asp)  
  Basic and intermediate dictionary operations.
- [GeeksforGeeks – Dictionary Methods](https://www.geeksforgeeks.org/python-dictionary/)  
  Covers dictionary methods and examples.
- [Programiz – Python Dictionary](https://www.programiz.com/python-programming/dictionary)  
  Clear examples and tutorials.
- [Real Python – Nested Dictionaries](https://realpython.com/python-nested-dictionaries/)  
  Full guide on creating, accessing, updating, and iterating nested dictionaries.
- [Programiz – Python Nested Dictionary](https://www.programiz.com/python-programming/nested-dictionary)  
  Examples with nested loops, safe access, and modification.
- [GeeksforGeeks – Nested Dictionaries](https://www.geeksforgeeks.org/python-nested-dictionary/)  
  Accessing, modifying, iterating, flattening, and merging nested dictionaries.
- [W3Schools – Python Dictionaries (Nested)](https://www.w3schools.com/python/python_dictionaries.asp)  
  Applies dictionary operations to nested structures.




##Python Lists CheatSheet

| Method                          | Description                                           | Example                                   |
| ------------------------------- | ----------------------------------------------------- | ----------------------------------------- |
| `append(x)`                     | Adds element `x` at the end                           | `my_list.append(5)` → `[1,2,3,4,5]`       |
| `insert(i, x)`                  | Inserts `x` at index `i`                              | `my_list.insert(1, 10)` → `[1,10,2,3,4]`  |
| `extend(iterable)`              | Adds elements from iterable                           | `my_list.extend([6,7])` → `[1,2,3,4,6,7]` |
| `remove(x)`                     | Removes first occurrence of `x`                       | `my_list.remove(2)` → `[1,3,4]`           |
| `pop([i])`                      | Removes & returns element at index `i` (default last) | `my_list.pop()` → `4`, list → `[1,2,3]`   |
| `clear()`                       | Removes all elements                                  | `my_list.clear()` → `[]`                  |
| `index(x[, start[, end]])`      | Returns first index of `x`                            | `my_list.index(3)` → `2`                  |
| `count(x)`                      | Counts occurrences of `x`                             | `my_list.count(2)` → `1`                  |
| `sort(key=None, reverse=False)` | Sorts list in-place                                   | `my_list.sort()` → `[1,2,3,4]`            |
| `reverse()`                     | Reverses list in-place                                | `my_list.reverse()` → `[4,3,2,1]`         |
| `copy()`                        | Returns a shallow copy                                | `new_list = my_list.copy()`               |

## List Comprehensions
# Basic
squares = [x**2 for x in range(5)] # [0,1,4,9,16]

# With condition
even_squares = [x**2 for x in range(10) if x%2==0] # [0,4,16,36,64]

# Nested comprehension
matrix = [[i*j for j in range(3)] for i in range(3)]
# [[0,0,0],[0,1,2],[0,2,4]]

## Reference Links
Reference Links

Official Python Docs: https://docs.python.org/3/tutorial/datastructures.html#more-on-lists
W3Schools Python Lists: https://www.w3schools.com/python/python_lists.asp
Real Python List Guide: https://realpython.com/python-lists-tuples

## String cheatsheet
| Method                        | Description                             | Example                                           |
| ----------------------------- | --------------------------------------- | ------------------------------------------------- |
| `str.upper()`                 | Converts to uppercase                   | `"hello".upper()` → `"HELLO"`                     |
| `str.lower()`                 | Converts to lowercase                   | `"HELLO".lower()` → `"hello"`                     |
| `str.title()`                 | Capitalizes each word                   | `"hello world".title()` → `"Hello World"`         |
| `str.capitalize()`            | Capitalizes first letter                | `"hello".capitalize()` → `"Hello"`                |
| `str.strip([chars])`          | Removes leading/trailing chars          | `"  hello  ".strip()` → `"hello"`                 |
| `str.lstrip([chars])`         | Removes leading chars                   | `"  hello".lstrip()` → `"hello"`                  |
| `str.rstrip([chars])`         | Removes trailing chars                  | `"hello  ".rstrip()` → `"hello"`                  |
| `str.replace(old, new)`       | Replaces substring                      | `"hello".replace('l','x')` → `"hexxo"`            |
| `str.split(sep=None)`         | Splits string to list                   | `"a,b,c".split(',')` → `['a','b','c']`            |
| `str.join(iterable)`          | Joins iterable into string              | `",".join(['a','b'])` → `"a,b"`                   |
| `str.find(sub)`               | Returns index of first occurrence or -1 | `"hello".find('l')` → 2                           |
| `str.index(sub)`              | Like find but raises error if not found | `"hello".index('l')` → 2                          |
| `str.count(sub)`              | Counts occurrences                      | `"hello".count('l')` → 2                          |
| `str.startswith(prefix)`      | Checks start                            | `"hello".startswith('he')` → True                 |
| `str.endswith(suffix)`        | Checks end                              | `"hello".endswith('lo')` → True                   |
| `str.isalpha()`               | Checks if all letters                   | `"abc".isalpha()` → True                          |
| `str.isdigit()`               | Checks if all digits                    | `"123".isdigit()` → True                          |
| `str.isspace()`               | Checks if all whitespace                | `"   ".isspace()` → True                          |
| `str.isalnum()`               | Checks letters + digits                 | `"abc123".isalnum()` → True                       |
| `str.zfill(width)`            | Pads with zeros on left                 | `"42".zfill(5)` → `"00042"`                       |
| `str.format(*args, **kwargs)` | Format string                           | `"Hello {}".format("World")` → `"Hello World"`    |
| `f-string`                    | Modern string formatting                | `name="Alice"; f"Hello {name}"` → `"Hello Alice"` |

## Reference Links
Official Python Docs: https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str
W3Schools Strings: https://www.w3schools.com/python/python_strings.asp
Real Python String Guide: https://realpython.com/python-strings/
