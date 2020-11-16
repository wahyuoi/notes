---
title: "Golang: Check sizeof data type"
date: 2020-11-16T09:33:55.085Z
tags:
  - til
---
A boolean can store either True or False as value. It will reserve 1 byte memory.

Here how to check the size of any type:

```go
func Test(t *testing.T) {
	fmt.Println(unsafe.Sizeof(false)) // 1 byte
	fmt.Println(unsafe.Sizeof(int8(1))) // 1 byte
	fmt.Println(unsafe.Sizeof(int16(1))) // 2 byte
	fmt.Println(unsafe.Sizeof(int32(1))) // 4 byte
	fmt.Println(unsafe.Sizeof(int64(1))) // 8 byte
}
```



So if you have more than 1 boolean variable, you can merge it into 1 integer and use bitwise operation. This will reduce number of varibale passing around



```go
// from this
func Before() {
	var hasNumber = checkNumber()
	var hasAlphabet = checkAlpabet()
	
	if hasAlphabet && hasNumber {
		// do something
	}
}

// to this
func After() {
	const flag_number = 0x01
	const flag_alphabet = 0x10
	
	var flag int8 = checkFlag()
	
	if flag & flag_number == flag_number && flag & flag_alphabet == flag_alphabet {
		// do something
	}
}
```