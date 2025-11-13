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

### 🏁 Dictionary Operations Summary

| Operation | Description | Example |
| ---------- | ------------ | -------- |
| **Create** | Create a new dictionary | `d = {"a": 1, "b": 2}` |
| **Access** | Retrieve values by key | `d["a"]`, `d.get("a")` |
| **Add / Update** | Add new or modify existing key | `d["c"] = 3` |
| **Remove** | Delete items | `d.pop("a")`, `del d["a"]` |
| **Loop** | Iterate through key-value pairs | `for k, v in d.items(): print(k, v)` |
| **Check Key** | Check if a key exists | `'a' in d` |
| **Copy** | Shallow copy of dictionary | `new_d = d.copy()` |
| **Merge** | Combine dictionaries | `{**d1, **d2}` or `d1 | d2` |
| **Comprehension** | Create from expression | `{k: v*2 for k, v in d.items()}` |

---

## 🧩 Python Nested Dictionary Cheat Sheet

| Operation | Description | Example |
|------------|--------------|----------|
| **Create Nested Dict** | Define a dictionary within another | `student = {"name": "Alice", "details": {"age": 25, "city": "London"}}` |
| **Access Nested Value** | Access deeper values | `student["details"]["city"]` → `'London'` |
| **Safe Access** | Prevent `KeyError` | `student.get("details", {}).get("age")` → `25` |
| **Add Nested Key** | Add a key inside inner dict | `student["details"]["country"] = "UK"` |
| **Update Nested Key** | Modify nested value | `student["details"]["age"] = 26` |
| **Delete Nested Key** | Remove key from inner dict | `del student["details"]["city"]` |
| **Delete Inner Dict** | Remove entire inner dictionary | `del student["details"]` |
| **Pop Nested Key** | Safely remove nested key | `student["details"].pop("age", None)` |
| **Iterate Nested** | Loop through outer and inner keys | `for k, v in student.items(): print(k, v)` |
| **Nested Loop** | Handle deeper dicts | `for k,v in student.items(): if isinstance(v, dict): for subk, subv in v.items(): print(subk, subv)` |
| **Check Nested Key** | Check key in nested dict | `'city' in student["details"]` → `True` |
| **Merge Nested Dicts** | Merge inner values | `student["details"].update({"grade": "A"})` |
| **Dynamic Create (setdefault)** | Auto-create nested dicts | `data.setdefault("user", {}).setdefault("info", {})["name"] = "Alice"` |
| **Dynamic Create (defaultdict)** | Infinite-depth dicts | `from collections import defaultdict; nested = lambda: defaultdict(nested); nested()["x"]["y"] = 1` |
| **Traverse Recursively** | Print all levels | `def traverse(d): for k,v in d.items(): print(k,v) if not isinstance(v,dict) else traverse(v)` |
| **Flatten Nested Dict** | Multi-level → single-level | `{'details.age': 25, 'details.city': 'London'}` |
| **Unflatten Dict** | Single-level → nested | `{'details': {'age': 25, 'city': 'London'}}` |
| **Deep Merge Dicts** | Merge recursively | `deep_merge(a, b)` |
| **Convert to JSON** | Serialize nested dict | `json.dumps(student, indent=2)` |
| **Pretty Print** | Nicely formatted output | `import pprint; pprint.pprint(student)` |
| **Get All Keys (Recursive)** | Collect all keys | `def keys(d): [k for k,v in d.items() if not isinstance(v,dict)]` |
| **Convert to List** | Get values from nested level | `list(student["details"].values())` |
| **Length** | Count top-level keys | `len(student)` |
| **Clear** | Remove all items | `student.clear()` |
| **Comprehension** | Create nested dict | `{cls: {stu: stu*2 for stu in range(2)} for cls in ["A","B"]}` |

---

✅ **Tips for Clean Markdown Tables**
- Use single backticks (`) for inline code.
- Don’t add newlines inside table cells.
- Avoid triple backticks (```) inside tables.
- Keep column widths aligned for readability.



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

## 📚 References & Further Reading

- [Python Docs – Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
- [Python dict Type Reference](https://docs.python.org/3/library/stdtypes.html#dict)
- [Real Python – Dictionaries 101](https://realpython.com/python-dicts/)
- [W3Schools – Python Dictionary](https://www.w3schools.com/python/python_dictionaries.asp)
- [GeeksforGeeks – Dictionary Methods](https://www.geeksforgeeks.org/python-dictionary/)
- [Programiz – Python Dictionary](https://www.programiz.com/python-programming/dictionary)

