---
title: Follow Redirect on Curl
date: 2019-01-24T15:46:53.703Z
tags: ["til"]
---
if we try to `curl gedewahyu.com`, it'll return

```
<html>
<head><title>302 Found</title></head>
<body bgcolor="white">
<center><h1>302 Found</h1></center>
<hr><center>nginx/1.10.3</center>
</body>
</html>
```

that means temporary redirect.

If we want curl to follow redirect, use `-L` flag.

`curl -L gedewahyu.com`
