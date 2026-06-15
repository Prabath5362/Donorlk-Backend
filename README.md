# Blood Donation Tracking System - Backend

A simple MERN stack backend for a Blood Donation Tracking system with MongoDB integration.

## Features

✅ Donor Management (CRUD operations)
✅ Blood Request Management
✅ Blood Type Filtering
✅ Statistics & Analytics
✅ MongoDB Integration with Mongoose
✅ CORS Support for Frontend
✅ Error Handling Middleware
✅ RESTful API

## Installation

### 1. Install Dependencies
```bash
npm install
```

### 2. Setup Environment Variables
Create a `.env` file in the server directory:
```bash
cp .env.example .env
```

Edit `.env` and add your MongoDB connection string:
```
MONGODB_URI=mongodb://localhost:27017/donor-tracking
PORT=5000
```

### 3. MongoDB Setup

**Option A: Local MongoDB**
```bash
# Make sure MongoDB is running on your machine
mongod
```

**Option B: MongoDB Atlas (Cloud)**
- Create account at https://www.mongodb.com/cloud/atlas
- Create a cluster and get connection string
- Update `MONGODB_URI` in `.env`

### 4. Start the Server

**Development (with auto-reload):**
```bash
npm run dev
```

**Production:**
```bash
npm start
```

Server will run on `http://localhost:5000`

## API Endpoints

### Donor Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/donors` | Get all donors |
| GET | `/api/donors/:id` | Get donor by ID |
| GET | `/api/donors/blood-type/:bloodType` | Get available donors by blood type |
| POST | `/api/donors` | Create new donor |
| PUT | `/api/donors/:id` | Update donor |
| DELETE | `/api/donors/:id` | Delete donor |

**Create Donor Example:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "0712345678",
  "bloodType": "O+",
  "age": 25,
  "location": "Colombo"
}
```

### Blood Request Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/blood-requests` | Get all blood requests |
| GET | `/api/blood-requests/:id` | Get request by ID |
| POST | `/api/blood-requests` | Create new blood request |
| PUT | `/api/blood-requests/:id` | Update blood request |
| DELETE | `/api/blood-requests/:id` | Delete blood request |

**Create Blood Request Example:**
```json
{
  "patientName": "Jane Smith",
  "bloodType": "A+",
  "hospital": "City Hospital",
  "urgencyLevel": "high",
  "unitsNeeded": 2,
  "reason": "Surgery"
}
```

### Statistics Endpoint

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/statistics` | Get system statistics |

### Health Check

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/health` | Server health check |

## Project Structure

```
server/
├── server.js          # Main server file with routes and models
├── package.json       # Dependencies
├── .env              # Environment variables (create from .env.example)
├── .env.example      # Environment template
└── README.md         # This file
```

## Blood Types Supported

- O+
- O-
- A+
- A-
- B+
- B-
- AB+
- AB-

## Urgency Levels

- low
- medium
- high
- critical

## Request Status

- pending
- fulfilled
- cancelled

## Technologies Used

- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **CORS** - Cross-Origin Resource Sharing
- **dotenv** - Environment variable management

## Next Steps

1. Create a React frontend to consume this API
2. Add authentication & authorization
3. Add email notifications
4. Implement user roles (donor, hospital, admin)
5. Add data validation & sanitization
6. Deploy to production

## License

ISC
