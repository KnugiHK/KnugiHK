# Bytes in Python 2 & 3
Recently, I'm working on converting a rtmp server from Python 2 and Python 3. Most of the syntax can be converted by using a built in tools called "2to3.py", but some cannot. One typical example is Bytes type.

In Python 2, a byte is simply a string. However, in Python 3 bytes does not equal to string, they are different, hence, we need to add a 'b' sign before a string to make the object be a Bytes.
```Python
# Python 2
>>> 'Foo\x06\x08' # this can be a bytes and a string

# Python 3
>>> 'Foo\x06\x08' # this is a string
>>> b'Foo\x06\x08' # this is a bytes
```
The representation is also changed because string and bytes are separated. In Python 2, whenever we need to get the integer value of a byte, we need to use ord() to convert the byte to integer. But in Python 3, we don't

```Python
# Python 2
>>> foo = '\x08'
>>> foo[0] # read the first byte and the only byte in foo
'\x08'
>>> ord('\x08') # we need to use ord to convert it to an integer
8

# Python 3
>>> foo = b'\x08'
>>> a[0] # also read the first byte and the only byte in foo
8
```
That's mean we need to remove ord() when converting Python 2 code in Python 3.

So, when we need to convert a network related program from Python 2 to Python 3, we need to take extra caution about bytes.

# Metadata
*This post was originally posted in 2020 May 26*

*[Bytes In Python 2 & 3 Comment Section](https://github.com/KnugiHK/KnugiHK/discussions/3)*
