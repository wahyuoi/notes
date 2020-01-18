---
title: Java Integer Cache
date: 2018-11-27T10:42:32.318Z
tags: ["til"]
---
`Integer a = 25;` equals to `Integer a = Integer.valueOf(25);`, it's called Auto Boxing and happens on compilation time.

Integer class maintains an internal IntegerCache, ranges from `-128 to 127`

Integer.valueOf will use IntegerCache if its in range of -128 to 127. other than that, Integer will create new Integer object.

```
  public static Integer valueOf(int var0) {
    return var0 >= -128 && var0 <= Integer.IntegerCache.high ? Integer.IntegerCache.cache[var0 + 128] : new Integer(var0);
  }
```
