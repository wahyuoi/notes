---
title: 'Go: Equals ignore case'
date: 2020-02-15T04:13:38.446Z
tags:
  - til
---
Comparing 2 strings ignoring case can be achieved using 2 approaches:
- make it lower/upper case than compare it
- using `strings.EqualFold`

sample benchmark code for both approaches
```
package main

import (
	"strings"
	"testing"
)

func getData() (x string, y string) {
	x = "ASDasd"
	y = "asdASD"
	return
}

func Benchmark_toLower(b *testing.B) {
	x, y := getData()
	for i := 0; i < b.N; i++ {
		if strings.ToLower(x) == strings.ToLower(y) {
		}
	}
}

func Benchmark_EqualFold(b *testing.B) {
	x, y := getData()
	for i := 0; i < b.N; i++ {
		if strings.EqualFold(x, y) {
		}
	}
}

```

Here the benchmark result:
```
Benchmark_toLower-12            11565530                99.8 ns/op            16 B/op          2 allocs/op
Benchmark_EqualFold-12          72237980                16.3 ns/op             0 B/op          0 allocs/op

```
