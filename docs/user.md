#User API Spec

##Register User API

Endpoint : POST /api/users
  
Request Body : 

```json 
{
    "username" : "hakim001"
    "password" : "Hakim123"
    "name" : "database 001"
}
```

Respond Body Succes :

```json 
{
    "data" : {},
        "username" : "hakim001"
        "name" : "database 001"
}
```


Response Body Error :

```json
{
  "errors" :  "Username already registered"  
}
```

##Login User API

Endpoint : POST /api/users/login

Request Body :

```json
{
    "username" : "hakim001"
    "password" : "Hakim123" 
}
```

Response Body Success : 

```json
{
     "data" : {
        "token" : "unique-token"
     }  
}
```

Response Body Error :

```json
{
    "errors" : "Username or password wrong"
}
```

##Update User API

Endpoint : PATCH /api/users/current

Headers :
- Authorization : token

Request Body : 

```json
{
    "name" : "database 001 pusat", //optional
    "password" : "hakim123" //optional
}
```

Response Body Success : 

```json
{
    "data" : {
        "username" : "hakim001"
        "name" : "database 001 pusat"
    } 
}
```

Response Body Error : 

```json
{
    "errors" : "Name length max 100"
}
```

#Get User API

Endpoint : GET /api/users/current

Headers :
- Authorization : token

Response Body Success:

```json
{
    "data" : {
        "username" : "hakim001"
        "name" : "database 001"
    }
}
```

Response Body Error :

```json
{
    "errors" : "Unauthorized"
}
```

#Logout User API

Endopoint : DELETE /api/users/logout

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : "OK"
}
```

Response Body Error : 

```json
{
    "errors" : "Unauthorized"
}
```