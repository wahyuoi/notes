---
title: 'Postgresql: Run on Docker'
date: 2020-04-06T17:33:59.511Z
tag:
  - til
---
So this midnight I tried to run postgresql 10 on docker. Few notes I get so far:

1. Use official image or build from official [Dockerfile](https://github.com/docker-library/postgres)
2. Provide postgres password using environment variable `POSTGRES_PASSWORD`
3. Never forget to store in persistence volume on host, use `-v /host/path/data:/var/lib/postgresql/data`
4. On default config pg_hba.conf, it will use MD5 auth-method. [(read for more here)](https://www.postgresql.org/docs/10/auth-pg-hba-conf.html)
5. I can't use .pgpass if auth-method is `MD5` or `password`
6. To use .pgpass, I need to change auth-method to `trust`