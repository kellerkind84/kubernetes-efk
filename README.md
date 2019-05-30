# Logging-Stack

## tl;dr
These are kubernetes descriptors for elasticsearch with kibana. Log Aggregation works via fluentd (done) or logstash (wip). Apply for kubernetes via kustomize, either the standalone binary or with kubectl in version 1.14+.

## Applying
Look in overlays for your flavor. If you have an existing cluster, or do not have all the rights to it (which usually means your admins provided you with a namespace), then use the "without namespace" options. It might also be a good idea to have your admin apply fluentd - which means you only need ek versions.

## Curator

It is also important to note that there is a curator pod deployed with every version of elasticsearch. This is so that old indices might be deleted after a certain amount of days. The actual amount of days may be changed by changing the INDEX_DELETION_AGE_IN_DAYS environment variable. For testing purposes the number is set to 1, but you will want to set that more to 30 in production.
