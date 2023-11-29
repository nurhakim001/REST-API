#contact API Spec

##Create Contact API

Endpoint : POST /api/contacts

Headers : 
- Authorization : token

Request Body :

```json
{
    "firstName" : "Abdul",
    "lastName" : "Hakim",
    "email" : "mnur.abdhakim@gmail.com",
    "phone" : "+6287708302720",
}
```

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "firstName" : "Abdul",
        "lastName" : "Hakim",
        "email" : "mnur.abdhakim@gmail.com",
        "phone" : "+6287708302720",
    }
}
```

Response Body Error :

```json
{
   "errors" : "Email is not valid format" 
}
```

##Update Contact API

Endpoint : PUT /api/contacts/:id

Headers : 
- Authorization : token

Request Body :

```json
{
    "firstName" : "Abdul",
    "lastName" : "Hakim",
    "email" : "mnur.abdhakim@gmail.com",
    "phone" : "+6287708302720",
}
```

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "firstName" : "Abdul",
        "lastName" : "Hakim",
        "email" : "mnur.abdhakim@gmail.com",
        "phone" : "+6287708302720",
    }
}
```

Response Body Error :

```json
{
    "errors" : "Email is not valid format"
}
```

##Get Contact API

Endpoint : GET /api/contacts

Headers : 
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "firstName" : "Abdul",
        "lastName" : "Hakim",
        "email" : "mnur.abdhakim@gmail.com",
        "phone" : "+6287708302720",
    }
}
```

Response Body Error :
```json
{
    "errors" : "Contact is not found"
}
```

##Search Contact API 

Endpoint : GET /api/contacts

Headers : 
- Authorization : token
  
Query params :
- name : Search by firstName or lastName, using like, optional
- email : Search by email using like, optional
- phone : Search by phone using like, optional
- page : number of page, default 1
- size : size per page, default 10

Response Body Success :

```json
{
    "data" : [
        {
            "id" : 1,
            "firstName" : "Abdul",
            "lastName" : "Hakim",
            "email" : "mnur.abdhakim@gmail.com",
            "phone" : "+6287708302720",
        },
        {
            "id" : 2,
            "firstName" : "Abdul",
            "lastName" : "Hakim",
            "email" : "mnur.abdhakim@gmail.com",
            "phone" : "+6287708302720",
        },
    ],
    "paging" : {
        "page" : 1,
        "total_page" : 3,
        "total_item" : 30
    }
}
```

Response Body Error :

##Remove Contact API

Endpoint : DELETE /api/contacts/:id

Headers : 
- Authorization : token

Response Body Success :

```json
{
    "data" : "ok"
}
```

Response Body Error :

```json
{
    "errors" : "Contact is not found"
}
```