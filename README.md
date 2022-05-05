Balena mdns resolver
====================

To use locally:
```
docker-compose build
docker run -it --rm --net host balena-mdns_resolve:latest $LOCALNAME.local
```

To use on a Balena fleet set the following environment variable:

**LOCALNAME**: Local mdns name to resolve.
