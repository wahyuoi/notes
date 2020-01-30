---
title: Free Up Postgresql Storage
date: 2020-01-30T15:30:40.957Z
tag:
  - story
---
When your storage is nearly full, you have 2 options to free it up:
1. Scale up --> burning some money
2. Delete data --> lost your records!

I've been using both options, and both have drawbacks.

Lets talk about option 2: **Delete data**

Deleting a lot of records **won't** increase your free storage immediately. 
Deleted records will become dead tuples. 

Use `VACUUM` to reclaims storage occupied by dead tuples. using `VERBOSE ANALYZE` option gives better understanding about dead records.

Don't forget to `REINDEX` all of your affected index.

More info about [VACUUM](https://www.postgresql.org/docs/9.5/sql-vacuum.html) and [REINDEX](https://www.postgresql.org/docs/9.5/sql-reindex.html)

