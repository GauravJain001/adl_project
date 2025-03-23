# Project Setup Guide

## Prerequisites

Ensure the following are installed on your system:

1. Node.js (v16 or higher): Download from Node.js official website[1].
2. npm (comes with Node.js).
3. MongoDB: Ensure a running MongoDB instance (local or cloud-based like MongoDB Atlas)[2].

## Step 1: Clone the Repository

1. Open a terminal.
2. Run the following command to clone the repository:

```bash
git clone https://github.com/GauravJain001/adl_project.git
```

3. Navigate into the project folder:

```bash
cd adl_project
```

## Step 2: Backend Setup

Navigate to the backend folder (e.g., server) and follow these steps:

### 1. Install Dependencies

Run the following command to install backend dependencies:

```bash
npm install
```

### 2. Configure Environment Variables

Create a `.env` file in the backend folder and add the following:

```
PORT=9000
MONGO_URL=""
```

Replace `` with your MongoDB connection string. If you're using MongoDB Atlas, it will look something like this:

```
mongodb+srv://:@cluster.mongodb.net/?retryWrites=true&w=majority
```

### 3. Start Backend Server

Run the following command to start the server:

```bash
node index.js
```

The backend will start at `http://localhost:9000`. Verify it by visiting one of the API endpoints in your browser or Postman:

- `http://localhost:9000/kpi/kpis`
- `http://localhost:9000/product/products`
- `http://localhost:9000/transaction/transactions`

## Step 3: Frontend Setup

Navigate to the frontend folder (client) and follow these steps:

### 1. Install Dependencies

Run the following command to install frontend dependencies:

```bash
npm install
```

### 2. Configure Environment Variables

Create a `.env` file in the frontend folder and add the following:

```
VITE_BASE_URL=http://localhost:9000
```

This sets up the base URL for API calls to point to your backend.

### 3. Start Frontend Server

Run the following command to start the Vite development server:

```bash
npm run dev
```

The frontend will start at `http://localhost:5173`. Open this URL in your browser.

## Step 4: Test Integration

1. Ensure both servers are running:
   - Backend at `http://localhost:9000`
   - Frontend at `http://localhost:5173`
2. Navigate through your frontend application and verify that data is being fetched from the backend.

## Step 5: Debugging Common Issues

### Backend Issues:

- If you encounter database connection errors, ensure MongoDB is running and your connection string is correct[7].
- Check for missing dependencies by running:

```bash
npm install
```

### Frontend Issues:

- If API calls fail, check for CORS errors in the browser console.
- Ensure the `VITE_BASE_URL` in `.env` matches your backend URL (`http://localhost:9000`).
