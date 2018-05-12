# Notes about federation


Federation is great when used right. However if you want to extract some metrics
from another prometheus server, and you rely on Prometheus 2.0 staleness
(metrics go away frequently) you might better use prometheus templates.

This is because federation exposes a prometheus timestamp. Such metrics are not
subject to the new staleness rules in prometheus 2.0.
