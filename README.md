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

### 🧩 Dictionary Methods (Quick Reference)

| Method | Description | Example |
|--------|--------------|----------|
| `d.keys()` | Returns all keys | `dict_keys(['name', 'age'])` |
| `d.values()` | Returns all values | `dict_values(['Alice', 25])` |
| `d.items()` | Returns key-value pairs | `dict_items([('name', 'Alice'), ('age', 25)])` |
| `d.copy()` | Shallow copy | `new_d = d.copy()` |
| `d.update(other)` | Merges another dict | `d.update({"city": "NYC"})` |
| `d.setdefault(k, v)` | Sets default if key missing | `d.setdefault("country", "USA")` |
| `d.fromkeys(keys, value)` | Create dict from keys | `dict.fromkeys(["a", "b"], 0)` → `{'a': 0, 'b': 0}` |

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

| Operation     | Description                      | Example |
| ------------- | -------------------------------- | -------- |
| **Create**        | Create a new dictionary | `d = {"a": 1, "b": 2}` |
| **Access**        | Retrieve values by key | `d["a"]`, `d.get("a")` |
| **Add / Update**  | Add new or modify existing key | `d["c"] = 3` |
| **Remove**        | Delete items | `d.pop("a")`, `del d["a"]` |
| **Loop**          | Iterate through key-value pairs | `for k, v in d.items(): print(k, v)` |
| **Check Key**     | Check if a key exists | `'a' in d` |
| **Copy**          | Shallow copy of dictionary | `new_d = d.copy()` |
| **Merge**         | Combine dictionaries | `{**d1, **d2}` or `d1 | d2` |
| **Comprehension** | Create from expression | `{k: v*2 for k, v in d.items()}` |

## 📚 References & Further Reading

- [Python Docs – Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
- [Python dict Type Reference](https://docs.python.org/3/library/stdtypes.html#dict)
- [Real Python – Dictionaries 101](https://realpython.com/python-dicts/)
- [W3Schools – Python Dictionary](https://www.w3schools.com/python/python_dictionaries.asp)
- [GeeksforGeeks – Dictionary Methods](https://www.geeksforgeeks.org/python-dictionary/)
- [Programiz – Python Dictionary](https://www.programiz.com/python-programming/dictionary)

