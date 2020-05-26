---
title: "Go: Interface Resolution"
date: 2020-05-26T08:12:32.691Z
tags:
  - til
---
In Go **interface resolution is implicit**. If the type you pass in matches what the interface is asking for, it will compile.

```go
type Shape interface {
	Area() float64
}

type Shape2 interface {
	Area() float64
	Diameter() float64
}

type Rectangle struct {
	Width float64
	Height float64
}

func (r Rectangle) Area() float64 {
	return r.Width * r.Height
}

type Circle struct {
	Radius float64
}

func (c Circle) Area() float64 {
	return math.Pow(c.Radius, 2) * math.Pi
}

func (c Circle) Diameter() float64 {
	return c.Radius*2
}

func (c Circle) Temp() string {
	return ""
}
```

With these code, we can see that
- Rectangle can match with interface Shape, because Rectangle implement function Area()
- Circle can match with both interface Shape and Shape2, because Circle implement function Area() and Diameter()