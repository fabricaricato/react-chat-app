<div align="center">

# WhatsApp Web Clone

**Aplicación de mensajería en tiempo real inspirada en WhatsApp Web**

Desarrollada con **React 19** · **Vite 7** · **React Router DOM 7**

[![React](https://img.shields.io/badge/React-19.1-61DAFB?logo=react&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.1-646CFF?logo=vite&logoColor=white)](https://vite.dev/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-000000?logo=vercel&logoColor=white)](https://vercel.com/)

</div>

---

## 📖 Descripción

Este proyecto es un **clon simplificado de WhatsApp Web**, desarrollado como trabajo final del primer módulo de _Front-End Developer_ en la **UTN**.

La aplicación permite a los usuarios iniciar sesión, ver contactos disponibles, y chatear en una interfaz limpia e intuitiva que replica la experiencia de WhatsApp Web. Implementa componentes reutilizables, gestión de estado global con Context API, un sistema de temas (modo claro/oscuro), soporte multilenguaje (español/inglés) y navegación protegida por rutas.

---

## ✨ Funcionalidades

| Funcionalidad                     | Descripción                                                |
| --------------------------------- | ---------------------------------------------------------- |
| 💬 **Chat en tiempo real**        | Envío y visualización de mensajes con marca de tiempo      |
| 🔐 **Login protegido**            | Autenticación simulada con contraseña y rutas protegidas   |
| 🌙 **Modo claro / oscuro**        | Cambio de tema persistente vía `localStorage`              |
| 🌐 **Multilenguaje (ES / EN)**    | Cambio de idioma completo persistente vía `localStorage`   |
| 🔍 **Búsqueda de contactos**      | Filtrado de usuarios en tiempo real desde la barra lateral |
| 🖼️ **Galería de imágenes**        | Galería con vista modal para previsualizar imágenes        |
| ❓ **Centro de ayuda**            | Página informativa con documentación de la app             |
| 📱 **Diseño responsive**          | Interfaz adaptable a dispositivos móviles y escritorio     |
| 👁️ **Mostrar/ocultar contraseña** | Toggle de visibilidad en el campo de contraseña            |

---

## �️ Stack tecnológico

| Tecnología                                                                        | Uso                                |
| --------------------------------------------------------------------------------- | ---------------------------------- |
| [React 19](https://react.dev/)                                                    | Biblioteca principal para la UI    |
| [Vite 7](https://vite.dev/)                                                       | Bundler y servidor de desarrollo   |
| [React Router DOM 7](https://reactrouter.com/)                                    | Enrutamiento y navegación SPA      |
| [Context API](https://react.dev/reference/react/createContext)                    | Estado global (chat, tema, idioma) |
| [ESLint 9](https://eslint.org/)                                                   | Linting y calidad de código        |
| [Font Awesome 6](https://fontawesome.com/)                                        | Iconografía                        |
| [localStorage](https://developer.mozilla.org/es/docs/Web/API/Window/localStorage) | Persistencia de datos del cliente  |
| [Vercel](https://vercel.com/)                                                     | Despliegue en producción           |

---

## 📂 Estructura del proyecto

```
react-chat-app/
├── public/                         # Archivos públicos estáticos
│
├── src/                            # Código fuente principal
│   ├── assets/                     # Recursos estáticos
│   │   └── images/
│   │       ├── avatar.jpeg         # Avatar por defecto
│   │       └── logo.png            # Logo de la aplicación
│   │
│   ├── components/                 # Componentes reutilizables
│   │   ├── Chat.jsx                # Interfaz principal del chat
│   │   ├── ProtectedRoute.jsx      # HOC para rutas protegidas
│   │   └── Sidebar.jsx             # Barra lateral con contactos
│   │
│   ├── context/                    # Providers de Context API
│   │   ├── ChatContext.jsx         # Estado global: usuarios y mensajes
│   │   ├── LanguageContext.jsx     # Estado global: idioma (es/en)
│   │   └── ThemeContext.jsx        # Estado global: tema (light/dark)
│   │
│   ├── router/                     # Configuración de rutas
│   │   └── RouterApp.jsx           # Definición de rutas de la app
│   │
│   ├── views/                      # Páginas / vistas
│   │   ├── Gallery.jsx             # Galería de imágenes con modal
│   │   ├── Help.jsx                # Centro de ayuda
│   │   ├── Login.jsx               # Inicio de sesión
│   │   ├── Messages.jsx            # Página principal de mensajes
│   │   └── NotFound.jsx            # Página 404
│   │
│   ├── index.css                   # Estilos globales
│   ├── main.jsx                    # Punto de entrada de React
│   └── translations.js             # Traducciones (ES / EN)
│
├── .gitignore
├── eslint.config.js                # Configuración de ESLint
├── index.html                      # Plantilla HTML base
├── package.json                    # Dependencias y scripts
├── vercel.json                     # Configuración de despliegue (Vercel)
├── vite.config.js                  # Configuración de Vite
└── README.md
```

---

## 🚀 Primeros pasos

### Prerrequisitos

- [Node.js](https://nodejs.org/) **v18+**
- [npm](https://www.npmjs.com/) **v9+** (incluido con Node.js)

### Instalación

```bash
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/react-chat-app.git

# 2. Entrar al directorio del proyecto
cd react-chat-app

# 3. Instalar dependencias
npm install

# 4. Iniciar el servidor de desarrollo
npm run dev
```

La aplicación estará disponible en `http://localhost:5173`.

### Scripts disponibles

| Comando           | Descripción                                         |
| ----------------- | --------------------------------------------------- |
| `npm run dev`     | Inicia el servidor de desarrollo con hot reload     |
| `npm run build`   | Genera el build de producción en `/dist`            |
| `npm run preview` | Previsualiza el build de producción                 |
| `npm run lint`    | Ejecuta ESLint para verificar la calidad del código |

---

## 🗺️ Rutas de la aplicación

| Ruta       | Vista                     | Acceso      |
| ---------- | ------------------------- | ----------- |
| `/`        | Login                     | 🔓 Pública  |
| `/chat`    | Mensajes (Chat + Sidebar) | � Protegida |
| `/help`    | Centro de ayuda           | 🔓 Pública  |
| `/gallery` | Galería de imágenes       | 🔓 Pública  |
| `*`        | Página 404                | 🔓 Pública  |

> **Nota:** La contraseña de acceso es `chatui`.

---

## 🧩 Arquitectura de contextos

La aplicación utiliza tres providers anidados que envuelven toda la app:

```
<ThemeProvider>          →  Gestiona el tema (light/dark)
  <ChatProvider>         →  Gestiona usuarios, mensajes y selección
    <LanguageProvider>   →  Gestiona el idioma (es/en)
      <RouterApp />      →  Rutas de la aplicación
    </LanguageProvider>
  </ChatProvider>
</ThemeProvider>
```

Cada contexto expone un hook personalizado para acceder a su estado:

- `useTheme()` — `{ theme, toggleTheme, setTheme }`
- `useChat()` — `{ users, setUsers, selectedUser, setSelectedUser }`
- `useLanguage()` — `{ language, setLanguage }`

---

## ☁️ Despliegue

El proyecto está configurado para desplegarse en **Vercel** con reescritura de rutas SPA:

```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

Para desplegar:

```bash
# Instalar Vercel CLI (si no está instalado)
npm i -g vercel

# Desplegar
vercel
```

---

## 🔮 Mejoras futuras

- [ ] Integración con base de datos real (Firebase / Supabase)
- [ ] Autenticación real con JWT o OAuth
- [ ] Envío de imágenes, audios y archivos
- [ ] Notificaciones en tiempo real con WebSockets
- [ ] Indicador de "escribiendo..."
- [ ] Lectura de mensajes (doble check azul)

---

## 🧑‍💻 Autor

**Fabrizio Caricato**

Proyecto desarrollado como trabajo final del primer módulo de _Front-End Developer_ en la **UTN**.