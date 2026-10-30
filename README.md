# ⚡ SlotX

> **Book smarter. Lock faster. Never double-book.**

SlotX is a concurrency-safe seat reservation platform built to handle simultaneous booking requests without compromising data consistency. Powered by Redis distributed locking and PostgreSQL transactions, it ensures reliable seat allocation even under high traffic.

## 🚀 Key Features

- **Distributed Seat Locking** – Uses Redis locks to prevent multiple users from reserving the same seat simultaneously.
- **Atomic Booking Transactions** – Leverages PostgreSQL transactions to maintain consistent and reliable booking records.
- **Real-Time Seat Availability** – Tracks seat states across three stages: Available, Locked, and Booked.
- **Automatic Lock Expiration** – Releases temporary reservations using Redis TTL when users fail to complete bookings.
- **Secure Authentication** – Implements JWT-based access and refresh token authentication.
- **Scalable Architecture** – Separates temporary reservation state from persistent booking data.

## 🏗️ System Architecture

```text
           React + TypeScript
                   |
                   ▼
             Node.js API
                   |
            ┌──────┴──────┐
            ▼             ▼
          Redis       PostgreSQL
       (Seat Locks)   (Bookings)
```

## 🔄 Booking Workflow

```text
     Select Seat
          |
          ▼
    Acquire Redis Lock
          |
          ▼
  Validate Seat Availability
          |
          ▼
  Execute PostgreSQL Transaction
          |
          ▼
      Commit Booking
          |
          ▼
      Release Lock
          |
          ▼
    Booking Confirmed
```

## 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React 19, TypeScript |
| State Management | Zustand |
| Backend | Node.js, Express.js |
| Database | PostgreSQL |
| Distributed Locking | Redis |
| Authentication | JWT |

## 📂 Project Structure

```text
SlotX/
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── middleware/
│   ├── services/
│   ├── utils/
│   └── db/
│
└── frontend/
    ├── pages/
    ├── stores/
    ├── components/
    └── types/
```

## ⚙️ Getting Started

### Prerequisites

- Node.js
- PostgreSQL
- Redis
- npm

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/Devadharshini784/SlotX.git
cd SlotX
```

**2. Install backend dependencies**

```bash
cd backend
npm install
```

**3. Install frontend dependencies**

```bash
cd ../frontend
npm install
```

**4. Configure Environment Variables**

Set up the required database and Redis connection details, along with your authentication secrets, in the appropriate environment files.

**5. Start the application**

Run the backend and frontend using their respective development scripts.

## 🧠 Engineering Concepts

SlotX demonstrates practical backend and distributed systems concepts:

- Concurrency Control
- Race Condition Prevention
- Redis Distributed Locking
- TTL-Based Resource Management
- ACID Transactions
- Database Consistency
- JWT Authentication
- Distributed Coordination
- Scalable System Architecture

## 🔮 Future Enhancements

- Payment Gateway Integration
- Booking Analytics Dashboard
- Kafka-Based Event Processing
- Kubernetes Deployment
- Prometheus & Grafana Monitoring

## 👩‍💻 Author

**DEVADHARSHINI D**

[GitHub](https://github.com/Devadharshini784)

---

<p align="center">
  ⚡ <strong>SlotX</strong> | Built for reliable reservations at scale.
</p>
