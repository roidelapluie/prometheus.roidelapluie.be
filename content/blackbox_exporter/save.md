---
title: "Save blackbox_exporter results"
date: 2018-05-17T11:33:59+02:00
---

Here is a one liner you can put in a cron tab to save blackbox_exporter results.

```
/usr/bin/wget -q --directory /var/log/blackbox_exporter -e robots=off  -r  -A 'logs*' http://127.0.0.1:9115/index.html
```

Here is a one liner you can put in a cron tab to delete blackbox_exporter results older than 32 days.

```
/usr/bin/find /var/log/blackbox_exporter -type f -ctime +32 -delete
```

