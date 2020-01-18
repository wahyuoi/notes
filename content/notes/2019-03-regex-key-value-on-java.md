---
title: Regex Key Value on Java
date: 2019-03-19T10:43:50.318Z
tags: ["til"]
---
Today, one intern on my team found valuable thing. 
Given text, get some values and remove noises.

Sample text `{"node"=>"8.11","java"=>"1.8"}` and should retrieve key and value.
Expected result
```
node 8.11
java 1.8
```

Using java, it can be solved by this code

```
    String regex = "\"(?<key>[.[^\"]]+)\"=>\"(?<value>[.[^\"]]+)\"";
    Pattern pattern = Pattern.compile(regex);
    Matcher matcher = pattern.matcher("{\"node\"=>\"8.11\",\"java\"=>\"1.8\"}");
    while (matcher.find()) {
      System.out.println(matcher.group("key") + " " + matcher.group("value"));
    }
```
