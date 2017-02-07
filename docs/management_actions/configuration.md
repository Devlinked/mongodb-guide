# Configuration

## Shutdown a mongod instance

### Mongo Shell

``` javascript
use admin
db.shutdownServer();
```

### Command line
``` bash
mongod --shutdown
```

## Using configuration files