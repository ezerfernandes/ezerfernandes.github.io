---
layout: post
title: "How to make truly private attributes in Python objects"
date: 2017-04-12
---

A colleague, coming from C#, asked me, *"how can you make an attribute truly private in Python?"* I think it's almost never necessary.

I thought of a case where it could be necessary: Imagine you want to create an user object, with username and password, and you want to be able to check if a password is valid, but you do want it to be unaccessible (maybe you'll pass this object to another program which code you don't control.) That's how I would do it:

<pre><code class="python">
import hashlib


class User:
    def __init__(self, username, password):
        self.username = username
        def _gen_hash(txt):
            return hashlib.sha224(txt).hexdigest()
        hash = _gen_hash(password)
        def _check_password(password):
            '''Check if the password is correct'''
            return hash == _gen_hash(password)
        self.check_password = _check_password

</code></pre>

Actually, I wouldn't do it like this, I would use a function. Here you can see that _gen_hash (the function that generates the hash) is also unaccessible. It makes the algorithm used to do hashing also unaccessible. Now how I would use this class:

<pre><code class="python">
user1 = User(username="ezerfernandes", password="abracadabra")

def some_foreign_code(user, pwd):
    # ...
    if user.check_password(pwd):
        # Do something
        print("You're authorized. Welcome!")
    else:
        print("You're not authorized. Try again")

some_foreign_code(user1, "foobar") # WRONG PASSWORD!
some_foreign_code(user1, "abacadabra") # RIGHT!

</code></pre>
