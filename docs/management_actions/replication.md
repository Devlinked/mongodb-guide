# Replication

A replica set consists in several instances of `mongod` running at different servers. Its purpose is to save a copy the database at each server (redundancy of data).

It is formed by a Primary server, a number of secondary servers and optionally, a number of arbiters. The primary is normally the one that receives the commands from Mongo drivers.
 
## Common configurations
 
It is recommended to have a odd number of replica set members.

### 3 members in the replica set

This is the most common configuration

### 2 members in the replica set and an arbiter

### 5 members in the replica set

## Create a replica set

```bash
mongod --replSet myReplSet --dbpath ~/db/r1 --logpath ~/db/r1/mongodb.log --port 30000 --fork
```

## Add a member to a running replica set

## Reconfig

## Arbiters
