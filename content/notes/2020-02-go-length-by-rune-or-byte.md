---
title: 'Go: Length by Rune or Byte?'
date: 2020-02-20T02:30:45.293Z
tags:
  - til
---
If I need to find the length of a string, I use built-in function `len`.
At first I thought it returns the number of character, but actually it returns length of byte of the string.

```
	s := `something`
	println(len(s)) // return 9
```
this will print 9

but it will be different if I use utf8 chars

```
	s2 := "hétérogénéité"
	println(len(s2)) // return 18
```
this one return 18, because é is 2 bytes long and `len` is counting byte not char

so, if we want count chars in a string, we can use `utf8.RuneCountInString`

```
	s2 := "hétérogénéité"
	println(utf8.RuneCountInString(s2)) // return 13
```
