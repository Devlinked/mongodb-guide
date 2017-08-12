# Common tasks

## Shutdown a mongod instance safely

### Mongo Shell

```javascript
use admin
db.shutdownServer();
```

### Command line
```bash
mongod --dbpath ~/db/ --shutdown
```

## Import and export data

### Import

```bash
mongoimport --port 12345 --db database --collection mycollection --file filename.json
```

## openssl commands
