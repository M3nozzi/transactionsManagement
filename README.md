# Transaction Management Application

That's a transaction management application with the purpose of putting into practice the technologies studied for the construction of the application backend.

## Technologies:

- Typescript

- Node.js 

- Docker

- PostgreSQL

- TypeORM

- Multer (to upload files)



<img src="https://res.cloudinary.com/menozzi/image/upload/v1604075360/project2/transactionManagement_wkum9u.png" width="600">


- Insomnia (to test the built API)


Create a transaction with method POST to http://localhost:3333/transactions:

```
{
	"title": "Salary",
	"value": 8000,
	"type": "income",
	"category": "work"
}
```

That's a success return:
```
{
  "title": "Salary",
  "type": "income",
  "value": 8000,
  "category_id": "417acd6e-d5c6-47eb-9e58-11dcd13dbd84",
  "category": {
    "id": "417acd6e-d5c6-47eb-9e58-11dcd13dbd84",
    "title": "work",
    "created_at": "2020-09-30T22:20:11.462Z",
    "updated_at": "2020-09-30T22:20:11.462Z"
  },
  "id": "c4894abd-4b04-4670-9b0e-0060f0ac4f98",
  "created_at": "2020-09-30T22:20:11.479Z",
  "updated_at": "2020-09-30T22:20:11.479Z"
}
```

List the transactions with method GET to http://localhost:3333/transactions, and get the balance, income and outcome
```
{
  "transactions": [
    {
      "id": "7559f85f-dd50-41af-8312-a7366dc92a46",
      "title": "Salary",
      "type": "income",
      "value": "9000.00",
      "category_id": "417acd6e-d5c6-47eb-9e58-11dcd13dbd84",
      "created_at": "2020-10-01T05:54:01.560Z",
      "updated_at": "2020-10-01T05:54:01.560Z"
    },
    {
      "id": "5a2d177a-a476-4552-9d04-a362175345d8",
      "title": "Website Hosting",
      "type": "outcome",
      "value": "50.00",
      "category_id": "dc92139e-5039-4ad7-930e-4f3fefa71281",
      "created_at": "2020-10-01T05:54:01.560Z",
      "updated_at": "2020-10-01T05:54:01.560Z"
    },
    {
      "id": "f725a777-4d37-4163-8bd7-d3ebebe0d486",
      "title": "Tickets",
      "type": "outcome",
      "value": "550.00",
      "category_id": "66cd851d-66c0-4dec-bc46-64af5984e9e1",
      "created_at": "2020-10-01T05:54:01.560Z",
      "updated_at": "2020-10-01T05:54:01.560Z"
    }
  ],
  "balance": {
    "income": 9000,
    "outcome": 600,
    "total": 8400
  }
}
```
Delete a transaction with the method DELETE to http://localhost:3333/transactions/:id
```
http://localhost:3333/transactions/c4894abd-4b04-4670-9b0e-0060f0ac4f98
```

Import file .csv  with method POST to http://localhost:3333/transactions/import
```
[
  {
    "title": "Salary",
    "type": "income",
    "value": "9000",
    "category_id": "417acd6e-d5c6-47eb-9e58-11dcd13dbd84",
    "category": {
      "id": "417acd6e-d5c6-47eb-9e58-11dcd13dbd84",
      "title": "work",
      "created_at": "2020-09-30T22:20:11.462Z",
      "updated_at": "2020-09-30T22:20:11.462Z"
    },
    "id": "c32eda69-fc21-463b-95f4-48e5a45c2336",
    "created_at": "2020-10-01T05:55:32.106Z",
    "updated_at": "2020-10-01T05:55:32.106Z"
  },
  {
    "title": "Website Hosting",
    "type": "outcome",
    "value": "50",
    "category_id": "dc92139e-5039-4ad7-930e-4f3fefa71281",
    "category": {
      "id": "dc92139e-5039-4ad7-930e-4f3fefa71281",
      "title": "Website",
      "created_at": "2020-10-01T05:42:01.309Z",
      "updated_at": "2020-10-01T05:42:01.309Z"
    },
    "id": "4fcc415e-00b5-4c3a-8d75-297482165c44",
    "created_at": "2020-10-01T05:55:32.106Z",
    "updated_at": "2020-10-01T05:55:32.106Z"
  },
  {
    "title": "Tickets",
    "type": "outcome",
    "value": "550",
    "category_id": "66cd851d-66c0-4dec-bc46-64af5984e9e1",
    "category": {
      "id": "66cd851d-66c0-4dec-bc46-64af5984e9e1",
      "title": "Travel",
      "created_at": "2020-10-01T05:54:01.545Z",
      "updated_at": "2020-10-01T05:54:01.545Z"
    },
    "id": "4e238c2e-9731-4bf0-96f3-1dccf63e4fd8",
    "created_at": "2020-10-01T05:55:32.106Z",
    "updated_at": "2020-10-01T05:55:32.106Z"
  }
]
```
## Author

Developed by [**Fabio Menozzi**](https://www.linkedin.com/in/menozzi-fabio/)
