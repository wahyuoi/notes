---
title: Java Logical Operator
date: 2018-11-27T10:43:13.318Z
tags: ["til"]
---
The `&&` and `||` logical operators, meaning they don't evaluate the right hand side if it isn't necessary. Also called as `short-circuit` logical operator.

The `&` and `|` operators, when used as logical operators, always evaluate both sides.

```
  public static void main(String[] args) {
    if (singleDigit(1) & singleDigit(22)) {
      System.out.println("OK");
    }
  }

  private static boolean singleDigit(int ii) {
    System.out.println("number: " + ii);
    return ii<10;
  }
```

The above code will print

```
number: 1
number: 22
```
