---
title: 'Docker: Difference ADD and COPY'
date: 2020-04-05T17:15:01.043Z
tag:
  - til
---
When creating docker image, sometimes we need to copy few files. We can use ADD or COPY command to copy files from our machine to docker image. Both have similar purpose, with different implementation

#### ADD: ([docs](https://docs.docker.com/engine/reference/builder/#add))

* Allow <src> to be a URL
* If <src> is a local tar archive in a recognized compression format (identity, gzip, bzip2 or xz) then it is unpacked as a directory. Resources from remote URLs are not decompressed. When a directory is copied or unpacked, it has the same behavior as tar -x

#### COPY: ([docs](https://docs.docker.com/engine/reference/builder/#copy))

* COPY is more transparent and only supports the basic copying of local files into the container
* If you have multiple Dockerfile steps that use different files from your context, COPY them individually, rather than all at once. This ensures that each step’s build cache is only invalidated (forcing the step to be re-run) if the specifically required files change.\
  Example\
  \
  `COPY requirements.txt /tmp/ `\
  `RUN pip install --requirement /tmp/requirements.txt`\
  `COPY . /tmp/`

This comparison already covered on [Docker's Best Practice](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#add-or-copy)