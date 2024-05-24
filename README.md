# matplotlib_mac_chinese
mac在matplotlib中显示中文的操作方法


## 正则过滤出中文(简中、繁中)、英文和数字
```python
import re
# 用正则过滤出中文(简中、繁中)、英文和数字 -- 中文是字级别，英文和数字是最长的连续串。
query = 'KIM  x Converse  70 UTILITY  奶白'
pattern = re.compile(r'([\u4e00-\u9fa5]|[a-zA-Z]+|\d+)') 
res = pattern.split(query)
print(res[1:-1])

res = pattern.findall(query)
print(res)
```

输出：  
```
['KIM', '  ', 'x', ' ', 'Converse', '  ', '70', ' ', 'UTILITY', '  ', '奶', '', '白']
['KIM', 'x', 'Converse', '70', 'UTILITY', '奶', '白']
```
