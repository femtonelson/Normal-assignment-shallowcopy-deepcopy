# Normal-assignment-shallowcopy-deepcopy (Python 3)

```python
import copy
b = {"a":1, "b":1, "c": [1, 2, 3], "d": {"a":1, "b":{"a":1, "b":2}, "c":4}, "e":4}

c = copy.copy(b)
d = copy.deepcopy(b)
e = b

print("Initial b equal to 1: ", b["d"]["a"])

c["d"]["a"] = 2
d["d"]["a"] = 3

print("b is changed by shallow copy and not deepcopy : ", b["d"]["a"])
print("c : ", c["d"]["a"])
print("d : ", d["d"]["a"])

e["d"]["a"] = 4
print("b is changed when e is changed : ", b["d"]["a"])
```
Result :
```python
Initial b equal to 1:  1
b is changed by shallow copy and not deepcopy :  2
c :  2
d :  3
b is changed when e is changed :  4
```
Comment :
- Normal variable assignment with "=" does a copy by reference, as such any modification done on variable e affects variable b
- Shallow copy (copy.copy) copies data to a new address location and assigns a new variable "c" but a change on compound objects in "c" (dictionary in dictionary) is still reflected in "b".
- Deepcopy (copy.deepcopy) copies data to a new memory address and assigns a new variable "d" such that any change performed on d leaves the original object "b" completely unchanged.
