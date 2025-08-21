# Chit-Chatra - MERN Stack Chat Application

Chit-Chatra is a real-time chat application built using the MERN stack (MongoDB, Express.js, React.js, Node.js) with Socket.io for real-time messaging and Chakra UI for the frontend design.

---

## Table of Contents

- [Project Structure](#project-structure)
  - [Root Directory](#root-directory)
  - [backend/](#backend)
  - [frontend/](#frontend)
  - [screenshots/](#screenshots)
- [Features](#features)
- [Getting Started](#getting-started)
- [Scripts](#scripts)
- [Environment Variables](#environment-variables)
- [License](#license)

---

## Project Structure

### Root Directory

- `.env`  
  Environment variables for backend (e.g., database URI, JWT secret, etc.).

- `package.json`  
  Main project configuration and scripts for backend and frontend.

- `README.md`  
  Project documentation.

---

### backend/

Contains all server-side code (Node.js + Express + MongoDB).

#### Folders & Files:

- **server.js**  
  Entry point for the backend server. Sets up Express, connects to MongoDB, configures routes, error handling, and initializes Socket.io for real-time communication.

- **config/**

  - `db.js`  
    MongoDB connection logic.
  - `generateToken.js`  
    Utility to generate JWT tokens for authentication.

- **controllers/**

  - `userControllers.js`  
    Handles user registration, login, and user search.
  - `chatControllers.js`  
    Handles chat creation (one-to-one and group), fetching chats, renaming groups, adding/removing users from groups.
  - `messageControllers.js`  
    Handles sending and retrieving messages for chats.

- **data/**

  - `data.js`  
    Sample chat data for testing or seeding the database.

- **middleware/**

  - `authMiddleware.js`  
    Middleware to protect routes using JWT authentication.
  - `errorMiddleware.js`  
    Middleware for handling errors and 404 responses.

- **models/**

  - `userModel.js`  
    Mongoose schema/model for users, including password hashing.
  - `chatModel.js`  
    Mongoose schema/model for chats (group and one-to-one).
  - `messageModel.js`  
    Mongoose schema/model for messages.

- **routes/**
  - `userRoutes.js`  
    API routes for user-related operations (register, login, search).
  - `chatRoutes.js`  
    API routes for chat-related operations (create, fetch, group management).
  - `messageRoutes.js`  
    API routes for message-related operations (send, fetch).

---

### frontend/

Contains all client-side code (React.js + Chakra UI).

#### Folders & Files:

- **public/**  
  Static files and HTML template for the React app.

- **src/**  
  Main source code for the React frontend.

  - **App.js / App.css**  
    Main React component and global styles.

  - **index.js / index.css**  
    Entry point for the React app and base styles.

  - **reportWebVitals.js**  
    Performance measuring utility.

  - **background.png / background.jpg**  
    Background images for the app.

  - **animations/**

    - `typing.json`  
      Lottie animation for typing indicator.

  - **components/**  
    Reusable React components:

    - `Chatbox.js`  
      Displays the current chat conversation.
    - `ChatLoading.js`  
      Skeleton loader for chat lists.
    - `MyChats.js`  
      Displays the list of chats for the user.
    - `ScrollableChat.js`  
      Handles auto-scrolling for chat messages.
    - `SingleChat.js`  
      Main chat window for a selected conversation.
    - `styles.css`  
      Component-specific styles.

    - **Authentication/**

      - `Login.js`  
        Login form and logic.
      - `Signup.js`  
        Signup form and logic.

    - **miscellaneous/**

      - `GroupChatModal.js`  
        Modal for creating group chats.
      - `ProfileModal.js`  
        Modal for viewing user profiles.
      - `SideDrawer.js`  
        Sidebar for searching users and notifications.
      - `UpdateGroupChatModal.js`  
        Modal for updating group chat details.

    - **userAvatar/**
      - `UserBadgeItem.js`  
        Badge component for displaying users in a group.
      - `UserListItem.js`  
        List item for displaying users in search results.

  - **config/**

    - `ChatLogics.js`  
      Utility functions for chat UI logic (e.g., sender display, message grouping).

  - **Context/**

    - `ChatProvider.js`  
      React Context for global chat state management.

  - **data/**

    - `messages.js`  
      Sample messages data for frontend testing.

  - **Pages/**
    - `Homepage.js`  
      Landing page with login/signup tabs.
    - `Chatpage.js`  
      Main chat interface after login.

---

### screenshots/

Contains screenshots of the application UI for documentation or promotional purposes.

---

## Features

- User authentication (JWT-based)
- Real-time messaging with Socket.io
- One-to-one and group chats
- Group chat management (add/remove users, rename group, leave group)
- User search and chat initiation
- Responsive UI with Chakra UI
- Profile viewing and editing
- Typing indicators and notifications

---

## Getting Started

### Prerequisites

- Node.js (v12+)
- MongoDB instance (local or cloud)

### Installation

1. **Clone the repository:**

   ```sh
   git clone <repo-url>
   cd ChitChatra
   ```

2. **Install backend dependencies:**

   ```sh
   npm install
   ```

3. **Install frontend dependencies:**

   ```sh
   cd frontend
   npm install
   ```

4. **Set up environment variables:**

   - Create a `.env` file in the root with the following:
     ```
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     NODE_ENV=development
     PORT=5000
     ```

5. **Run the backend server:**

   ```sh
   npm run server
   ```

6. **Run the frontend app:**

   ```sh
   cd frontend
   npm start
   ```

   The frontend will be available at [http://localhost:3000](http://localhost:3000) and the backend at [http://localhost:5000](http://localhost:5000).

---

## Scripts

- **Backend**

  - `npm run server` — Starts backend with nodemon.
  - `npm start` — Starts backend with Node.js.

- **Frontend**
  - `npm start` — Starts React development server.
  - `npm run build` — Builds the React app for production.

---

## Environment Variables

- `MONGO_URI` — MongoDB connection string.
- `JWT_SECRET` — Secret key for JWT authentication.
- `NODE_ENV` — Set to `production` or `development`.
- `PORT` — Port for backend server (default: 5000).

---

## License

This project is licensed under the ISC License.

---

## Author

Nishant Garg

---

For any questions or issues, please open an issue on the repository.
