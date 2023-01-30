# C language basics

## Data types in C

| Data Type | Range |
|-----------|-------|
| int | -2^31 - 2^31 -1 |
| unsigned int | 0 - 2^32^ -1 |
| char | -128 - 127 |
| float | eg. 3.14 |
| double | like float, can store bigger nums |
| void | type =/= data type |

## CS50 library

| function | return |
|-----------|-------|
| bool | true/false |
| string (char*) | eg. "hello" |
| get_char | char input |
| get_double | double input |
| get_int | int input |
| get_float | float input |
| get_long | long input |
| get_string | string input |

## Arithmetic operations

| operator | operation |
|----------|-----------|
| + | add |
| - | substract |
| * | multiply |
| / | divide |
| % | modulo |
| x = x * 5 | x *= 5 |
| x = x + 1 | x++ |

## Boolean expressions

| expression | result |
|------------|--------|
| AND (&&) | x and y true |
| OR (\|\|) | x or y or both true |
| NOT (!) | x = true !x = false; |
| less than | x < y |
| less than or equal | x <= y |
| greater than | x > y |
| greater than or equal | x >= y |
| equality | x == y |
| inequality | x != y |

## Conditionals
```if construct```
```C
if (condition)
{
  ...
}
```
```if-else construct```
```C
if (condition)
{
  ...
}
else
{

}
```
```if-elseif-else construct```
```C
if (condition)
{
  ...
}
else if (diffect condition)
{

}
else
{

}
```
```switch construct```
```C
switch (variable)
{
  case 1:
    ...;
    break;
  case 2:
    ...;
    break;
  case 3:
    ...;
    break;
  default:
    ...;
}
```
```ternary operator```
```C
int x;
if (condition)
{
  x = 5;
}
else
{
  x = 6;
}
```
is the same as
```C
int x = (condition) ? 5 : 6;
```

# Loops
```while``` loop executes only if condition is true
```C
while (condition)
{
  ... // repeats until condition is false
}
```
```do-while``` loop executes is the same as ```while``` loop, but exectues at least once before checking the condition
```C
do
{
  ... // executes once, then repeats until condition is false
}
```
```for``` loop executes a set amount of times
```C
for (int i = 0; i < 10; i++)
{
  ... // loop executes 10 times
}
```
```C
for (start; condition; increment)
{
  ... // loop until condition false
}
```

# Command line

| unix | windows | purpose |
|------|---------|---------|
| ls | dir | show all files in the directory |
| cd | cd | change directory |
| pwd | echo %cd% | write full path name |
| mkdir | mkdir / md | create directory |
| cp | copy | create duplicate of the file |
| cp -r | xcopy /E | create duplicate of the entire directory |
| rm -rf | rd /s /q | remove directory with everything |
| mv | move | move and rename file from src to dir |