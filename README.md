# AlgoRoot Global Website

A real-time website for AlgoRoot Global, featuring user authentication (sign-in, sign-out, password recovery) and a dashboard displaying user details. The site includes pages for Navigation, About, Services, Products, Partner, Career, Contact, and Portfolio, with a profile icon showing logged-in user information.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Authentication Flow](#authentication-flow)
- [Dashboard Functionality](#dashboard-functionality)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

## Project Overview
This project is a dynamic, user-friendly website built for AlgoRoot Global. It provides secure user authentication and a responsive dashboard to view user details. The site is designed with a modern navigation bar, multiple informational pages, and a portfolio section. The application is built using Next.js, Firebase for authentication, and CSS modules for styling.

## Features
- **User Authentication**:
  - Sign-in and sign-up with email and password.
  - Password recovery via email.
  - Sign-out and account deletion options.
- **Dashboard**:
  - Displays user details fetched from a mock API (`jsonplaceholder.typicode.com/users`).
  - Search functionality by ID, name, email, or username.
  - Pagination for efficient data display.
  - Responsive sidebar with navigation links.
- **Navigation Bar**:
  - Displays company logo and user profile (if logged in).
  - Profile includes email, logout, and delete account options.
  - Shows sign-in/sign-up buttons when not logged in.
- **Pages**:
  - About, Services, Products, Partner, Career, Contact, and Portfolio pages linked to external URLs.
- **Responsive Design**:
  - Mobile-friendly sidebar and hamburger menu.
  - Fixed copyright footer.

## Technologies Used
- **Frontend**: Next.js, React
- **Authentication**: Firebase Authentication
- **Styling**: CSS Modules
- **Data Fetching**: Fetch API (mock data from `jsonplaceholder.typicode.com`)
- **Context API**: React Context for managing authentication state
- **Routing**: Next.js App Router
- **Deployment**: Vercel (recommended)

## Installation
To run the project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/algoroot-global.git
   cd algoroot-global
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up Firebase**:
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/).
   - Enable Email/Password authentication in the Authentication section.
   - Copy your Firebase configuration and add it to `/src/app/firebase/firebase.js`.

   Example `firebase.js`:
   ```javascript
   import { initializeApp } from "firebase/app";
   import { getAuth } from "firebase/auth";

   const firebaseConfig = {
     apiKey: "YOUR_API_KEY",
     authDomain: "YOUR_AUTH_DOMAIN",
     projectId: "YOUR_PROJECT_ID",
     storageBucket: "YOUR_STORAGE_BUCKET",
     messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
     appId: "YOUR_APP_ID",
   };

   const app = initializeApp(firebaseConfig);
   export const auth = getAuth(app);
   ```

4. **Run the development server**:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

## Usage
- **Sign Up**: Navigate to `/SignUp`, enter email, password, and confirm password to create an account.
- **Sign In**: Go to `/SignIn`, enter credentials to log in.
- **Password Recovery**: Use `/ForgotPassword` to receive a password reset email.
- **Dashboard**: After logging in, view user details, search, and paginate through data.
- **Navigation**: Use the sidebar or navbar to access About, Services, Products, Partner, Career, Contact, or Portfolio pages.
- **Profile**: Click the profile icon in the navbar to view user info, log out, or delete the account.

## File Structure
```
src/
├── app/
│   ├── contexts/
│   │   └── authContext.js        # Authentication context for managing user state
│   ├── firebase/
│   │   ├── firebase.js          # Firebase configuration and initialization
│   │   └── Auth.js              # Firebase authentication utilities
│   ├── ForgotPassword/
│   │   ├── page.js              # Password recovery page
│   │   └── fp.module.css        # Styles for ForgotPassword page
│   ├── SignIn/
│   │   ├── page.js              # Sign-in page
│   │   └── signin.module.css    # Styles for SignIn page
│   ├── SignUp/
│   │   ├── page.js              # Sign-up page
│   │   └── signup.module.css    # Styles for SignUp page
│   ├── Navbar.js                # Navigation bar component
│   ├── Navbar.module.css        # Styles for Navbar
│   ├── page.js                  # Dashboard page with user details
│   ├── page.module.css          # Styles for Dashboard
│   ├── copyright.js             # Fixed footer with copyright info
│   ├── layout.js                # Root layout with Navbar, AuthProvider, and Copyright
│   └── globals.css              # Global styles
```

## Authentication Flow
- **AuthContext** (`authContext.js`):
  - Uses Firebase's `onAuthStateChanged` to monitor user login state.
  - Provides `userLoggedIn`, `isEmailUser`, and `currentUser` to components via React Context.
  - Ensures loading state prevents rendering until authentication is verified.
- **SignIn/SignUp**:
  - Prompts users for email and password.
  - Validates input and communicates with Firebase Authentication.
- **ForgotPassword**:
  - Sends a password reset email via Firebase.
- **Navbar**:
  - Conditionally renders profile or sign-in/sign-up buttons based on `userLoggedIn`.

## Dashboard Functionality
- **Data Fetching**:
  - Fetches mock user data from `jsonplaceholder.typicode.com/users`.
  - Formats data into `id`, `name`, `email`, and `username`.
- **Search**:
  - Filters data by `id`, `name`, `email`, or `username` using a case-insensitive search.
- **Pagination**:
  - Displays 5 rows per page with Previous/Next buttons.
- **Sidebar**:
  - Toggles via a hamburger menu on mobile.
  - Links to external pages (About, Services, etc.).

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

Please ensure your code follows the project's coding style and includes tests where applicable.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For inquiries, reach out to:
- **Developer**: Rishik Reddy
- **Portfolio**: [rishik.tech](https://rishik.tech)
- **Email**: [your-email@example.com](mailto:your-email@example.com)

## Acknowledgements
- **Firebase**: For secure authentication services.
- **Next.js**: For a powerful React framework.
- **JSONPlaceholder**: For providing mock API data.
- **Algoroot Global**: For project inspiration and external page content.