---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://excellentbeliever.com'>Documentation Powered by Exbel</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Exbel API! You can use our API to access Excellent Believer API endpoints, which can get information on readings of a user in our database.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct params with each request
curl "http://excellantbeliever.com/api/v1/user/login"
  -F user_details[:email]='teset@test.com'
  -F user_details[:password]='password'
```
> The above command returns JSON structured like this:

```json
{
  auth_token: 'osdjgfousjgoujasog1204u0u32wejf314o0sdij',
  msg: "Successfully authenticated. Welcome Roman!",
  status: 'success'
}
```

### HTTP Request

`POST http://excellantbeliever.com/api/v1/user/login`

### Query Parameters

Parameter | required | Description
--------- | ------- | -----------
user_details[:email] | true | Needed for all types of login(ie, facebook, google, email-password)
user_details[:uid] | false | Should be sent for google & facebook login
user_details[:password] | false | Should be sent for email-password login


ExcellantBeliever uses API keys to allow access to the API. It expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer osdjgfousjgoujasog1204u0u32wejf314o0sdij`

<aside class="notice">
You must replace <code>osdjgfousjgoujasog1204u0u32wejf314o0sdij</code> with your personal API key.
</aside>

# User Registration

> To authorize, use this code:

```shell
# With shell, you can just pass the correct params with each request
curl "http://excellantbeliever.com/api/v1/user/register"
  -F name='teset'
  -F email='teset@test.com'
  -F password='password'
```
> The above command returns JSON structured like this:

```json
{
  msg: 'Welcome! You have signed up successfully. Please confirm your registration by the confirmation link you have received via email.'
  status: 'success'
}
```

### HTTP Request

`POST http://excellantbeliever.com/api/v1/user/register`

### Query Parameters

Parameter | required | Description
--------- | ------- | -----------
email | true | should be a valid email id
name | true | can alpha numeric
password | true | Should be 6 chars min


This creates a user in excellant believer app. But the user has to be confirmed. 

# Readings

## Get All readings for the user

```shell
# With shell, you can just pass the correct header with each request
curl "http://excellantbeliever.com/api/v1/readings"
  -H "Authorization: Bearer osdjgfousjgoujasog1204u0u32wejf314o0sdij"
```
> The above command returns JSON structured like this:

```json
{"readings"=>
  {"Jude"=>
    {"readings"=>
      [{"id"=>98,
        "chapter_id"=>5877,
        "user_id"=>8,
        "created_at"=>"2017-05-24T10:47:41.501Z",
        "updated_at"=>"2017-05-24T10:47:41.501Z",
        "date_read"=>"2017-05-24"}],
     "book_id"=>52,
     "completed"=>20.0,
     "last_read"=>"2017-05-24T10:47:41.501Z"},
   "Genesis"=>
    {"readings"=>
      [{"id"=>99,
        "chapter_id"=>4015,
        "user_id"=>8,
        "created_at"=>"2017-05-24T10:48:51.829Z",
        "updated_at"=>"2017-05-24T10:48:51.829Z",
        "date_read"=>"2017-05-24"},
       {"id"=>50,
        "chapter_id"=>3971,
        "user_id"=>8,
        "created_at"=>"2017-05-22T12:58:29.180Z",
        "updated_at"=>"2017-05-22T12:58:29.180Z",
        "date_read"=>"2017-05-22"}],
     "book_id"=>1,
     "completed"=>34.17,
     "last_read"=>"2017-05-30T10:46:52.759Z"},
   "Exodus"=>
    {"readings"=>
      [{"id"=>106,
        "chapter_id"=>4089,
        "user_id"=>8,
        "created_at"=>"2017-05-24T11:21:54.327Z",
        "updated_at"=>"2017-05-24T11:21:54.327Z",
        "date_read"=>"2017-05-24"},
       {"id"=>107,
        "chapter_id"=>4090,
        "user_id"=>8,
        "created_at"=>"2017-05-24T11:22:02.956Z",
        "updated_at"=>"2017-05-24T11:22:02.956Z",
        "date_read"=>"2017-05-24"},
       {"id"=>108,
        "chapter_id"=>4092,
        "user_id"=>8,
        "created_at"=>"2017-05-24T11:32:01.135Z",
        "updated_at"=>"2017-05-24T11:32:01.135Z",
        "date_read"=>"2017-05-24"}],
     "book_id"=>2,
     "completed"=>28.11,
     "last_read"=>"2017-05-30T10:47:07.971Z"},
   "Esther"=>
    {"readings"=>
      [{"id"=>76,
        "chapter_id"=>4536,
        "user_id"=>8,
        "created_at"=>"2017-05-23T13:22:22.105Z",
        "updated_at"=>"2017-05-23T13:22:22.105Z",
        "date_read"=>"2017-05-23"}],
     "book_id"=>14,
     "completed"=>50.0,
     "last_read"=>"2017-05-23T13:22:22.105Z"},
   "Ruth"=>
    {"readings"=>
      [{"id"=>96,
        "chapter_id"=>4444,
        "user_id"=>8,
        "created_at"=>"2017-05-24T10:38:49.976Z",
        "updated_at"=>"2017-05-24T10:38:49.976Z",
        "date_read"=>"2017-05-24"}],
     "book_id"=>8,
     "completed"=>12.5,
     "last_read"=>"2017-05-24T10:38:49.976Z"},
   "Leviticus"=>
    {"readings"=>
      [{"id"=>158,
        "chapter_id"=>4274,
        "user_id"=>8,
        "created_at"=>"2017-05-24T16:26:41.104Z",
        "updated_at"=>"2017-05-24T16:26:41.104Z",
        "date_read"=>"2017-05-24"},
       {"id"=>159,
        "chapter_id"=>4275,
        "user_id"=>8,
        "created_at"=>"2017-05-24T16:27:23.022Z",
        "updated_at"=>"2017-05-24T16:27:23.022Z",
        "date_read"=>"2017-05-24"},
       {"id"=>160,
        "chapter_id"=>4276,
        "user_id"=>8,
        "created_at"=>"2017-05-24T16:27:26.878Z",
        "updated_at"=>"2017-05-24T16:27:26.878Z",
        "date_read"=>"2017-05-24"}],
     "book_id"=>3,
     "completed"=>39.06,
     "last_read"=>"2017-05-24T16:45:28.288Z"
    }
  }
}
```

