# User Management Web Application

A full-stack web application for user registration, authentication, and administration.

## 🚀 Technologies Used

### 🌐 Frontend

- React + JavaScript
- Next.js
- TailwindCSS

### 🔧 Backend

- Node.js + TypeScript
- Express.js
- PostgreSQL (Prisma ORM)

### 🐳 DevOps

- Docker & `docker-compose` for PostgreSQL orchestration and isolation
- GitHub for version control and collaboration
- Gitmoji for conventional commit messages

## ✅ Requirements Implemented

### 📌 Database

- A **relational database** is used (PostgreSQL).
- A **unique index** is created on the `email` field to guarantee email uniqueness at the **storage level**, ensuring consistency even with concurrent requests.
- A **primary key** is also defined separately from the unique index.

### 🔐 Authentication & Authorization

- Fully functional **user registration** and **login system**.
- Only authenticated users can access the user management panel.
- **Unauthenticated users** are only allowed to access the login and registration forms.
- Blocked users cannot log in.
- Deleted users may re-register using the same email.

### 🧾 Admin Table (User Management Panel)

- Accessible only to authenticated users.
- Includes the following columns:
  - [ ] **Checkbox** for selection (no label).
  - **Name**
  - **Email**
  - **Last Login** (or activity time)
  - **Status** (Active / Blocked)
- The leftmost column contains **checkboxes without labels** for multi-selection. The header contains a **"select all" checkbox**.
- The table is **sortable**, with default sorting by **last login time**.
- Fully styled as a **table** using Bootstrap.

### 🧰 Toolbar (Above the Table)

- A **toolbar** with global actions (no buttons per row):
  - **Block** (text button)
  - **Unblock** (icon button)
  - **Delete** (icon button)
- Actions apply to **selected users** (including self).

### ✅ Functional Rules

- Users can block, unblock, or delete **themselves or any other user**.
- If a user is blocked or deleted during an active session, they are not immediately redirected. The session becomes invalid **only when an action is attempted**, triggering a redirect to the login page.
- The backend checks **on every request (except registration and login)** whether the user still exists and is not blocked.

### 🧾 UI Guidelines

- **No row-level buttons**.
- **No browser alerts**, animations, or background images.
- **CSS framework** is used to ensure responsive and consistent styling across devices and browsers.

### ⚠️ Error Handling & Feedback

- Proper **error messages** are shown for failed operations.
- **Tooltips** are used where appropriate to describe actions.
- **Status messages** are shown after operations to notify success.

### 📂 Features Planned

- 🔄 Pagination and filtering
- 📊 Mini-graphs for user activity (optional)
- 🌐 Deployment (e.g., Vercel / Render / Railway)

### 🧠 Notes

- The purpose of this application is to demonstrate skills in:
  - Secure authentication
  - Relational DB design with unique constraints
  - Frontend UI using component libraries and best practices
  - Backend validation and authorization middleware
