---
layout: post
title: "Functional programming with Lua"
date: 2017-02-18
---

[[2016-08-11-favorite-hello-world]]


Lua is a fun language. It is used for embedded scripts, like games etc. It is also fast and it is easy to integrate C modules into it. One fun fact: it was created because there were trade restrictions for software in Brazil at the time, so instead of "importing" software, they created their own language. Crazy right?

I created [FunkMoon](https://github.com/ezerfernandes/funkmoon) (Lua means Moon in Portuguese) more as an exercise of implementing a functional style of programming in Lua. It is a collection of functions that allows you to code in a functional style. You can use it as standalone functions, like:

```lua
local funkmoon = require "funkmoon"

local list = {1, 2, -3, 4}

-- Returns only even numbers.
local even = funkmoon.filter(list, function(n) return n % 2 == 0 end)
```

Or you can use a fluent style of programming, because it returns a Table (another fun fact: a Table - a hash table on steroids - is the only built-in data structure in Lua) and this table has a metatable that allows to work like:

```lua
local funkmoon = require "funkmoon"

local list = funkmoon.FunctionalTable({1, 2, -3, 4, 9, 8})

-- Returns the sum of the squares of even numbers.
local sumOfSquaresEvenNumbers = list
        :filter(function(n) return n % 2 == 0 end)
        :map(function(n) return n*n end)
        :reduce(function(a, b) return a + b end)
```

I have a confession to make: I was heavily inspired by the collection of methods in [Scala iterables](https://www.scala-lang.org/api/current/scala/collection/AbstractIterable.html), that are very comprehensive.

I hope you enjoy it as much as I did!
