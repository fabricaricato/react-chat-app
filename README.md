<div align="center">

# WhatsApp Web Clone

**Real-time messaging application inspired by WhatsApp Web**

Built with **React 19** · **Vite 7** · **React Router DOM 7**

[![React](https://img.shields.io/badge/React-19.1-61DAFB?logo=react&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.1-646CFF?logo=vite&logoColor=white)](https://vite.dev/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-000000?logo=vercel&logoColor=white)](https://vercel.com/)

</div>

---

## 📖 Description

This project is a **simplified WhatsApp Web clone**, developed as the final project for the first _Front-End Developer_ module at **UTN**.

The application allows users to log in, view available contacts, and chat through a clean and intuitive interface that replicates the WhatsApp Web experience. It implements reusable components, global state management with Context API, a theme system (light/dark mode), multi-language support (Spanish/English), and navigation protected by routes.

---

## ✨ Features

| Feature                         | Description                                                 |
| ------------------------------- | ----------------------------------------------------------- |
| 💬 **Real-time chat**           | Sending and displaying messages with timestamps             |
| 🔐 **Protected login**          | Simulated authentication with password and protected routes |
| 🌙 **Light / dark mode**        | Persistent theme switching via `localStorage`               |
| 🌐 **Multi-language (ES / EN)** | Full persistent language switching via `localStorage`       |
| 🔍 **Contact search**           | Real-time user filtering from the sidebar                   |
| 🖼️ **Image gallery**            | Gallery with modal view for image previewing                |
| ❓ **Help center**              | Informational page with app documentation                   |
| 📱 **Responsive design**        | Interface adaptable to mobile and desktop devices           |
| 👁️ **Show/hide password**       | Visibility toggle on the password field                     |

---

## 🛠️ Tech Stack

| Technology                                                                           | Usage                                |
| ------------------------------------------------------------------------------------ | ------------------------------------ |
| [React 19](https://react.dev/)                                                       | Main UI library                      |
| [Vite 7](https://vite.dev/)                                                          | Bundler and development server       |
| [React Router DOM 7](https://reactrouter.com/)                                       | SPA routing and navigation           |
| [Context API](https://react.dev/reference/react/createContext)                       | Global state (chat, theme, language) |
| [ESLint 9](https://eslint.org/)                                                      | Linting and code quality             |
| [Font Awesome 6](https://fontawesome.com/)                                           | Iconography                          |
| [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) | Client-side data persistence         |
| [Vercel](https://vercel.com/)                                                        | Production deployment                |

---

## 📂 Project Structure

```
react-chat-app/
├── public/                         # Static public files
│
├── src/                            # Main source code
│   ├── assets/                     # Static resources
│   │   └── images/
│   │       ├── avatar.jpeg         # Default avatar
│   │       └── logo.png            # Application logo
│   │
│   ├── components/                 # Reusable components
│   │   ├── Chat.jsx                # Main chat interface
│   │   ├── ProtectedRoute.jsx      # HOC for protected routes
│   │   └── Sidebar.jsx             # Sidebar with contacts
│   │
│   ├── context/                    # Context API Providers
│   │   ├── ChatContext.jsx         # Global state: users and messages
│   │   ├── LanguageContext.jsx     # Global state: language (es/en)
│   │   └── ThemeContext.jsx        # Global state: theme (light/dark)
│   │
│   ├── router/                     # Route configuration
│   │   └── RouterApp.jsx           # App route definitions
│   │
│   ├── views/                      # Pages / views
│   │   ├── Gallery.jsx             # Image gallery with modal
│   │   ├── Help.jsx                # Help center
│   │   ├── Login.jsx               # Login page
│   │   ├── Messages.jsx            # Main messages page
│   │   └── NotFound.jsx            # 404 page
│   │
│   ├── index.css                   # Global styles
│   ├── main.jsx                    # React entry point
│   └── translations.js             # Translations (ES / EN)
│
├── .gitignore
├── eslint.config.js                # ESLint configuration
├── index.html                      # Base HTML template
├── package.json                    # Dependencies and scripts
├── vercel.json                     # Deployment configuration (Vercel)
├── vite.config.js                  # Vite configuration
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) **v18+**
- [npm](https://www.npmjs.com/) **v9+** (included with Node.js)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/tu-usuario/react-chat-app.git

# 2. Navigate to the project directory
cd react-chat-app

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
```

The application will be available at `http://localhost:5173`.

### Available Scripts

| Command           | Description                                   |
| ----------------- | --------------------------------------------- |
| `npm run dev`     | Starts the development server with hot reload |
| `npm run build`   | Generates the production build in `/dist`     |
| `npm run preview` | Previews the production build                 |
| `npm run lint`    | Runs ESLint to check code quality             |

---

## 🗺️ Application Routes

| Route      | View                      | Access       |
| ---------- | ------------------------- | ------------ |
| `/`        | Login                     | 🔓 Public    |
| `/chat`    | Messages (Chat + Sidebar) | 🔒 Protected |
| `/help`    | Help center               | 🔓 Public    |
| `/gallery` | Image gallery             | 🔓 Public    |
| `*`        | 404 Page                  | 🔓 Public    |

> **Note:** The access password is `chatui`.

---

## 🧩 Context Architecture

The application uses three nested providers that wrap the entire app:

```
<ThemeProvider>          →  Manages the theme (light/dark)
  <ChatProvider>         →  Manages users, messages, and selection
    <LanguageProvider>   →  Manages the language (es/en)
      <RouterApp />      →  Application routes
    </LanguageProvider>
  </ChatProvider>
</ThemeProvider>
```

Each context exposes a custom hook to access its state:

- `useTheme()` — `{ theme, toggleTheme, setTheme }`
- `useChat()` — `{ users, setUsers, selectedUser, setSelectedUser }`
- `useLanguage()` — `{ language, setLanguage }`

---

## ☁️ Deployment

The project is configured for deployment on **Vercel** with SPA route rewrites:

```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

To deploy:

```bash
# Install Vercel CLI (if not already installed)
npm i -g vercel

# Deploy
vercel
```

---

## 🔮 Future Improvements

- [ ] Integration with a real database (Firebase / Supabase)
- [ ] Real authentication with JWT or OAuth
- [ ] Sending images, audio, and files
- [ ] Real-time notifications with WebSockets
- [ ] "Typing..." indicator
- [ ] Message read receipts (blue double check)

---

## 🧑‍💻 Author

**Fabrizio Caricato**

Project developed as the final project for the first _Front-End Developer_ module at **UTN**.