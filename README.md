# Logging-Stack

## tl;dr
These are kubernetes descriptors for elasticsearch with kibana. Log Aggregation works via fluentd (done) or logstash (wip). Apply for kubernetes via kustomize, either the standalone binary or with kubectl in version 1.14+.

## Applying
Look in overlays for your flavor. If you have an existing cluster, or do not have all the rights to it (which usually means your admins provided you with a namespace), then use the "without namespace" options. It might also be a good idea to have your admin apply fluentd - which means you only need ek-without-namespace yourself.
