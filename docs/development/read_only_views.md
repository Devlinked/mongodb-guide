```javascript
db.createView(
     "peopleSectors", 
     "people", 
     [
         { 
            $lookup: {
                from: "companies",
                localField: "company_id",
                foreignField: "_id",
                as: "sector"
            } 
        },
        { $unwind: "$sector" },
        { 
            $project: {
                "_id": 0, 
                "company_id": 1,
                "first_name": 1, 
                "last_name": 1, 
                "job": 1, 
                "sector": "$sector.sector",
                "company": "$sector.name",
            }
        },
        { 
            $project: {
                "company_id": 0,
            }
        }
     ]
)
```

```javascript
db.createView(
     "tweets_sql", 
     "tweets", 
     [
        { 
            $project: {
                "_id": 1, 
                "created_at": 1,
                "id": 1, 
                "source": 1, 
                "text": 1, 
                "user_id": "$user.id",
                "language": "$user.lang",
                "location": "$user.location",
                "name": "$user.name",
                "screen_name": "$user.screen_name"
            }
        }       
     ]
)
```
