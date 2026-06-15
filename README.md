# Task-Management-Application
A full-stack task management web application built with React, Node.js/Express, MongoDB, and Socket.io for real-time updates.

Tech Stack

Frontend uses React 18, React Router v6, Axios, and Socket.io-client. The backend runs on Node.js and Express.js with Socket.io. The database is MongoDB with Mongoose. Authentication is handled via JWT and bcryptjs. Real-time features use WebSockets through Socket.io.

Project Structure

The project has two main folders — backend and frontend. The backend contains models (User and Task schemas), routes (auth and tasks), middleware (JWT auth), and server.js as the entry point. The frontend src folder contains components (TaskCard, TaskModal, ConfirmModal), context (AuthContext for global auth state), hooks (useSocket for real-time), pages (Login, Register, Dashboard), and utils (Axios instance with interceptors).

Setup Instructions

Prerequisites: Node.js 16 or higher, and MongoDB either locally or via MongoDB Atlas.

Step 1 — Open the project folder in VS Code.

Step 2 — Set up environment variables by copying the example file:
cp backend/.env.example backend/.env

Then edit backend/.env with your values: PORT as 5000, MONGODB_URI pointing to your MongoDB instance, a JWT_SECRET of your choice, and CLIENT_URL as http://localhost:3000.

Step 3 — Install dependencies by running npm install in the root, then npm install in both the backend and frontend folders. Or just run: npm run install:all

Step 4 — Start both servers with: npm run dev

This starts the backend on http://localhost:5000 and the frontend on http://localhost:3000 at the same time.

API Endpoints

Auth routes: POST /api/auth/register to create an account, POST /api/auth/login to sign in, GET /api/auth/me to get the current user.

Task routes (all require a Bearer token): GET /api/tasks to fetch all tasks with optional filters, POST /api/tasks to create a task, PUT /api/tasks/:id to update a task, DELETE /api/tasks/:id to delete a task, and PATCH /api/tasks/:id/status for a quick status update.

Features

User auth with JWT tokens stored in localStorage. Full CRUD operations for tasks with validation. Status tracking across todo, in-progress, and completed — click any status badge to cycle it. Priority levels (High, Medium, Low) shown with color-coded card borders. Due date support with overdue detection. Comma-separated tags on each task. Real-time updates via Socket.io so changes appear instantly. Live search and filter by status and priority. Skeleton loading states while data loads. Fully responsive layout for mobile and desktop. Dark theme with purple and teal accents.


This project covers all four key features from the assignment — user authentication and authorization, full CRUD operations for tasks, real-time updates using WebSockets (the optional Socket.io requirement), and a responsive design that works on both web and mobile screens.
