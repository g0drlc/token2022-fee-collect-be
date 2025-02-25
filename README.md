
# Token2022 Fee Collection Backend

Welcome to the **Token2022 Fee Collection Backend** repository! This project is designed to handle the fee collection logic for the Token2022 ecosystem, providing a seamless backend solution for processing payments, token transfers, and fee management.

## Overview

The **Token2022 Fee Collection Backend** is responsible for managing the fee structure associated with Token2022 transactions. It connects with various smart contracts and handles the logic for fee collection, ensuring accurate and timely payment processing.

## Features

- **Fee Calculation**: Automatically calculates fees for token transactions.
- **Payment Gateway**: Integrates with token and fiat payment gateways to process fees.
- **Smart Contract Integration**: Connects with the Token2022 smart contracts to collect fees directly from transactions.
- **Database Management**: Stores and tracks fee collection history, including transaction IDs, amounts, and payment status.
- **API Endpoints**: Exposes RESTful API endpoints for external services to interact with the fee collection system.
- **Security**: Implements security best practices for protecting sensitive data, including API key authentication and encryption.

## Technologies Used

- **Node.js**: Backend logic and server.
- **Express.js**: API server for handling HTTP requests.
- **MongoDB**: Database to store transaction records and fee information.
- **Web3.js**: Interaction with Ethereum-based smart contracts.
- **JWT**: Token-based authentication for API security.
- **dotenv**: Manage environment variables.

## Setup

### Prerequisites

Before you get started, make sure you have the following installed:

- Node.js (v14 or later)
- MongoDB
- Web3.js
- Git

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/g0drlc/token2022-fee-collect-be.git
   cd token2022-fee-collection-backend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with the following variables:

   ```env
   DB_URI=mongodb://localhost:27017/token2022-fee
   PRIVATE_KEY=your-private-key
   INFURA_URL=https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID
   JWT_SECRET=your-jwt-secret
   ```

4. Run the application:

   ```bash
   npm start
   ```

### API Endpoints

#### 1. **POST /api/fees**

   Calculate the fee for a transaction.

   - **Request Body**:
   
     ```json
     {
       "amount": "1000",
       "token": "Token2022"
     }
     ```

   - **Response**:
   
     ```json
     {
       "fee": "10",
       "totalAmount": "1010"
     }
     ```

#### 2. **POST /api/transactions**

   Process a transaction and collect the associated fee.

   - **Request Body**:
   
     ```json
     {
       "transactionId": "123456",
       "amount": "1000",
       "fee": "10",
       "fromAddress": "0xabc123",
       "toAddress": "0xdef456"
     }
     ```

   - **Response**:
   
     ```json
     {
       "status": "success",
       "transactionId": "123456",
       "feeCollected": "10"
     }
     ```

### Database Schema

- **Transactions**:
  - `transactionId`: String (Unique ID for the transaction)
  - `amount`: Number (Amount of the transaction)
  - `fee`: Number (Calculated fee for the transaction)
  - `fromAddress`: String (Sender's address)
  - `toAddress`: String (Recipient's address)
  - `status`: String (Pending/Completed)

## Contributing

We welcome contributions to this project! If you find a bug or want to add a new feature, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
