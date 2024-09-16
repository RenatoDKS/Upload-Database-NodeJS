# Go Finances API

**Go Finances API** is a project developed during the **GoStack Bootcamp** by Rocketseat. This challenge focuses on building a financial management API using Node.js, Express, TypeORM, and PostgreSQL. The API allows users to manage their financial transactions by creating income and outcome entries and importing bulk transactions from CSV files.

## Features

- **Create transactions**: Add income and outcome financial transactions.
- **View balance**: Display the current balance, which is calculated by summing the income and subtracting the outcome transactions.
- **Import transactions via CSV**: Upload a CSV file containing multiple transactions to be processed.

## Endpoints

### 1. Create Transaction
- **POST** `/transactions`
- Payload:
  ```json
  {
    "title": "Transaction title",
    "value": 1000,
    "type": "income" | "outcome",
    "category": "Category name"
  }
  ```

### 2. List Transactions and Balance
- **GET** `/transactions`
- Response:
  ```json
  {
    "transactions": [
      {
        "id": "uuid",
        "title": "Transaction title",
        "value": 1000,
        "type": "income",
        "category": {
          "id": "uuid",
          "title": "Category name"
        }
      }
    ],
    "balance": {
      "income": 1000,
      "outcome": 500,
      "total": 500
    }
  }
  ```

### 3. Delete Transaction
- **DELETE** `/transactions/:id`
- Removes a transaction by its ID.

### 4. Import CSV
- **POST** `/transactions/import`
- Allows uploading a CSV file containing transaction data for batch import.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/renatosilveira99/go-finances-api.git
   ```

2. Navigate to the project directory and install dependencies:
   ```bash
   cd go-finances-api
   yarn
   ```

3. Set up a PostgreSQL database and configure the `.env` file with your database credentials.

4. Run the migrations:
   ```bash
   yarn typeorm migration:run
   ```

5. Start the server:
   ```bash
   yarn dev:server
   ```

## Technologies Used

- Node.js
- Express
- TypeORM
- PostgreSQL
- Multer (for file uploads)
- CSV-Parse (for CSV file handling)

---

This is a backend project for managing financial transactions and balances through a RESTful API.
