# Roles

## Common built in roles

## Create users with a role

```javascript
db.createUser({
    user: 'userAdmin', 
    pwd: 'badges', 
    roles: [
        { role: 'userAdminAnyDatabase', db: 'admin' }
    ]
})

db.createUser({
    user: 'dbAdmin', 
    pwd: 'collections', 
    roles: [
        { role: 'dbAdminAnyDatabase', db: 'admin' }
    ]
})

db.createUser({
    user: 'sysAdmin', 
    pwd: 'cables', 
    roles: [
        { role: 'clusterManager', db: 'admin' }
    ]
})

db.createUser({
    user: 'dataLoader', 
    pwd: 'dumpin', 
    roles: [
        { role: 'readWriteAnyDatabase', db: 'admin' }
    ]
})
```

## Custom roles

```javascript
db.createRole({
    role: 'HRDEPARTMENT', 
    privileges: [
        {
            resource: {
                db: 'HR', 
                collection: ''
            }, 
            actions: [
                "find", 
                "dropUser"
            ]
        },
        {
            resource: {
                db: 'HR', 
                collection: 'employees'
            }, 
            actions: ["insert"]
        }
    ], 
    roles: []
})
```
