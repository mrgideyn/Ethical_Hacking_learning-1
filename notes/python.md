# Section 21 : python bases
## datatype
- native : int, float, bool, str, list, tuple, set, dict, complex
- classes = custom types
- spezialized data types (module.*)
- None (=NULL)


# operators
`a ** b` = a^b
`a // b` = a/b round to lower integer
`a % b` = modulo (reste division euclienne -> a//b)

# math functions
https://docs.python.org/3
round(), abs(), https://docs.python.org/3/library/math.html#module-math
bin()

# variables

# expressions VS statement
- expression : "50/5", piece of code that produce value/results
- statement : line of code doing an action (var assign, etc.)

# Augmented assignment operator (+=, -=, etc)

# type conversion
str(), int()

# formatted string
```
vara='ddd'
varb='fff'
print(f'{vara} {varb}')
```

# string index
```
vara='ttrtaratat'
print(vara[2])
print(vara[2:5])
print(vara[start:stop:stepover])
print(vara[::-1]) #reverse string
```
**WARNING : string index starts at 1, not 0**

# Immutability
string in python are immutable (possible to reassign, but not modify)

## [builtin functions](https://docs.python.org/3/library/functions.html)
```
vara='azerty'
varb=vara.len()
```

possible to embed function in print fcuntion with f option :
```
print(f'{vara} {len(varb)}')
```
