---
layout: post
title: Tip of the Day - Walrus operator
katex: false
---

`:=`, assignment expression operator, also known as the walrus operator, is supported by Python 3.8 and above. Unlike an assignment *statement*, assignment *expression* returns the value as well as does assignment. 
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