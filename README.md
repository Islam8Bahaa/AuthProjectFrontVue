# 🌟 Auth Vue Project Setup Guide

Welcome to the Auth Vue project! Follow these steps to get your project up and running smoothly. If you encounter any issues, feel free to reach out. Happy coding 😄!

## 🛠️ Prerequisites

Before you start, make sure you have the following installed:

- Node.js & npm latest version

## 📦 Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/Islam8Bahaa/AuthProjectFrontVue.git
cd AuthProjectFrontVue
```

## 🔧 Install Dependencies

Install all the necessary dependencies using npm:

```bash
npm install
```

## 🌐 API Endpoints

Ensure your Laravel backend is running and the API endpoints are properly set up:

- **Register**: `POST /api/register`
- **Login**: `POST /api/login`
- **Logout**: `POST /api/logout` (requires Bearer token)

## 🚀 Running the Project

To start the development server, run:

```bash
npm run dev
```

Your project should now be running at `http://localhost:3000` or any URL will show up to you when running npm run dev.

## 📂 Project Structure

- `src/` - Main source directory
  - `assets/` - Static assets like images and styles
  - `components/` - Vue components
  - `router/` - Vue Router setup
  - `views/` - View components for different pages
  - `App.vue` - Root component
  - `main.js` - Main entry point
- `public/` - Static files served directly
- `package.json` - Project configuration and dependencies

## 🌟 Features

- **User Authentication**: Register, login, and logout functionality.
- **Navigation Guard**: Redirect based on authentication state.
- **State Management**: Manage state using Vue's reactive system.

## 🔄 Important Scripts

- `npm run dev`: Start the development server.

## 🎨 Styling

We are using SCSS for styling. Ensure you have a preprocessor set up to handle SCSS files.


Happy Coding! 💻✨
