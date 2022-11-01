---
layout: post
title: Tip of the Day
katex: false
---

Test
```python
from collections import defaultdict
# default value : 0
d1 = defaultdict(int)
# default value : -2
d2 = defaultdict(lambda : -2)
# 2-d dictionary with default value None
d3 = defaultdict(lambda : defaultdict(lambda : None))
```

{% highlight python %}
from collections import defaultdict
# default value : 0
d1 = defaultdict(int)
# default value : -2
d2 = defaultdict(lambda : -2)
# 2-d dictionary with default value None
d3 = defaultdict(lambda : defaultdict(lambda : None))
{% endhighlight %}