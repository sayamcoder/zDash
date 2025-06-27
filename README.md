# zDashboard - Professional Minecraft Hosting Panel



ProHost is a modern, feature-rich, and professional web dashboard for managing game servers, built with Node.js. It integrates directly with the Pterodactyl panel to provide a seamless user experience, including automatic user and server creation.

This project serves as a powerful foundation for anyone looking to build their own game hosting service.

## ✨ Features

-   **User Authentication:** Secure local login/registration and social logins (Google & Discord).
-   **Persistent Database:** Uses `better-sqlite3` for a simple, file-based database that requires no external setup.
-   **Pterodactyl Integration:**
    -   **Automatic User Creation:** New dashboard sign-ups automatically create a corresponding user on the Pterodactyl panel.
    -   **Server Creation Hook:** Users can create new game servers directly from the dashboard.
-   **Currency & Rewards System:**
    -   In-game "coins" for purchasing servers.
    -   AFK page to earn coins over time with a visually engaging progress bar.
-   **Admin Panel:**
    -   View all registered users.
    -   Customize global site branding (site title and header name).
-   **Modern Frontend:**
    -   Clean, responsive, dark-themed UI.
    -   Interactive elements with smooth CSS animations.
    -   Icon-driven navigation for a professional feel.

## 🛠️ Tech Stack

-   **Backend:** Node.js, Express.js
-   **Frontend:** EJS (Embedded JavaScript templates), CSS3
-   **Authentication:** Passport.js (Local, Google OAuth 2.0, Discord)
-   **Database:** better-sqlite3 (File-based)
-   **Pterodactyl API:** Axios

---

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

1.  **Node.js and npm:** [Download & Install Node.js](https://nodejs.org/en/) (v16 or newer recommended).
2.  **A running Pterodactyl Panel:** You must have a fully functional Pterodactyl panel installed and accessible.
3.  **Git:** Required for cloning the repository.

### ⚙️ Installation & Configuration

**1. Clone the Repository**

Open your terminal or command prompt and clone the project from GitHub.

```bash
git clone https://github.com/sayamcoder/zDash.git
cd zDash
unzip dashboard.zip
cd dashboard
```

**2. Install Dependencies**

Install all the required npm packages.

```bash
npm install
```

**3. Create and Configure the `.env` File**

This is the most important step for configuration. Create a file named `.env` in the root of the project and fill it with your specific credentials. Use the `.env.example` file as a template.

```ini
# .env

# === Server & Session ===
PORT=3000
SESSION_SECRET=replace_this_with_a_long_random_and_secret_string

# === Pterodactyl API Settings ===
# Your Pterodactyl Panel URL (NO trailing slash)
PTERO_URL=https://panel.yourdomain.com
# Your Pterodactyl Application API Key
# IMPORTANT: This key needs Read & Write permissions for USERS and SERVERS.
PTERO_API_KEY=ptla_xxxxxxxxxxxxxxxxxxxxxxxxxxxx

# === Google OAuth Credentials ===
GOOGLE_CLIENT_ID=YOUR_GOOGLE_CLIENT_ID.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=YOUR_GOOGLE_CLIENT_SECRET

# === Discord OAuth Credentials ===
DISCORD_CLIENT_ID=YOUR_DISCORD_CLIENT_ID
DISCORD_CLIENT_SECRET=YOUR_DISCORD_CLIENT_SECRET

# === Database ===
# The path where the SQLite database file will be stored.
DATABASE_PATH=./database.sqlite
```

**Obtaining API Keys:**
-   **Pterodactyl:** Go to your Pterodactyl Panel -> API Credentials -> Create New Application API Key.
-   **Google & Discord:** Follow the setup guides in the project's documentation (or add links to your own guides). You must configure the **authorized redirect URIs** correctly:
    -   Google: `http://localhost:3000/auth/google/callback`
    -   Discord: `http://localhost:3000/auth/discord/callback`

**4. Start the Application**

Run the following command to start the server:

```bash
node index.js
```

You should see a confirmation message in your console:
`✅ Server is running in development mode on http://localhost:3000`

Your dashboard is now live! Open your browser and navigate to `http://localhost:3000`.

---

## 👑 Becoming an Admin

The **very first user** to register on the dashboard is automatically promoted to an administrator.

1.  Start the server with an empty database (delete `database.sqlite` if it exists).
2.  Go to the registration page.
3.  Create your account.
4.  Log in, and you will see the "Admin" links in the navigation bar.

