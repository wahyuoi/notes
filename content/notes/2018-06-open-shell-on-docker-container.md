---
title: Open Shell on Docker Container
date: 2018-06-14T11:11:11.111Z
tags: ["til"]
---

Open Shell on Running Container
---

use `docker ps` to show container's name. To open new terminal with new instance of container's shell, just need to run:

```
docker exec -i -t CONTAINER_NAME /bin/bash

```
