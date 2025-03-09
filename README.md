# tinyapi: one api one line

```
TINYAPI
TYPE User id uuid name string email string
GET /users -> 200 User[]
GET /users/:id -> 200 User 404 {error string}
POST /users BODY {name string email string} -> 201 User
PUT /users/:id BODY {name? email?} -> 200 User
DELETE /users/:id -> 204

RESOURCE users User {name string email string} # above is equivalent
RESOURCE comments ONLY index,create # only specific operations

AUTH jwt bearer # auth when needed
GET /admin/stats -> 200 {count int} AUTH jwt

GROUP Admin
  GET /admin/stats -> 200 {count int} AUTH jwt
  POST /admin/reset -> 204 AUTH jwt
ENDGROUP
```
