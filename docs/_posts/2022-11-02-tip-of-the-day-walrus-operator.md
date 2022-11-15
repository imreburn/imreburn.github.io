---
layout: post
title: Tip of the Day - Walrus operator (Python)
katex: false
---

`:=`, assignment expression operator, also known as the walrus operator, is supported by Python 3.8 and above. Unlike an assignment *statement*, assignment *expression* returns the value as well as assigns. 
It can improve both performance and readability when using it properly.

```python
>>> (walrus := 1)
1
>>> walrus
1
# Call function f twice for each x
>>> [f(x) for x in numlist if f(x) > 0]
# Walrus operator can reduce calls with maintaining the readability
>>> [val for x in numlist if (val := f(x)) > 0]
```

### Related
- [What is the difference between an expression and a statement in Python?](https://stackoverflow.com/questions/4728073/what-is-the-difference-between-an-expression-and-a-statement-in-python)
- [The Walrus Operator: Python 3.8 Assignment Expressions](https://realpython.com/python-walrus-operator/)