# Task Management System

A full-stack web application for managing tasks, boards, and team collaboration. Built with Express.js backend and React frontend with Tailwind CSS for modern UI design.

## Features

- **User Authentication**: Secure login and registration with JWT-based authentication
- **Board Management**: Create, manage, and organize project boards
- **Task Management**: Create, update, and organize tasks with kanban board view
- **Drag & Drop**: Intuitive drag-and-drop interface for task management using dnd-kit
- **User Profiles**: Manage user profiles with image uploads via Cloudinary
- **Notifications**: Real-time notifications for task assignments and updates
- **Board Invitations**: Invite other users to collaborate on boards
- **Comments**: Add comments to tasks for better team communication
- **Responsive Design**: Mobile-friendly interface built with Tailwind CSS and DaisyUI

## Tech Stack

### Backend
- **Node.js** with Express.js
- **MongoDB** with Mongoose ORM
- **JWT** for authentication
- **Bcryptjs** for password hashing
- **Cloudinary** for image uploads
- **Multer** for file handling
- **CORS** for cross-origin requests

### Frontend
- **React 19** with React Router
- **Vite** for build tooling
- **Tailwind CSS** for styling
- **DaisyUI** for UI components
- **dnd-kit** for drag-and-drop functionality
- **React Hook Form** for form management
- **React Hot Toast** for notifications
- **Axios** for API calls

## Project Structure

```
task-management-system/
├── backend/
│   ├── src/
│   │   ├── index.js
│   │   ├── controllers/        # Request handlers
│   │   ├── models/             # MongoDB schemas
│   │   ├── routes/             # API endpoints
│   │   ├── middleware/         # Custom middleware
│   │   ├── library/            # Utility libraries
│   │   └── database/           # Database connection
│   ├── temp/
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/         # Reusable React components
│   │   ├── pages/              # Page components
│   │   ├── context/            # React context (Auth)
│   │   ├── hooks/              # Custom hooks
│   │   ├── layouts/            # Layout components
│   │   ├── library/            # API utilities
│   │   └── assets/             # Static assets
│   ├── public/                 # Public files
│   └── package.json
└── README.md
```

## Installation

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- MongoDB database
- Cloudinary account (for image uploads)

### Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd task-management-system
   ```

2. **Install dependencies**
   ```bash
   npm run build
   ```
   This command will install dependencies for both backend and frontend.

3. **Environment Variables**

   Create a `.env` file in the `backend` directory with the following variables:
   ```
   PORT=5000
   MONGODB_URI=<your-mongodb-connection-string>
   JWT_SECRET=<your-jwt-secret-key>
   CLOUDINARY_NAME=<your-cloudinary-name>
   CLOUDINARY_API_KEY=<your-cloudinary-api-key>
   CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
   NODE_ENV=development
   ```

## Running the Application

### Development Mode

**Backend**:
```bash
cd backend
npm run dev
```
The server will run on `http://localhost:5000`

**Frontend** (in a new terminal):
```bash
cd frontend
npm run dev
```
The app will run on `http://localhost:5173`

### Production Mode

Build and start the application:
```bash
npm run build
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/signup` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Boards
- `GET /api/boards` - Get all user boards
- `POST /api/boards` - Create a new board
- `PUT /api/boards/:id` - Update a board
- `DELETE /api/boards/:id` - Delete a board
- `POST /api/boards/:id/invite` - Invite user to board

### Tasks
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task
- `POST /api/tasks/:id/assign` - Assign task to user
- `POST /api/tasks/:id/comment` - Add comment to task

### Notifications
- `GET /api/notifications` - Get user notifications
- `PUT /api/notifications/:id/read` - Mark notification as read
- `DELETE /api/notifications/:id` - Delete notification

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update user profile

## Key Features Explained

### Kanban Board
The application features a drag-and-drop kanban board interface that allows users to:
- Organize tasks in different columns (To Do, In Progress, Done, etc.)
- Drag and drop tasks between columns
- View task details and make quick updates

### Authentication
- Secure JWT-based authentication
- Passwords hashed with bcryptjs
- Protected routes for authenticated users

### File Uploads
- Images uploaded to Cloudinary for fast, reliable storage
- Used for user avatars and board images

### Real-time Notifications
- Users receive notifications for:
  - Task assignments
  - Board invitations
  - Task updates and comments

## Database Schema

### User
- Email (unique)
- Password (hashed)
- Name
- Avatar URL
- Created at timestamp

### Board
- Title
- Description
- Owner (User reference)
- Members (User references)
- Created at timestamp

### Task
- Title
- Description
- Status (Todo, In Progress, Done, etc.)
- Board (Board reference)
- Assignee (User reference)
- Due date
- Priority
- Created at timestamp

### Notification
- Type (assignment, invitation, update, etc.)
- User (User reference)
- Related Board/Task
- Read status
- Created at timestamp

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License.

## Support

For support, please open an issue in the repository or contact the development team.

---

**Happy Task Managing! 🚀**
