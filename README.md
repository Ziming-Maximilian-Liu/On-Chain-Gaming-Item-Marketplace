# On-Chain Gaming Item Marketplace

This is a full-stack application for an **On-Chain Gaming Item Marketplace**, where users can place buy and sell orders for different gaming items like **Characters**, **Weapons**, and **Accessories**. The application uses **parallelized blockchain concepts** to efficiently process multiple orders in different item categories.

## Project Structure

The project consists of two main components:

1. **Backend**: An Express.js server that handles user orders and processes them using sharded architecture.
2. **Frontend**: A React application that provides a user-friendly interface for placing orders and processing them.

### Backend

- **Technology**: Node.js with Express.js
- **Endpoints**:
  - `POST /api/order` - Place an order for a game item.
  - `GET /api/process-orders` - Process all placed orders in parallel.
- **Parallelization**: The backend uses a sharding mechanism to handle different categories of gaming items (Characters, Weapons, Accessories). Each shard processes its orders concurrently to optimize performance.

### Frontend

- **Technology**: React.js
- **Features**:
  - A form to place a buy or sell order for a gaming item.
  - A button to trigger the processing of all orders.
  - Displays messages about the status of orders.

## How to Run the Project

### Prerequisites

- **Node.js** and **npm** installed.
- **React** (frontend setup is included).

### Installation

1. **Clone the repository**
   ```sh
   git clone <repository-url>
   cd onchain-gaming-item-marketplace
   ```

2. **Install dependencies for the backend**
   ```sh
   cd backend
   npm install
   ```

3. **Start the backend server**
   ```sh
   npm start
   ```
   The backend server will run on `http://localhost:3000`.

4. **Install dependencies for the frontend**
   ```sh
   cd ../frontend
   npm install
   ```

5. **Start the frontend application**
   ```sh
   npm start
   ```
   The frontend application will run on `http://localhost:3001`.

### API Endpoints

- **Place an Order**: `POST http://localhost:3000/api/order`
  - **Request Body**:
    ```json
    {
      "userId": "<USER_ID>",
      "itemId": "<ITEM_ID>",
      "category": "<CATEGORY>",
      "orderType": "<ORDER_TYPE>"
    }
    ```
  - **Response**: Confirmation of the placed order.

- **Process Orders**: `GET http://localhost:3000/api/process-orders`
  - **Response**: Confirmation that all orders have been processed.

## Application Logic

### Sharding and Parallel Processing

- The backend uses **shards** to represent different categories of gaming items (Characters, Weapons, Accessories).
- Each shard processes its assigned orders **concurrently** using JavaScript's asynchronous capabilities, ensuring that non-conflicting orders are processed efficiently.

### User Workflow

1. **Place an Order**: Users can enter their details, select an item category, and place a buy or sell order.
2. **Process Orders**: Once enough orders are placed, users can click a button to process all orders in parallel.
3. **Order Status**: The frontend displays messages to inform the user of the success or failure of their actions.

## Future Improvements

- **Blockchain Integration**: Connect the backend to an actual blockchain network to store and verify orders.
- **Authentication**: Add user authentication to ensure secure access and prevent fraudulent activities.
- **Order Book**: Develop a more sophisticated on-chain order book for improved tracking of buy/sell orders.

## Technologies Used

- **Backend**: Node.js, Express.js
- **Frontend**: React.js, Axios

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue to suggest improvements or report bugs.

## License

This project is licensed under the GNU 3.0 License.

## Contact

For any questions, please contact the repository owner.

