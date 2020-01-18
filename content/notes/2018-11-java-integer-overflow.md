---
title: Java Integer Overflow
date: 2018-11-29T10:41:28.412Z
tags: ["til"]
---
```
public static void main(String[] args) {
  final long MICROS_PER_DAY = 24 * 60 * 60 * 1000 * 1000;
  final long MILLIS_PER_DAY = 24 * 60 * 60 * 1000;
  System.out.println(MICROS_PER_DAY / MILLIS_PER_DAY);
}
```

At the first glance, we might guess the output is 1000. NO, its not!
The output is 5!

Why?

It's because of overflow on computation process. All values are int type, not long. If we multiply two int values, we get another int value. 

To fix that problem, we need use long type on computation process. 

```
public static void main(String[] args) {
  final long MICROS_PER_DAY = 24 * 60 * 60 * 1000 * 1000L;
  final long MILLIS_PER_DAY = 24 * 60 * 60 * 1000L;
  System.out.println(MICROS_PER_DAY / MILLIS_PER_DAY);
}
```
