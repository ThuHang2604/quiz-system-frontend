# Quiz System: Frontend

Modern React web app for the **Online Question & Quiz Management System**. Students can take quizzes and see their score instantly; admins can manage quizzes and questions from a protected dashboard.

🔗 **Live demo:** <https://quiz-system-frontend-eight.vercel.app>

⚙️ **Backend API:** [quiz-system-backend](https://github.com/ThuHang2604/quiz-system-backend) · [Swagger docs](https://quiz-system-backend-seven.vercel.app/api-docs)

## Features

**Everyone**
- Register / log in with JWT; the session is kept after a page refresh.

**Students**
- Browse available quizzes.
- Take a quiz question by question and get the score and percentage at the end.

**Admins** (protected `/admin` routes)
- Create, edit and delete quizzes.
- Add, edit and delete questions (4 options, mark the correct one).

**UI / UX**
- Responsive layout built with Bootstrap 5 and custom styles.
- Custom toast notifications and confirmation dialogs.
- Route guard that redirects non-admin users away from admin pages.

## Tech Stack

React · Vite · Redux + Redux Thunk · React Router · Axios · Bootstrap 5 · Vercel

## Pages

| Route | Page | Access |
|---|---|---|
| `/login`, `/register` | Authentication | Public |
| `/dashboard` | List of quizzes | Logged-in user |
| `/quiz/:id` | Take a quiz and view the result | Logged-in user |
| `/admin` | Manage quizzes | Admin |
| `/admin/quiz/:id` | Manage a quiz's questions | Admin |

## Getting Started

**Requirements:** Node.js v18+ and a running instance of the [backend API](https://github.com/ThuHang2604/quiz-system-backend).

```bash
git clone https://github.com/ThuHang2604/quiz-system-frontend.git
cd quiz-system-frontend
npm install
npm run dev
```

Open `http://localhost:5173`. In development, API requests (`/auth`, `/quizzes`, `/questions`) are proxied to the backend; set the backend address in `vite.config.js`.

| Script | Description |
|---|---|
| `npm run dev` | Start the dev server |
| `npm run build` | Build for production |
| `npm run preview` | Preview the production build |

## Project Structure

```
src/
├── components/   # Navbar, AdminRoute (route guard), ToastContainer
├── pages/        # Login, Register, Dashboard, QuizPage, AdminDashboard, AdminQuizDetail
├── redux/        # store, actions (auth, quiz) and reducers
├── utils/        # toast helper
├── App.jsx       # Routes
└── main.jsx      # Entry point
```

## Try It Out

Log in on the [live demo](https://quiz-system-frontend-eight.vercel.app) with a demo account:

| Role | Username | Password |
|---|---|---|
| Admin | `admin` | `123` |
| Student | `user` | `123` |

You can also click **Register** to create your own account (tick **Register as Admin** to try the admin features).

> The "Register as Admin" option is for demo purposes only. In production, roles should be assigned server-side.

## Notes

- Built as an assignment for the Node.js course (SDN301m) at FPT University, as the frontend for the [quiz-system-backend](https://github.com/ThuHang2604/quiz-system-backend) API.

## Author

**Do Thi Thu Hang** · [@ThuHang2604](https://github.com/ThuHang2604)
