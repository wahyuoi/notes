---
title: 'Java: Recursive Type Declaration'
date: 2020-03-11T15:36:53.619Z
tag:
  - til
---
Just playing around jackson library, and found interesting interface, VisibilityChecker.

This class use recursive type declaration, to support builder/fluent pattern.

Here the snippet:

```java
package com.fasterxml.jackson.databind.introspect;

**
 * Interface for object used for determine which property elements
 * (methods, fields, constructors) can be auto-detected, with respect
 * to their visibility modifiers.
 *<p>
 * Note on type declaration: funky recursive type is necessary to
 * support builder/fluent pattern.
 */
public interface VisibilityChecker<T extends VisibilityChecker<T>>
{
  ...
}
```

By using this interface, we can create 2 types of class

1. Class that implement VisibilityChecker with it's class as type.

```java
public class Leaf implements VisibilityChecker<Leaf> 
{
  ...
}
```

2. Class that implement VisibilityChecker with other class as type, the other class should implement VisibilityChecker with it's class as type

```java
public class Node implements VisibilityChecker<Leaf> 
{
  ...
}
```

But, we can't create class that implement VisibilityChecker with other class as type, the other class that implement VisibilityCheker with another class as type.

```java
// this one not working
public class Root implements VisibilityChecker<Node>
{
  ...
}
```