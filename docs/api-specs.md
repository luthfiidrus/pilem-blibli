Admin API
=========

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
- Endpoint: `/backend/theater/update`
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
    // TBD
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
- Endpoint: `/backend/theater/delete/{theaterId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    // TBD
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
