## 🖥️ Backend Setup

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v16 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [PostgreSQL](https://www.postgresql.org/)
- [Prisma CLI](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch) (`npm install -g prisma`)

## Setup Instructions

### 1. Install Dependencies

Install all required Node.js packages by running:

```bash
npm install
```

This will fetch all dependencies listed in `package.json`.

### 2. Configure Environment Variables

Create a `.env` file in the project root by copying the `.env.example` file. Then, update it with your credentials:

```env
DATABASE_URL="postgresql://your_db_user:your_db_password@localhost:5432/multi_user_proyek_db?schema=public"
JWT_SECRET=your_jwt_secret_key
PORT=5000
```

- Replace `your_db_user` and `your_db_password` with your PostgreSQL credentials.
- Set `your_jwt_secret_key` to a secure, unique string (e.g., a 32-character random key).
- Ensure the database `multi_user_proyek_db` exists in your PostgreSQL instance.

### 3. Run Prisma Migrations

Generate the Prisma client and apply database migrations with the following commands:

```bash
npx prisma generate
npx prisma migrate dev --name init
```

This sets up the database schema and prepares the Prisma client for use.

### 4. Start the Server

Launch the backend server with `nodemon` for automatic restarts during development:

```bash
npx nodemon index.js
```

Your server should now be running on `http://localhost:5000`! 🎉
