# Python 3.7
* Introducing Data Classes

```python

# before:
class MyClass:
	def __init__(self, var_a, var_b):
		self.var_a = var_a
		self.var_b = var_b

# after:
@dataclass
class MyClass:
	var_a: str
	var_b: str
```