
# Table of Contents

1.  [Build-in object preview](#orgb22cb5b)
2.  [Immutability](#org14b55fc)
3.  [bytearray](#org87f4b43)
4.  [泛型操作和类型操作](#org9dcc1c4)
5.  [Pattern Matching](#orgc9dc4fb)
6.  [List comprehension expression](#orge05f49a)
7.  [Dictionaries](#org85f9861)
8.  [Iteration](#orgb8e840e)
9.  [Tuples](#orgfaa2da3)
    1.  [Why Tuples?](#orgac750a0)
10. [Files](#orgebad954)
11. [Numeric Types](#org05fcad6)
    1.  [Numeric Literals](#org16e110d)
        1.  [Decimal Type](#org09f5d29)
        2.  [Fraction Type](#org292b089)
    2.  [IMMUTABLE CONSTRAINTS AND FROZEN SETS](#org69075da)
        1.  [WHY SETS?](#org2a6aed2)
    3.  [Booleans](#org4860be9)
12. [Dynamic Type(动态类型)](#org1f85bea)
    1.  [Shared References](#org62028b1)
    2.  [Shared References and In-Place Changes](#org8ff4066)
    3.  [Shared References and Equality](#orgc35c749)
    4.  [Dynamic Typing Is Everywhere](#org05e686a)
    5.  [“WEAK” REFERENCES](#orgca947cd)
13. [String Fundamentals](#org1e795a5)
    1.  [Unicode: The Short Story](#orgc9b9866)
    2.  [String Basics](#org7062515)
    3.  [String Literals](#org6082f4d)
        1.  [Single- and Double-Quoted Strings Are the Same](#org636f342)
        2.  [Escape Sequences Represent Special Characters](#org9555f3a)
        3.  [Raw Strings Suppress Escapes](#org16aba31)
        4.  [Triple Quotes Code Multiline Block Strings](#org139ea34)
    4.  [Strings in Action](#org421388b)
        1.  [Basic Operations](#orgf30c467)
        2.  [Indexing and Slicing](#org56457cd)
        3.  [String Conversion Tools](#org7332ade)
    5.  [String Methods](#orgd913fa9)
        1.  [Methods of Strings](#orgb11c87c)
        2.  [String Method Examples: Changing Strings II](#org3440da6)
    6.  [String Formatting Expressions](#org76c69ec)
        1.  [Adding Keys, Attributes, and Offsets](#org5ea8553)
    7.  [General Type Categories](#org2a11577)
        1.  [Mutable Types Can Be Changed in Place](#org586852d)
14. [Lists and Dictionaries](#org0f5fa61)


<a id="orgb22cb5b"></a>

# Build-in object preview

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Object type</td>
<td class="org-left">Example literals/creation</td>
</tr>


<tr>
<td class="org-left">Numbers</td>
<td class="org-left">1234, 3.1415, 3+4j, 0b111, Decimal(), Fraction()</td>
</tr>


<tr>
<td class="org-left">Strings</td>
<td class="org-left">'spam', "Bob's", b'a\x01c', u'sp\xc4m'</td>
</tr>


<tr>
<td class="org-left">Lists</td>
<td class="org-left">[1, [2, 'three'], 4.5], list(range(10))</td>
</tr>


<tr>
<td class="org-left">Dictionaries</td>
<td class="org-left">{'food': 'spam', 'taste': 'yum'}, dict(hours=10)</td>
</tr>


<tr>
<td class="org-left">Tuples</td>
<td class="org-left">(1, 'spam', 4, 'U'), tuple('spam'), namedtuple</td>
</tr>


<tr>
<td class="org-left">Files</td>
<td class="org-left">open('eggs.txt'), open(r'C:\ham.bin', 'wb')</td>
</tr>


<tr>
<td class="org-left">Sets</td>
<td class="org-left">set('abc'), {'a', 'b', 'c'}</td>
</tr>


<tr>
<td class="org-left">Other core types</td>
<td class="org-left">Booleans, types, None</td>
</tr>


<tr>
<td class="org-left">Program unit types</td>
<td class="org-left">Functions, modules, classes (Part IV, Part V, Part VI)</td>
</tr>


<tr>
<td class="org-left">Implementation-related types</td>
<td class="org-left">Compiled code, stack tracebacks (Part IV, Part VII)</td>
</tr>
</tbody>
</table>


<a id="org14b55fc"></a>

# Immutability

String都是不可变的, 无法改变其中的一个值, 只能构建一个新的字符串.

Every object in Python is classified as either immutable (unchangeable) or not. In terms of the core types, numbers, strings, and tuples are immutable; lists, dictionaries, and sets are not—they can be changed in place freely, as can most new objects you’ll code with classes. 

Python中的对象要么是不可变的(numbers, strings, tuples)

要么是可变的(lists, sets, dictionaries)


<a id="org87f4b43"></a>

# TODO bytearray


<a id="org9dcc1c4"></a>

# 泛型操作和类型操作

-   泛型操作通常是函数调用, 如 `len(x)`
-   类型操作通常是对象的方法调用, 如 `s.upper()`


<a id="orgc9dc4fb"></a>

# TODO Pattern Matching


<a id="orge05f49a"></a>

# List comprehension expression

-   `[row[1] for row in M]`
-   `[row[1] for row in M if row[1] % 2 != 0]`


<a id="org85f9861"></a>

# Dictionaries


<a id="orgb8e840e"></a>

# Iteration

In a nutshell, an object is iterable if it is either a physically stored sequence in memory, or an object that generates one item at a time in the context of an iteration operation—a sort of “virtual” sequence. More formally, both types of objects are considered iterable because they support the iteration protocol—they respond to the iter call with an object that advances in response to next calls and raises an exception when finished producing values.

支持迭代协议的对象都可以迭代&#x2013;&#x2014;iter() next()


<a id="orgfaa2da3"></a>

# Tuples

Functionally, they’re used to represent fixed collections of items: the components of a specific calendar date, for instance. Syntactically, they are normally coded in parentheses instead of square brackets, and they support arbitrary types, arbitrary nesting, and the usual sequence


<a id="orgac750a0"></a>

## Why Tuples?

So, why have a type that is like a list, but supports fewer operations? Frankly, tuples are not generally used as often as lists in practice, but their immutability is the whole point. If you pass a collection of objects around your program as a list, it can be changed anywhere; if you use a tuple, it cannot. That is, tuples provide a sort of integrity constraint that is convenient in programs larger than those we’ll write here. We’ll talk more about tuples later in the book, including an extension that builds upon them called named tuples. For now, though, let’s jump ahead to our last major core type: the file.


<a id="orgebad954"></a>

# Files


<a id="org05fcad6"></a>

# Numeric Types

-   Integer and floating-point objects
-   Complex number objects
-   Decimal: fixed-precision objects
-   Fraction: rational number objects
-   Sets: collections with numeric operations
-   Booleans: true and false
-   Built-in functions and modules: round, math, random, etc.
-   Expressions; unlimited integer precision; bitwise operations; hex, octal, and binary formats
-   Third-party extensions: vectors, libraries, visualization, plotting, etc.


<a id="org16e110d"></a>

## Numeric Literals


<a id="org09f5d29"></a>

### Decimal Type

    In [5]: from decimal import Decimal
    
    In [6]: Decimal(0.1)
    Out[6]: Decimal('0.1000000000000000055511151231257827021181583404541015625')
    
    In [7]: Decimal(0.1) + Decimal(0.1) + Decimal(0.1)
    Out[7]: Decimal('0.3000000000000000166533453694')
    
    In [8]: Decimal(0.1) + Decimal(0.1) + Decimal(0.1) - Decimal(0.3)
    Out[8]: Decimal('2.775557561565156540423631668E-17')
    
    In [9]: Decimal('0.1') + Decimal('0.1') + Decimal('0.1') - Decimal('0.3')
    Out[9]: Decimal('0.0')

**可以用来表示经济, 钱**

    >>> 1999 + 1.33      # This has more digits in memory than displayed in 3.3
    2000.33
    >>>
    >>> decimal.getcontext().prec = 2
    >>> pay = decimal.Decimal(str(1999 + 1.33))
    >>> pay
    Decimal('2000.33')


<a id="org292b089"></a>

### Fraction Type


<a id="org69075da"></a>

## IMMUTABLE CONSTRAINTS AND FROZEN SETS

Sets are powerful and flexible objects, but they do have one constraint in both 3.X and 2.X that you should keep in mind—largely because of their implementation, sets can only contain immutable (a.k.a. “hashable”) object types. Hence, lists and dictionaries cannot be embedded in sets, but tuples can if you need to store compound values. Tuples compare by their full values when used in set operations:

Sets中只能放不可变的(hashable)对象, 所以list和dict是不能放到里面的.而可以将Tuple放到Set中

    >>> S
    {1.23}
    >>> S.add([1, 2, 3])                   # Only immutable objects work in a set
    TypeError: unhashable type: 'list'
    >>> S.add({'a':1})
    TypeError: unhashable type: 'dict'
    >>> S.add((1, 2, 3))
    >>> S                                  # No list or dict, but tuple OK
    {1.23, (1, 2, 3)}
    
    >>> S | {(4, 5, 6), (1, 2, 3)}         # Union: same as S.union(...)
    {1.23, (4, 5, 6), (1, 2, 3)}
    >>> (1, 2, 3) in S                     # Membership: by complete values
    True
    >>> (1, 4, 3) in S
    False

Sets themselves are mutable too, and so cannot be nested in other sets directly; if you need to store a set inside another set, the frozenset built-in call works just like set but creates an immutable set that cannot change and thus can be embedded in other sets.

Sets自身是可变的, 因此也不能嵌套在其他Set中. 但是可以使用 `frozenset()` 方法将一个set对象固化

    In [12]: s = set()
    
    In [13]: s.add(1)
    
    In [14]: s.add(2)
    
    In [15]: s
    Out[15]: {1, 2}
    
    In [16]: ss = frozenset(s)
    
    In [17]: s.add(ss)
    
    In [18]: s
    Out[18]: {1, 2, frozenset({1, 2})}


<a id="org2a6aed2"></a>

### WHY SETS?

1.  过滤重复项
    
    list->set->list
    
        >>> L = [1, 2, 1, 3, 2, 4, 5]
        >>> set(L)
        {1, 2, 3, 4, 5}
        >>> L = list(set(L))                                  # Remove duplicates
        >>> L
        [1, 2, 3, 4, 5]
        
        >>> list(set(['yy', 'cc', 'aa', 'xx', 'dd', 'aa']))   # But order may change
        ['cc', 'xx', 'yy', 'dd', 'aa']

2.  比较list, string等其他可迭代对象的不同
    
    set1 - set2
    
        >>> set([1, 3, 5, 7]) - set([1, 2, 4, 5, 6])          # Find list differences
        {3, 7}
        >>> set('abcdefg') - set('abdghij')                   # Find string differences
        {'c', 'e', 'f'}
        >>> set('spam') - set(['h', 'a', 'm'])                # Find differences, mixed
        {'p', 's'}
        
        >>> set(dir(bytes)) - set(dir(bytearray))             # In bytes but not bytearray
        {'__getnewargs__'}
        >>> set(dir(bytearray)) - set(dir(bytes))
        {'append', 'copy', '__alloc__', '__imul__', 'remove', 'pop', 'insert', ...more...]

3.  只关心collection的内容, 不关心顺序的时候用来比较是否相同
    
        	 >>> L1, L2 = [1, 3, 5, 2, 4], [2, 5, 3, 4, 1]
        ]	 >>> L1 == L2                                          # Order matters in sequences
        	 False
        	 >>> set(L1) == set(L2)                                # Order-neutral equality
        	 True
        	 >>> sorted(L1) == sorted(L2)                          # Similar but results ordered
        	 True
        	 >>> 'spam' == 'asmp', set('spam') == set('asmp'), sorted('spam') == sorted('asmp')
        	 (False, True, True)

4.  遍历图或循环结构是用于记录是否已经处理过当前节点
    
    Sets can also be used to keep track of where you’ve already been when traversing a graph or other cyclic structure. For example, the transitive module reloader and inheritance tree lister examples we’ll study in Chapter 25 and Chapter 31, respectively, must keep track of items visited to avoid loops, as Chapter 19 discusses in the abstract. Using a list in this context is inefficient because searches require linear scans. Although recording states visited as keys in a dictionary is efficient, sets offer an alternative that’s essentially equivalent (and may be more or less intuitive, depending on whom you ask).

1.  用来处理大的数据集时∩和∪特别有用
    sets are also convenient when you’re dealing with large data sets (database query results, for example)—the intersection of two sets contains objects common to both categories, and the union contains all items in either set.
    
        >>> engineers = {'bob', 'sue', 'ann', 'vic'}
        >>> managers  = {'tom', 'sue'}
        
        >>> 'bob' in engineers                   # Is bob an engineer?
        True
        
        >>> engineers & managers                 # Who is both engineer and manager?
        {'sue'}
        
        >>> engineers | managers                 # All people in either category
        {'bob', 'tom', 'sue', 'vic', 'ann'}
        
        >>> engineers - managers                 # Engineers who are not managers
        {'vic', 'ann', 'bob'}
        
        >>> managers - engineers                 # Managers who are not engineers
        {'tom'}
        
        >>> engineers > managers                 # Are all managers engineers? (superset)
        False
        
        >>> {'bob', 'sue'} < engineers           # Are both engineers? (subset)
        True
        
        >>> (managers | engineers) > managers    # All people is a superset of managers
        True
        
        >>> managers ^ engineers                 # Who is in one but not both?
        {'tom', 'vic', 'ann', 'bob'}
        
        >>> (managers | engineers) - (managers ^ engineers)     # Intersection!
        {'sue'}


<a id="org4860be9"></a>

## Booleans

数值上是1和0, 但是是bool类的实例

    >>> type(True)
    <class 'bool'>
    >>> isinstance(True, int)
    True
    >>> True == 1                # Same value
    True
    >>> True is 1                # But a different object: see the next chapter
    False
    >>> True or False            # Same as: 1 or 0
    True
    >>> True + 4                 # (Hmmm)
    5


<a id="org1f85bea"></a>

# Dynamic Type(动态类型)

![img](./img/lp5e_0601.png)

变量和对象的关系:

Names (a.k.a. variables) and objects after running the assignment a = 3. Variable a becomes a reference to the object 3. Internally, the variable is really a pointer to the object’s memory space created by running the literal expression 3.

-   Variables are entries in a system table, with spaces for links to objects.

-   Objects are pieces of allocated memory, with enough space to represent the values for which they stand.

-   References are automatically followed pointers from variables to objects.

Technically speaking, objects have more structure than just enough space to represent their values. Each object also has two standard header fields: a type designator used to mark the type of the object, and a reference counter used to determine when it’s OK to reclaim the object. 

技术上说, 对象不仅仅只包含values的空间, 至少还包含两个额外的东西: 类型指示符和引用计数器.

**Types Live with Objects, Not Variables**

**Objects Are Garbage-Collected**


<a id="org62028b1"></a>

## Shared References

    >>> a = 3
    >>> b = a

![img](./img/lp5e_0602.png)

Names and objects after next running the assignment b = a. Variable b becomes a reference to the object 3. Internally, the variable is really a pointer to the object’s memory space created by running the literal expression 3.

![img](./img/lp5e_0603.png)

Names and objects after finally running the assignment a = ‘spam’. Variable a references the new object (i.e., piece of memory) created by running the literal expression ‘spam’, but variable b still refers to the original object 3. Because this assignment is not an in-place change to the object 3, it changes only variable a, not b.


<a id="org8ff4066"></a>

## Shared References and In-Place Changes

    import copy
    X = copy.copy(Y)          # Make top-level "shallow" copy of any object Y
    X = copy.deepcopy(Y)      # Make deep copy of any object Y: copy all nested parts


<a id="orgc35c749"></a>

## Shared References and Equality

    >>> L = [1, 2, 3]
    >>> M = L                 # M and L reference the same object
    >>> L == M                # Same values
    True
    >>> L is M                # Same objects
    True

The first technique here, the **==** operator, tests whether the two referenced objects have the **same values**; this is the method almost always used for equality checks in Python. The second method, the is operator, instead tests for object identity—it returns True only if both names point to the exact same object, so it is a much stronger form of equality testing and is rarely applied in most programs.

Really, **is** simply compares the pointers that implement references, and it serves as a way to detect shared references in your code if needed. It returns False if the names point to equivalent but different objects, as is the case when we run two different literal expressions:

    >>> L = [1, 2, 3]
    >>> M = [1, 2, 3]         # M and L reference different objects
    >>> L == M                # Same values
    True
    >>> L is M                # Different objects
    False

    >>> X = 42
    >>> Y = 42                # Should be two different objects
    >>> X == Y
    True
    >>> X is Y                # Same object anyhow: caching at work!
    True

the `getrefcount` function in the standard sys module returns the object’s reference count. When I ask about the integer object 1 in the IDLE GUI, for instance, it reports 647 reuses of this same object (most of which are in IDLE’s system code, not mine, though this returns 173 outside IDLE so Python must be hoarding 1s as well):


<a id="org05e686a"></a>

## Dynamic Typing Is Everywhere


<a id="orgca947cd"></a>

## “WEAK” REFERENCES

You may occasionally see the term “weak reference” in the Python world. This is a somewhat advanced tool, but is related to the reference model we’ve explored here, and like the `is` operator, can’t really be understood without it.

In short, a weak reference, implemented by the `weakref` standard library module, is a reference to an object that does not by itself prevent the referenced object from being garbage-collected. If the last remaining references to an object are weak references, the object is reclaimed and the weak references to it are automatically deleted (or otherwise notified).

This can be useful in dictionary-based caches of large objects, for example; otherwise, the cache’s reference alone would keep the object in memory indefinitely. Still, this is really just a special-case extension to the reference model. For more details, see Python’s library manual.


<a id="org1e795a5"></a>

# String Fundamentals

**string** — an ordered collection of characters used to store and represent text- and bytes-based information. 


<a id="orgc9b9866"></a>

## Unicode: The Short Story

In Python 3.X there are three string types: str is used for Unicode text (including ASCII), bytes is used for binary data (including encoded text), and bytearray is a mutable variant of bytes. Files work in two modes: text, which represents content as str and implements Unicode encodings, and binary, which deals in raw bytes and does no data translation.

In fact, the primary distinction of Unicode often lies in the translation (a.k.a. encoding) step required to move it to and from files. Beyond that, it’s largely just string processing.

Unicode主要在读取和写入文件的时候才需要考虑. 其他时候用String就可以了.


<a id="org7062515"></a>

## String Basics

Python’s strings serve the same role as character arrays in languages such as C, but they are a somewhat higher-level tool than arrays. Unlike in C, in Python, strings come with a powerful set of processing tools. Also unlike languages such as C, Python **has no distinct type for individual characters**; instead, you just use **one-character strings**

Strictly speaking, Python strings are categorized as immutable sequences, meaning that the characters they contain have a left-to-right positional order and that they cannot be changed in place. In fact, strings are the first representative of the larger class of objects called sequences that we will study here. 

严格的说, Strings属于不可变序列. 


<a id="org6082f4d"></a>

## String Literals


<a id="org636f342"></a>

### Single- and Double-Quoted Strings Are the Same


<a id="org9555f3a"></a>

### Escape Sequences Represent Special Characters

The character `\`, and one or more characters following it in the string literal, are replaced with a single character in the resulting string object, which has the binary value specified by the escape sequence. 

3.X defines str strings formally as sequences of **Unicode code points**, not bytes, to make this clear.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Escape</td>
<td class="org-left">Meaning</td>
</tr>


<tr>
<td class="org-left">\newline</td>
<td class="org-left">Ignored (continuation line)</td>
</tr>


<tr>
<td class="org-left">\\\\</td>
<td class="org-left">Backslash (stores one \\)</td>
</tr>


<tr>
<td class="org-left">\\'</td>
<td class="org-left">Single quote (stores ')</td>
</tr>


<tr>
<td class="org-left">\\"</td>
<td class="org-left">Double quote (stores ")</td>
</tr>


<tr>
<td class="org-left">\a</td>
<td class="org-left">Bell</td>
</tr>


<tr>
<td class="org-left">\b</td>
<td class="org-left">Backspace</td>
</tr>


<tr>
<td class="org-left">\f</td>
<td class="org-left">Formfeed</td>
</tr>


<tr>
<td class="org-left">\n</td>
<td class="org-left">Newline (linefeed)</td>
</tr>


<tr>
<td class="org-left">\r</td>
<td class="org-left">Carriage return</td>
</tr>


<tr>
<td class="org-left">\t</td>
<td class="org-left">Horizontal tab</td>
</tr>


<tr>
<td class="org-left">\v</td>
<td class="org-left">Vertical tab</td>
</tr>


<tr>
<td class="org-left">\xhh</td>
<td class="org-left">Character with hex value hh (exactly 2 digits)</td>
</tr>


<tr>
<td class="org-left">\ooo</td>
<td class="org-left">Character with octal value ooo (up to 3 digits)</td>
</tr>


<tr>
<td class="org-left">\\0</td>
<td class="org-left">Null: binary 0 character (doesn’t end string)</td>
</tr>


<tr>
<td class="org-left">\N{ id }</td>
<td class="org-left">Unicode database ID</td>
</tr>


<tr>
<td class="org-left">\uhhhh</td>
<td class="org-left">Unicode character with 16-bit hex value</td>
</tr>


<tr>
<td class="org-left">\Uhhhhhhh</td>
<td class="org-left">Unicode character with 32-bit hex valuea</td>
</tr>


<tr>
<td class="org-left">\other</td>
<td class="org-left">Not an escape (keeps both \\ and other)</td>
</tr>
</tbody>
</table>

    >>> s = 'a\0b\0c'
    >>> s
    'a\x00b\x00c'
    >>> len(s)
    5

In Python, a zero (null) character like this does not terminate a string the way a “null byte” typically does in C. Instead, Python keeps both the string’s length and text in memory. In fact, no character terminates a string in Python. Here’s a string that is all absolute binary escape codes—a binary 1 and 2 (coded in octal), followed by a binary 3 (coded in hexadecimal):

    >>> s = '\001\002\x03'
    >>> s
    '\x01\x02\x03'
    >>> len(s)
    3


<a id="org16aba31"></a>

### Raw Strings Suppress Escapes

    >>> path = r'C:\new\text.dat'
    >>> path                          # Show as Python code
    'C:\\new\\text.dat'
    >>> print(path)                   # User-friendly format
    C:\new\text.dat
    >>> len(path)                     # String length
    15

即使是Raw Strings也不能以 `\` 结束

    In [32]: path = r'C:\new\text.dat\'
      File "<ipython-input-32-7d67db395ae9>", line 1
        path = r'C:\new\text.dat\'
    			      ^
    SyntaxError: EOL while scanning string literal

如果必须要以 `\` 结束, 那么有几个办法:

1.  truncate
    
        In [35]: path = r'C:\new\text.dat\\'[:-1]

2.  join
    
        In [38]: path = r'C:\new\text.dat' + '\\'
        
        In [39]: print(path)
        C:\new\text.dat\

3.  不要使用r'&#x2026;'


<a id="org139ea34"></a>

### Triple Quotes Code Multiline Block Strings


<a id="org421388b"></a>

## Strings in Action


<a id="orgf30c467"></a>

### Basic Operations

-   `+`
-   `*`
-   `len()`
-   `for c in s:`


<a id="org56457cd"></a>

### Indexing and Slicing

![img](./img/lp5e_0701.png)

Offsets and slices: positive offsets start from the left end (offset 0 is the first item), and negatives count back from the right end (offset −1 is the last item). Either kind of offset can be used to give positions in indexing and slicing operations.

到end但是不包含end:

    In [44]: S = 'spam'
    
    In [45]: S[-1]
    Out[45]: 'm'
    
    In [47]: S[:-1]
    Out[47]: 'spa'
    
    In [48]: S[:2]
    Out[48]: 'sp'

1.  EXTENDED SLICING: THE THIRD LIMIT AND SLICE OBJECTS

        >>> S = 'hello'
        >>> S[::−1]                            # Reversing items
        'olleh'
    
        >>> S = 'abcedfg'
        >>> S[5:1:−1]                          # Bounds roles differ
        'fdec'
    
        >>> 'spam'[1:3]                        # Slicing syntax
        'pa'
        >>> 'spam'[slice(1, 3)]                # Slice objects with index syntax + object
        'pa'
        >>> 'spam'[::-1]
        'maps'
        >>> 'spam'[slice(None, None, −1)]
        'maps'
    
    1.  WHY YOU WILL CARE: SLICES
    
            # File echo.py
            import sys
            print(sys.argv)
            
            % python echo.py −a −b −c
            ['echo.py', '−a', '−b', '−c']
        
        a single slice expression can be used to return all but the first item of a list. Here, `sys.argv[1:]` returns the desired list, ['−a', '−b', '−c']. You can then process this list without having to accommodate the program name at the front.


<a id="org7332ade"></a>

### String Conversion Tools

    >>> int("42"), str(42)          # Convert from/to string
    (42, '42')
    >>> repr(42)                    # Convert to as-code string
    '42'

The int function converts a string to a number, and the str function converts a number to its string representation (essentially, what it looks like when printed). The repr function (and the older backquotes expression, removed in Python 3.X) also converts an object to its string representation, but returns the object as a string of code that can be rerun to recreate the object.

1.  CHARACTER CODE CONVERSIONS

        >>> S = '5'
        >>> S = chr(ord(S) + 1)
        >>> S
        '6'
        >>> S = chr(ord(S) + 1)
        >>> S
        '7'
    
        >>> B = '1101'                 # Convert binary digits to integer with ord
        >>> I = 0
        >>> while B != '':
        ...     I = I * 2 + (ord(B[0]) - ord('0'))
        ...     B = B[1:]
        ...
        >>> I
        13
    
        >>> int('1101', 2)             # Convert binary to integer: built-in
        13
        >>> bin(13)                    # Convert integer to binary: built-in
        '0b1101'
    
        >>> 'That is %d %s bird!' % (1, 'dead')           # Format expression: all Pythons
        That is 1 dead bird!
        >>> 'That is {0} {1} bird!'.format(1, 'dead')     # Format method in 2.6, 2.7, 3.X
        'That is 1 dead bird!'


<a id="orgd913fa9"></a>

## String Methods


<a id="orgb11c87c"></a>

### Methods of Strings

Table 7-3. String method calls in Python 3.3

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">S.capitalize()</td>
<td class="org-left">S.ljust(width [, fill])</td>
</tr>


<tr>
<td class="org-left">S.casefold()</td>
<td class="org-left">S.lower()</td>
</tr>


<tr>
<td class="org-left">S.center(width [, fill])</td>
<td class="org-left">S.lstrip([chars])</td>
</tr>


<tr>
<td class="org-left">S.count(sub [, start [, end]])</td>
<td class="org-left">S.maketrans(x[, y[, z]])</td>
</tr>


<tr>
<td class="org-left">S.encode([encoding [,errors]])</td>
<td class="org-left">S.partition(sep)</td>
</tr>


<tr>
<td class="org-left">S.endswith(suffix [, start [, end]])</td>
<td class="org-left">S.replace(old, new [, count])</td>
</tr>


<tr>
<td class="org-left">S.expandtabs([tabsize])</td>
<td class="org-left">S.rfind(sub [,start [,end]])</td>
</tr>


<tr>
<td class="org-left">S.find(sub [, start [, end]])</td>
<td class="org-left">S.rindex(sub [, start [, end]])</td>
</tr>


<tr>
<td class="org-left">S.format(fmtstr, \*args, \*\*kwargs)</td>
<td class="org-left">S.rjust(width [, fill])</td>
</tr>


<tr>
<td class="org-left">S.index(sub [, start [, end]])</td>
<td class="org-left">S.rpartition(sep)</td>
</tr>


<tr>
<td class="org-left">S.isalnum()</td>
<td class="org-left">S.rsplit([sep[, maxsplit]])</td>
</tr>


<tr>
<td class="org-left">S.isalpha()</td>
<td class="org-left">S.rstrip([chars])</td>
</tr>


<tr>
<td class="org-left">S.isdecimal()</td>
<td class="org-left">S.split([sep [,maxsplit]])</td>
</tr>


<tr>
<td class="org-left">S.isdigit()</td>
<td class="org-left">S.splitlines([keepends])</td>
</tr>


<tr>
<td class="org-left">S.isidentifier()</td>
<td class="org-left">S.startswith(prefix [, start [, end]])</td>
</tr>


<tr>
<td class="org-left">S.islower()</td>
<td class="org-left">S.strip([chars])</td>
</tr>


<tr>
<td class="org-left">S.isnumeric()</td>
<td class="org-left">S.swapcase()</td>
</tr>


<tr>
<td class="org-left">S.isprintable()</td>
<td class="org-left">S.title()</td>
</tr>


<tr>
<td class="org-left">S.isspace()</td>
<td class="org-left">S.translate(map)</td>
</tr>


<tr>
<td class="org-left">S.istitle()</td>
<td class="org-left">S.upper()</td>
</tr>


<tr>
<td class="org-left">S.isupper()</td>
<td class="org-left">S.zfill(width)</td>
</tr>


<tr>
<td class="org-left">S.join(iterable)</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="org3440da6"></a>

### String Method Examples: Changing Strings II

    >>> S = 'xxxxSPAMxxxxSPAMxxxx'
    >>> S.replace('SPAM', 'EGGS')         # Replace all
    'xxxxEGGSxxxxEGGSxxxx'
    
    >>> S.replace('SPAM', 'EGGS', 1)      # Replace one
    'xxxxEGGSxxxxSPAMxxxx'

    >>> line = 'bob,hacker,40'
    >>> line.split(',')
    ['bob', 'hacker', '40']

    >>> line = "i'mSPAMaSPAMlumberjack"
    >>> line.split("SPAM")
    ["i'm", 'a', 'lumberjack']


<a id="org76c69ec"></a>

## String Formatting Expressions

    >>> template = '{0}, {1} and {2}'                             # By position
    >>> template.format('spam', 'ham', 'eggs')
    'spam, ham and eggs'
    
    >>> template = '{motto}, {pork} and {food}'                   # By keyword
    >>> template.format(motto='spam', pork='ham', food='eggs')
    'spam, ham and eggs'
    
    >>> template = '{motto}, {0} and {food}'                      # By both
    >>> template.format('ham', motto='spam', food='eggs')
    'spam, ham and eggs'
    
    >>> template = '{}, {} and {}'                                # By relative position
    >>> template.format('spam', 'ham', 'eggs')                    # New in 3.1 and 2.7
    'spam, ham and eggs'


<a id="org5ea8553"></a>

### Adding Keys, Attributes, and Offsets

    >>> import sys
    
    >>> 'My {1[kind]} runs {0.platform}'.format(sys, {'kind': 'laptop'})
    'My laptop runs win32'
    
    >>> 'My {map[kind]} runs {sys.platform}'.format(sys=sys, map={'kind': 'laptop'})
    'My laptop runs win32'


<a id="org2a11577"></a>

## General Type Categories

-   Numbers (integer, floating-point, decimal, fraction, others)
    
    Support addition, multiplication, etc.

-   Sequences (strings, lists, tuples)
    
    Support indexing, slicing, concatenation, etc.

-   Mappings (dictionaries)
    
    Support indexing by key, etc.


<a id="org586852d"></a>

### Mutable Types Can Be Changed in Place

-   Immutables (numbers, strings, tuples, frozensets)
    
    None of the object types in the immutable category support in-place changes, though we can always run expressions to make new objects and assign their results to variables as needed.

-   Mutables (lists, dictionaries, sets, bytearray)
    
    Conversely, the mutable types can always be changed in place with operations that do not create new objects. Although such objects can be copied, in-place changes support direct modification.


<a id="org0f5fa61"></a>

# Lists and Dictionaries

