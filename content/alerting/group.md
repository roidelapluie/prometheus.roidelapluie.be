---
title: "Alertmanager Group_By"
date: 2018-05-12T10:31:26+02:00
---

Something that did byte me:

If you say in the alertmanager `group_by: []`, then all the alerts will always be
grouped together, in a single group.

I was expecting not to group them but that turns out to be not possible.
