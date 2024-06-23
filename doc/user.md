# User API Spec

## Register User

Endpoint : POST /api/users

Request Body : 
```json
{
    "username" : "bayufirmansyah",
    "password" : "passwordbayu",
    "name" : "Bayu"
}

```

Response Body (Success) :
```json
{
    "data" : {
        "username" : "bayufirmansyah",
        "name" : "Bayu"
    },
    "status" : 200,
}
```

Response Body (Failed) : 
```json
{
    "error" : "Username has already registered",
    "status" : 400
}
```

## Login User

Endpoint : POST /api/users/login

Request Body : 
```json
{
    "username" : "bayufirmansyah",
    "password" : "passwordbayu",
}
```

Response Body (Success) :
```json
{
    "data" : {
        "username" : "bayufirmansyah",
        "name" : "Bayu",
        "token" : "session_id_generated"
    },
    "status" : 200,
}
```

Response Body (Failed) : 
```json
{
    "error" : "Username or password is wrong",
    "status" : 400
}
```

## Get User

Endpoint : GET /api/users/current

Header
- Authorization : token

Response Body (Success) :
```json
{
    "data" : {
        "id_user" : "1",
        "username" : "bayufirmansyah",
        "name" : "Bayu",
    },
    "status" : 200,
}
```

Response Body (Failed)
```json
{
    "error" : "Unauthorize",
    "status" : 400
}
```

## Update user

Endpoint : PATCH /api/users/current

Header
- Authorization : token

Request Body : 
```json
{
    "password" : "new password", // optional, if want to change password
    "name" : "new name", // optional, if want to change username
}
```

Response Body (Success) :
```json
{
    "data" : {
        "id_user" : "1",
        "username" : "bayufirmansyah",
        "name" : "Bayu",
    },
    "status" : 200,
}
```

Response Body (Failed)
```json
{
    "error" : "Unauthorize",
    "status" : 400
}
```

## Delete User

Endpoint : DELETE /api/users/current

Header
- Authorization : token

Response Body (Success) : 
```json
{
    "data" : "logout success",
    "status" : 200
}
```

Response Body (Failed)
```json
{
    "error" : "Unauthorize",
    "status" : 400
}
```
