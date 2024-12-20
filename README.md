# Cashbook - Open Source Accounting Software

Cashbook is a simple yet powerful open-source accounting application designed to help individuals, small businesses, and organizations manage their financial transactions effortlessly. Built using modern technologies like **Node.js**, **Vue.js**, and **Vuetify**, Cashbook aims to provide an intuitive and accessible solution for basic accounting needs.

Currently hosted on [hcashbook.com](https://hcashbook.com), Cashbook is evolving into a free-to-use platform through community-driven contributions.

---

## 🚀 Key Features

- **Transaction Management**: Record and categorize income and expenses with ease.
- **Multi-Business Support**: Manage multiple businesses under a single account.
- **Google Login Integration**: Simplified authentication process using Google OAuth.
- **Interactive Dashboards**: Visualize financial data through charts and summaries.
- **Seamless User Experience**: Responsive and user-friendly interface powered by Vuetify.

---

## 🌟 Vision

Cashbook aspires to become a completely free and community-driven basic accounting software for everyone. With contributions from developers worldwide, it will evolve to include more features while remaining accessible to all.

---

## 💡 Why Open Source?

We believe in the power of open-source collaboration. By making Cashbook open source, we aim to:

- Foster innovation and improvements from a global community of developers.
- Provide a transparent and adaptable solution for accounting needs.
- Make essential financial tools available to everyone, regardless of budget.

---

## 🛠️ How You Can Contribute

Whether you're a developer, designer, or accountant, your contributions can make a difference! Help us improve Cashbook by:

- Adding new features or fixing bugs.
- Improving documentation or UI/UX design.
- Sharing feedback or testing the application.

Join us in building a free, reliable, and open accounting tool for everyone. Let's make financial management simple and accessible for all!

---

## 🧰 Technologies Used

- **Backend**: Node.js with Express.js
- **Frontend**: Vue.js with Vuetify
- **OAuth**: Google Authentication

---

## ⚙️ Installation

### Prerequisites

1. Install **Node.js** and **npm** (comes with Node.js).
2. Set up your database (if required for admin seeding).

---

### Backend Installation

1. Navigate to the backend directory:

    ```bash
    cd backend
    ```

2. Install dependencies:

    ```bash
    npm install
    ```

3. Configure the application (see [Configuration](#configuration)).

4. Start the server:

    ```bash
    npm start
    ```

    By default, the server will run on `http://localhost:4000`.

---

### Frontend Setup

1. Navigate to the frontend directory:

    ```bash
    cd frontend
    ```

2. Install dependencies:

    ```bash
    npm install
    ```

3. Update the `global_config.js` file in the `frontend/config` directory with the appropriate API URLs.

4. Start the Vue application:

    ```bash
    npm run serve
    ```

    By default, the frontend will run on `http://localhost:3001`.

---

## 🔧 Configuration

### Backend

Update the `global_config.js` file in the `backend/config` directory:

```javascript
const GlobalVariable = {
    "SERVER_API_URL": "http://localhost:4000/api",
    "SERVER_BASE_URL": "http://localhost:4000",
    "CLIENT_BASE_URL": "http://localhost:3001"
};

module.exports = GlobalVariable;


For Google Login, update the following in backend/controllers/auth/auth.js:

const googleAuthData = {
    code: code, // Ensure 'code' parameter is included
    client_id: 'YOUR_CLIENT_ID',
    client_secret: 'YOUR_CLIENT_SECRET',
    redirect_uri: `${CLIENT_BASE_URL}/auth/callback`,
    grant_type: 'authorization_code'
};

🌱 Database Seeding
To seed the admin user, run the admin_seeder.js file:
node seeder/admin_seeder.js

🔐 Google Login Setup
In frontend/views/auth/login.vue, update the login method:

async login() {
    try {
        this.$router.push("/processing");
        window.location.href = `https://accounts.google.com/o/oauth2/v2/auth?client_id=YOUR_CLIENT_ID.apps.googleusercontent.com&redirect_uri=${globalConfig.CLIENT_BASE_URL}/auth/callback&response_type=code&scope=email%20profile%20openid`;
    } catch (error) {
        this.snackbarFunc(false, "Oops! Something went wrong!");
    }
}

In frontend/main.js, configure the Vue Google Login plugin:

app.use(vue3GoogleLogin, {
    clientId: 'YOUR_CLIENT_ID'
});


📦 Deployment
Build the Vue frontend:

npm run build
Deploy the built files to your hosting platform (e.g., cPanel, AWS, etc.).

Ensure the Node.js backend server is running on your production server.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

⚠️ Notes
Keep sensitive data like the Google Client ID and Secret private.
Use .env files for better security in a production environment.

💬 Contact
For any issue or feedback, you can create an issue or contact me at hemantajungkarki@gmail.com.

Tags
#opensource #MIT #freetouse #freesoftware
