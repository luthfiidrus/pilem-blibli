# Admin API

## Theaters

### Get List of Theaters

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

### Get Theater Detail

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

### Create Theater

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
  "image": base64image,
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
    "id": 1456,
    "name": "Pondok Indah Mall 2",
    "abbreviationName": "PIM 2",
    "detailLocation": "Pondok Indah Mall Lantai 2",
    "city": "Jakarta",
    "phones": [
      "021-12345678",
      "021-09876543"
    ],
    "image": base64image,
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

### Edit Theater

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
  "image": base64image,
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
    "theaterId": "1092834", // mandatory field
    "name": "Pondok Indah Mall 2",
    "abbreviationName": "PIM 2",
    "detailLocation": "Pondok Indah Mall Lantai 2",
    "city": "Jakarta",
    "phones": [
      "021-12345678",
      "021-09876543"
    ],
    "image": base64image,
    "priceMondayToThursday": 40000,
    "priceFriday": 45000,
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

### Delete Theater

- Purpose: deleting existing theater object
- Endpoint: `/backend/theater/{theaterId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": true,
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

## Movies

### Get Available Movies

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
        "ageCategory": "SU",
        "potraitImage": base64image,
        "duration": 105 //minutes
      },
      {
        "id": 1358,
        "name": "Frozen 2",
        "ageCategory": "SU",
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

### Create Movie

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
  "ageCategory": "SU",
  "duration": 105 //minutes
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "id": 123,
    "landscapeImage": base64image,
    "potraitImage": base64image,
    "name": "Big Hero 6",
    "ageCategory": "SU",
    "duration": 105 //minutes
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

### Edit Movie

- Purpose: editing existing movie object
- Endpoint: `/backend/movie/{movieId}`
- HTTP Method: `PUT`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "movieId": "1357",
  "landscapeImage": base64image,
  "potraitImage": base64image,
  "name": "Big Hero 6",
  "ageCategory": "SU",
  "duration": 120 //minutes
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "movieId": "1357",
    "landscapeImage": base64image,
    "potraitImage": base64image,
    "name": "Big Hero 6",
    "ageCategory": "SU",
    "duration": 120 //minutes
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

### Delete Movie

- Purpose: deleting existing movie object
- Endpoint: `/backend/movie/{movieId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": true,
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

### Get List of Movies in Specific Theater

- Purpose: getting all movies in specific theater
- Endpoint: `/backend/movie/{theaterId}`
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
        "ageCategory": "SU",
        "potraitImage": base64image,
        "duration": 105 //minutes
      },
      {
        "id": 1358,
        "name": "Frozen 2",
        "ageCategory": "SU",
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

### Add Movie Schedule

- Purpose: Adding movie schedule in a theater
- Endpoint: `/backend/movie/{movieId}/schedule` //TBD
- HTTP Method: `POST`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "theaterId": "1092834",
  "studioId": 1,
  "startTimeAndDate": 1642219448 //EPOCH FORMAT
}
```
- Response Body (Success);
```
{
  "code": 200,
  "data": true,
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

### Get Specific Movie Schedules with Specific Theater

- Purpose: getting specific movie schedules with Specific Theater
- Endpoint: `/backend/movie/{movieId}/schedule`
- HTTP Method: `GET`
- Request Header:
  - Accept: `application/json`
- Request Param:
  - theaterId String
- Response Body (Success):
```
{
  "code": 200,
  "data": [
    {
      "date": 1642220528,
      "studio": [
        {
          "id": 1,
          "time": [
            {
              "text": "13.00",
              "exist": false
            },
            {
              "text": "17.00",
              "exist": true
            }
          ]
        },
        {
          "id": 2,
          "time": [
            {
              "text": "15.00",
              "exist": false
            },
            {
              "text": "20.00",
              "exist": true
            }
          ]
        },
      ]
    },
    {
      "date": 1642220530,
      "studio": [
        {
          "id": 1,
          "time": [
            {
              "text": "07.00",
              "exist": false
            },
            {
              "text": "17.00",
              "exist": true
            }
          ]
        },
        {
          "id": 2,
          "time": [
            {
              "text": "12.00",
              "exist": false
            },
            {
              "text": "18.00",
              "exist": true
            }
          ]
        },
      ]
    }
  ],
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

### Delete Specific Movie in Theater

- Purpose: deleting movie in theater
- Endpoint: `/backend/movie/{movieId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Request Param:
  - theaterId String
- Request Body (Success):
```
{
  "code": 200,
  "data": true,
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

### Create Studio

- Purpose: creating new studio object
- Endpoint: `/backend/studio/create`
- HTTP Method: `POST`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "name": "Studio 1",
  "seatsRow": 9,
  "seatsColumn": 3
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "id": "584cb254-659d-4172-b7af-972390ebd2b6 ",
    "name": "Studio 1",
    "seatsRow": 9,
    "seatsColumn": 3
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

### Delete Studio

- Purpose: deleting existing studio object
- Endpoint: `/backend/studio/{studioId}`
- HTTP Method: `DELETE`
- Request Header:
  - Accept: `application/json`
- Response Body (Success):
```
{
  "code": 200,
  "data": true,
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

### Edit Studio

- Purpose: editing existing studio object
- Endpoint: `/backend/studio/{studioId}`
- HTTP Method: `PUT`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "seatsRow": 3,
  "seatsColumn": 4
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "studioId: 123,
    "seatsRow": 3,
    "seatsColumn": 4
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

### Edit Meals

- Purpose: editing existing meals object
- Endpoint: `/backend/meals/{mealsId}`
- HTTP Method: `PUT`
- Request Header:
  - Accept: `application/json`
  - Content-Type: `application/json`
- Request Body:
```
{
  "stock": 3
}
```
- Response Body (Success):
```
{
  "code": 200,
  "data": {
    "mealsId": 123,
    "stock": 4,
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
