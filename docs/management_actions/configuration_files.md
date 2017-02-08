# Configuration files

Configuration files are very useful when your `mongod` or `mongos` call it's very long and has a lot of parameters. It will prevent you to make mistakes and typos, and you will able to reuse common parameters on your instances. Very necessary when you are dealing with a encrypted replica set.

### Use a configuration File

To run a mongo instance using a config file, add the following parameter:

```bash
mongod --config /home/tony/mongod.yml

mongos --config /home/tony/mongos.yml
```
Or:

```bash
mongod -f /home/tony/mongod.yml

mongos -f /home/tony/mongos.yml
```


### File format

MongoDB configuration files are written in [YAML](http://www.yaml.org/). 

!!! note
    YAML doesn't support tab indentation, so use spaces instead.
    
Here's a example file with a common instance of a mongod with replication, x509 authentication and encryption enabled:
 
```yaml
storage:
    dbPath: "/home/tony/awesomeReplSet/r0"
systemLog:
   destination: file
   path: "/home/tony/awesomeReplSet/r0/mongo.log"
net:
   port: 27111
   ssl:
       mode: requireSSL
       PEMKeyFile: "/home/tony/awesomeReplSet/member0.pem"
       CAFile: "/home/tony/awesomeReplSet/ca.pem"
replication:
    replSetName: awesomeReplSet
security:
   authorization: enabled
   clusterAuthMode: x509
   enableEncryption: true
   encryptionKeyFile: "/home/tony/awesomeReplSet/mongodb-keyfile"
processManagement:
   fork: true
```
!!! tip
    You can combine a config file and parameters passed by the command line to have maximum flexibility.

    
See a complete list of MongoDB configuration files [here](https://docs.mongodb.com/manual/reference/configuration-options/#core-options).