This endpoint retrieves all readings of the user.

### HTTP Request

`GET http://excellantbeliever.com/api/v1/readings`


<aside class="success">
Remember — you must send auth_token in the header for this request
</aside>

## Get all readings from a Specific Book

```shell
curl "http://excellantbeliever.com/api/v1/readings/1"
  -H "Authorization: Bearer meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
"read_chapters"=>[
    {"id"=>4088,
    "name"=>"Exodus",
    "book_id"=>2,
    "chapter"=>2,
    "chapter_index"=>2002,
    "created_at"=>"2017-05-02T07:08:37.639Z",
    "updated_at"=>"2017-05-02T07:08:37.642Z"},
    {"id"=>4089,
    "name"=>"Exodus",
    "book_id"=>2,
    "chapter"=>3,
    "chapter_index"=>2003,
    "created_at"=>"2017-05-02T07:08:37.639Z",
    "updated_at"=>"2017-05-02T07:08:37.642Z"},
    {"id"=>4090,
    "name"=>"Exodus",
    "book_id"=>2,
    "chapter"=>4,
    "chapter_index"=>2004,
    "created_at"=>"2017-05-02T07:08:37.639Z",
    "updated_at"=>"2017-05-02T07:08:37.642Z"},
    {"id"=>4091,
    "name"=>"Exodus",
    "book_id"=>2,
    "chapter"=>5,
    "chapter_index"=>2005,
    "created_at"=>"2017-05-02T07:08:37.639Z",
    "updated_at"=>"2017-05-02T07:08:37.642Z"},
    {"id"=>4092,
    "name"=>"Exodus",
    "book_id"=>2,
    "chapter"=>6,
    "chapter_index"=>2006,
    "created_at"=>"2017-05-02T07:08:37.639Z",
    "updated_at"=>"2017-05-02T07:08:37.642Z"}
  ]
}

```

This endpoint retrieves all readings for the current user in specified book.

### HTTP Request

`POST http://excellantbeliever.com/api/v1/readings`

## Create a reading for the user

```shell
curl "http://excellantbeliever.com/api/v1/readings"
  -H "Authorization: Bearer meowmeowmeow"
  -F book_id=23
  -F chapter=5
```

> The above command returns JSON structured like this:

```json
{"reading"=>
  {"id"=>241,
   "user_id"=>8,
   "chapter_id"=>4087,
   "created_at"=>"2017-05-31T13:30:08.087Z",
   "updated_at"=>"2017-05-31T13:30:08.087Z",
   "date_read"=>"2017-05-31"}
}

```
### Query Parameters

Parameter | required | Description
--------- | ------- | -----------
book_id | true | must be numeric
chapter | true | must be numeric

This endpoint creates a reading for the user in given book and chapter.

### HTTP Request

`POST http://excellantbeliever.com/api/v1/readings`

## Destroy a reading for the user

```shell
curl "http://excellantbeliever.com/api/v1/readings/destroy"
  -H "Authorization: Bearer meowmeowmeow"
  -F book_id=23
  -F chapter=5
```

> The above command returns a http status 204.

### Query Parameters

Parameter | required | Description
--------- | ------- | -----------
book_id | true | must be numeric
chapter | true | must be numeric

This endpoint destroy the reading for the user in given book and chapter.

### HTTP Request

`POST http://excellantbeliever.com/api/v1/readings/destroy`

## Retrive reading statistics of the user

```shell
curl "http://excellantbeliever.com/api/v1/readings/my_stats"
  -H "Authorization: Bearer meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{"stats"=>{
  "total_reading"=>73,
  "total_remaining"=>1910,
  "complete_percent"=>3.7,
  "remaining_percent"=>96.3,
  "days_to_complete"=>"about 2 years"
  }
}

```

This endpoint destroy the reading for the user in given book and chapter.

### HTTP Request

`GET http://excellantbeliever.com/api/v1/readings/my_stats