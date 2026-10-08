# Todo App (React Context + localStorage)

A simple, clean todo application built with **React 19**, **Context API**, and **Tailwind CSS v4**, bundled with **Vite**. Todos are stored in the browser's `localStorage`, so your list is still there after a refresh or restart.

## Features

- Add, edit, and delete todos
- Mark todos as complete / incomplete
- Global state shared via the React **Context API** (no prop drilling)
- Persistent data using **localStorage**
- Responsive UI styled with **Tailwind CSS v4**
- Fast dev server and builds with **Vite**

## Tech Stack

| Tool | Purpose |
| --- | --- |
| React 19 | UI library |
| React Context API | Global state management |
| Tailwind CSS 4 (`@tailwindcss/vite`) | Styling |
| Vite 8 | Dev server and bundler |
| ESLint 10 (+ react-hooks, react-refresh plugins) | Linting |
| localStorage | Data persistence |

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 20.19+ (or the latest LTS)
- npm (comes with Node.js)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Sayan161005/Todo-App.git

# 2. Move into the project folder
cd Todo-App

# 3. Install dependencies
npm install

# 4. Start the dev server
npm run dev
```

Then open the URL shown in the terminal (usually `http://localhost:5173`).

## Available Scripts

| Command | What it does |
| --- | --- |
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Creates an optimized production build in `dist/` |
| `npm run preview` | Serves the production build locally |
| `npm run lint` | Runs ESLint on the project |

## File Structure

```
Todo-App/
├── node_modules/            # Installed dependencies (git-ignored)
├── public/                  # Static assets
├── src/
│   ├── components/          # UI components
│   │   ├── index.js         # Re-exports components
│   │   ├── TodoForm.jsx     # Input form to add a todo
│   │   └── TodoItem.jsx     # Single todo (edit / toggle / delete)
│   ├── contexts/            # Global todo state
│   │   ├── index.js         # Re-exports context, provider and hook
│   │   └── TodoContext.js   # Todo context, provider and useTodo hook
│   ├── App.css              # App styles
│   ├── App.jsx              # Root component, provider, localStorage sync
│   ├── index.css            # Tailwind import and global styles
│   └── main.jsx             # React entry point
├── .gitignore               # Files ignored by Git
├── eslint.config.js         # ESLint flat config
├── index.html               # HTML entry point
├── package-lock.json        # Locked dependency versions
├── package.json             # Scripts and dependencies
├── README.md                # You are here
└── vite.config.js           # Vite config (React + Tailwind plugins)
```

## How It Works

1. **Context** – `contexts/TodoContext.js` holds the `todos` array and the functions `addTodo`, `updateTodo`, `deleteTodo`, and `toggleComplete`, exposed through a `useTodo` custom hook.
2. **Provider** – `App.jsx` wraps the UI in `TodoProvider` and owns the actual state.
3. **Persistence** – on first load, todos are read from `localStorage`; whenever the list changes, it is written back.
4. **UI** – `TodoForm` adds new todos and each `TodoItem` reads from context to edit, toggle, or delete itself.

## Build for Production

```bash
npm run build
```

The output is generated in the `dist/` folder and can be deployed to Netlify, Vercel, GitHub Pages, or any static host.

## Contributing

Suggestions and pull requests are welcome. Fork the repo, create a branch, and open a PR.

## 📬 Contact

Made by **SAYAN SAHA** · [GitHub](https://github.com/Sayan161005) 

---

⭐ If you found this project helpful, consider giving it a star!
