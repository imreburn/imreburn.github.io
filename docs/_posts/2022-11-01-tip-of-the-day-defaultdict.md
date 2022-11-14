---
layout: post
title: Tip of the Day - defaultdict (Python)
katex: false
---

`defaultdict` in Python is a lazy implementation of the dictionary. It is not necessary to set the size or initialize values at the time of declaration. The default value is not assigned for a key until it is called for the first time. It is useful for implementing dynamic programming.

```python
from collections import defaultdict
# default value : 0
d1 = defaultdict(int)
# default value : -2
d2 = defaultdict(lambda : -2)
# 2-d dictionary with default value None
d3 = defaultdict(lambda : defaultdict(lambda : None))
```

