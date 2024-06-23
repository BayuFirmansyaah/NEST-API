# Contact API Spec

## Create Contact

Endpoint : POST /api/contacts

Headers : 
- Authorization : token

Request Body :
```json
{
    "first_name" : "Bayu",
    "last_name" : "Firmansyah",
    "email" : "bayu@mail.com",
    "phone" : "+62xxxxxxxxx",
}
```

Response Body (Success) : 
```json
{
    "data" : {
        "id" : 1,
        "first_name" : "Bayu",
        "last_name" : "Firmansyah",
        "email" : "bayu@mail.com",
        "phone" : "+62xxxxxxxxx",
    },
    "status" : 200
}
```

Response Body (Failed) : 
```json
{
    "error" : "Can't create contact",
    "status" : 400
}
```

## Get All Contacts

Endpoint : GET /api/contacts

Headers :
- Authorization : token

Response Body (Success) : 
```json
{
    "data" : [
        {
            "id" : 1,
            "first_name" : "Bayu",
            "last_name" : "Firmansyah",
            "email" : "bayu1@mail.com",
            "phone" : "+62xxxxxxxxx",
        },
        {
            "id" : 2,
            "first_name" : "Bayu",
            "last_name" : "Firmansyah",
            "email" : "bayu2@mail.com",
            "phone" : "+62xxxxxxxxx",
        }
    ],
    "status" : 200
}

Response Body (Failed) : 
```json
{
    "error" : "Can't get contacts",
    "status" : 400
}
```

## Get Contact

Endpoint : GET /api/contacts/:contactId

Headers :
- Authorization : token

Response Body (Success) : 
```json
{
    "data" : {
        "id" : 1,
        "first_name" : "Bayu",
        "last_name" : "Firmansyah",
        "email" : "bayu@mail.com",
        "phone" : "+62xxxxxxxxx",
    },
    "status" : 200
}


Response Body (Failed) : 
```json
{
    "error" : "Contact not found",
    "status" : 400
}
```

## Update Contact

Endpoint : PATCH /api/contacts/:contactId

Headers :
- Authorization : token

Request Body : 
```json
{
    "first_name" : "Bayu",
    "last_name" : "Firmansyah",
    "email" : "newEmail@gmail.com",
    "phone" : "+62xxxxxxxxx",
}

Response Body (Success) : 
```json
{
    "data" : {
        "id" : 1,
        "first_name" : "Bayu",
        "last_name" : "Firmansyah",
        "email" : "newMail@gmail.com",
        "phone" : "+62xxxxxxxxx",
    },
    "status" : 200
}

Response Body (Failed) : 
```json
{
    "error" : "Can't update contact",
    "status" : 400
}
```

## Remove Contact

Endpoint : DELETE /api/contacts/:contactId

Headers :
- Authorization : token

Response Body (Success) : 
```json
{
    "data" : "Contact removed",
    "status" : 200
}

Response Body (Failed) : 
```json
{
    "error" : "Can't remove contact",
    "status" : 400
}
```

## Search Contact

Endpoint : GET /api/contacts/search

Headers :
- Authorization : token

Query Params :
- q : search query

Response Body (Success) : 
```json
{
    "data" : [
        {
            "id" : 1,
            "first_name" : "Bayu",
            "last_name" : "Firmansyah",
            "email" : "bayu@mail.com",
            "phone" : "+62xxxxxxxxx",
        },
        {
            "id" : 2,
            "first_name" : "Bayu",
            "last_name" : "Firmansyah",
            "email" : "bayu2@mail.com",
            "phone" : "+62xxxxxxxxx",
        }
    ],
    "status" : 200
}

Response Body (Failed) : 
```json
{
    "error" : "Can't search contact",
    "status" : 400
}
```
