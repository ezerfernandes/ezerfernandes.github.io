---
layout: post
title: "Querying dictionaries by priority"
date: 2016-11-30
---

I was thinking of a way to query several dictionaries for a key, in order of priority. The simplest way that I thought was this:

```python
class DictQuery(object):
    def __init__(self, *args):
        self._dicts = args
    def __getitem__(self, value):
        for dic in self._dicts:
            if value in dic.keys():
                return dic[value]
        raise KeyError()
```

Now I can pass a list of dictionaries to this class and use it as a read-only dictionary. It will try to find the key in the first dictionary; if it finds it will return the value; otherwise, it will try to find in the next dictionary. Only if doesn't find the key in any dictionary, it will raise an error.

```python
In [1]: cache_list = [{'banana': 3, 'apple': 5}, {'pineapple': 7, 'banana': 15}]

In [2]: dic = DictQuery(*cache_list)

In [3]: dic['apple']
Out[3]: 5

In [4]: dic['pineapple']
Out[4]: 7

In [5]: dic['banana']
Out[5]: 3

In [6]: cache_list[0].pop('banana')
Out[6]: 3

In [7]: dic['banana']
Out[7]: 15
```

You can make it as complicated as you need (e.g., to update the keys), but the neat thing about it is to be able to query a list of dictionaries as if it's just one.
