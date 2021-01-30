---
layout: post
title: "Favorite algorithmns to 'hello world' a language"
date: 2016-08-11
---

I think the best algorithms to try on a new language must be simple, well understood and quickly implementable. The algorithms I always try on a new language are **factorial** and **fibonacci**. I like to implement them in several different ways, with different performances so I can explore the power and expressiveness of that language.</p>

As an example, here are some implementations of the fibonacci algorithm, in Python.

### A recursive implementation. Performance is O(2<sup>N</sup>), horrible, but it's the clearer implementation:

```python
def fibonacci(n):
	if n == 0 or n == 1:
		return n
	else:
		return fibonacci(n - 1) + fibonacci(n - 2)
```

The recursive implementation is simply a transcription of the mathematical definition. I like to start with the simplest implementation to getting acquainted with the language.

### An iterative implementation. Better performance, O(N), and it's yet a simple implementation:

```python
def fibonacci(n):
	elem1, elem2 = (0, 1)
	for i in range(n):
		elem1, elem2 = (elem2, elem1 + elem2)
	return elem1
```

It would be possible not to calculate elem2 (one element ahead of the needed), but I think it's good enough.

### Fibonacci with memoization, using a class (Performance is O(N) but can be close to the performance of getting a dictionary item, O(1), if it's used several times to generate the elements of the fibonacci series):</h4>

```python
class Fibonacci(object):
	_cache = { 0: 0, 1: 1 }

	def __call__(self, n):
		return self._fib(n)

	def _fib(self, n):
		if n in self._cache.keys():
			return self._cache[n]
		else:
			self._cache[n] = self._fib(n - 1) + self._fib(n - 2)
			return self._cache[n]

fibonacci = Fibonacci()
```

The object 'fibonacci' can be used as a normal function, but it saves the results in a dictionary, so that when it's called again, it checks if the result is already calculated and returns it, instead of calculating it again.

### Fibonacci using a decorator for memoization. It has the same performance characteristics of the last example, with the advantage of being easier to read and being easier to reuse the memoization function:

```python
def memoize(f):
	cache = {}
	def decorated_function(*args):
		if args in cache:
			return cache[args]
		else:
			cache[args] = f(*args)
			return cache[args]
	return decorated_function


@memoize
def fibonacci(n):
	if n < 2:
		return n
	else:
		return fibonacci(n - 1) + fibonacci(n - 2)
```

It's a better implementation than the last one, because it allows us to use the first example (the clearer one) for fibonacci while having a great performance and keeping the concepts orthogonal, that is, we have completely separate implementations for fibonacci and for memoization. You could call it aspect oriented programming.

### Conclusion

No conclusions. What are your favorite algorithms to try on new languages?
