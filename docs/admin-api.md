Admin API
=========

Get List of Theaters
-------------
- Purpose: getting all existing theaters
- Endpoint: `/backend/theater/list/{location}`
- HTTP Method: `GET`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "theaters" : [
      {
        "id": "123456",
        "name": "Pondok Indah Mall 1",
        "url": "https://pilem.com/backend/theater/detail/123456"
      },
      {
        "id": "123457",
        "name": "Pondok Indah Mall 2",
        "url": "https://pilem.com/backend/theater/detail/123457"
      }
    ]
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Get Theater Detail
------------------

- Purpose: getting an existing theater object
- Endpoint: `/backend/theater/{theaterId}`
- HTTP Method: `GET`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "id": 123457,
    "name": "Pondok Indah Mall 2",
    "abbreviationName": "PIM 2",
    "detailLocation": "Pondok Indah Mall Lantai 2",
    "city": "Jakarta",
    "phones": [
      "021-12345678",
      "021-09876543"
    ],
    "priceMondayToThursday": 35000,
    "priceFriday": 40000,
    "priceSaturdayToSunday": 50000
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Create Theater
--------------

- Purpose: creating new theater object
- Endpoint: `/backend/theater/create`
- HTTP Method: `POST`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "name": "Pondok Indah Mall 2",
  "abbreviationName": "PIM 2",
  "detailLocation": "Pondok Indah Mall Lantai 2",
  "city": "Jakarta",
  "phones": [
    "021-12345678",
    "021-09876543"
  ],
  "priceMondayToThursday": 35000,
  "priceFriday": 40000,
  "priceSaturdayToSunday": 50000
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    // **TBD**
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Edit Theater
------------

- Purpose: editing existing theater object
- Endpoint: `/backend/theater/{theaterId}`
- HTTP Method: `PUT`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "theaterId": "1092834", // mandatory field
  "name": "Pondok Indah Mall 2",
  "abbreviationName": "PIM 2",
  "detailLocation": "Pondok Indah Mall Lantai 2",
  "city": "Jakarta",
  "phones": [
    "021-12345678",
    "021-09876543"
  ],
  "priceMondayToThursday": 40000,
  "priceFriday": 45000,
  "priceSaturdayToSunday": 50000
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    // **TBD**
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Delete Theater
------------

- Purpose: deleting existing theater object
- Endpoint: `/backend/theater/{theaterId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    // **TBD**
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Get Available Movies
------------------

- Purpose: getting all available movies
- Endpoint: `/backend/movie/available-list`
- HTTP Method: `GET`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "movies": [
      {
        "id": 1357,
        "name": "Big Hero 6",
        "ageCategory": {
          "id": "SU",
          "name": "Semua Umur"
        },
        "potraitImage": base64image,
        "duration": 105 //minutes
      },
      {
        "id": 1358,
        "name": "Frozen 2",
        "ageCategory": {
          "id": "SU",
          "name": "Semua Umur"
        },
        "potraitImage": base64image,
        "duration": 110 //minutes
      }
    ]
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```

Create Movie
------------

- Purpose: creating new movie object
- Endpoint: `/backend/movie/create`
- HTTP Method: `GET`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "landscapeImage": base64image,
  "potraitImage": base64image,
  "name": "Big Hero 6",
  "ageCategory": {
    "id": "SU",
    "name": "Semua Umur"
  },
  "duration": 105 //minutes
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    // **TBD**
  },
  "status": "OK"
}
```
- Response Body (Fail):
```
{
  "code": 403,
  "status": "FORBIDDEN"
}
```
```
{
  "code": 500,
  "status": "INTERNAL_SERVER_ERROR"
}
```
