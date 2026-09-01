# Redux Patterns - React State Management Examples

A comprehensive repository showcasing two different approaches to state management in React using Redux and Redux Toolkit. This project demonstrates the evolution from traditional Redux to modern Redux Toolkit patterns.

## 📋 Table of Contents

- [Overview](#overview)
- [Projects](#projects)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Features](#features)
- [Key Differences](#key-differences)
- [Dependencies](#dependencies)
- [Scripts](#scripts)
- [Learning Outcomes](#learning-outcomes)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This repository contains two complete React applications demonstrating different state management patterns:

1. **react_redux** - Traditional Redux pattern using Create React App
2. **react-rtk** - Modern Redux Toolkit pattern using Vite

Both applications manage the same business logic (Burger, Pizza, and Products) but with different architectural approaches, making it an excellent resource for learning and comparing Redux implementations.

## 📁 Projects

### 1. React Redux (Traditional Redux)
**Location:** `./react_redux/`

A classic Redux implementation built with Create React App, demonstrating:
- Manual action creators
- Separate action types and reducers
- Redux middleware integration (Redux Thunk, Redux Logger)
- Traditional Redux DevTools setup

**Tech Stack:**
- React 19.1.0
- Redux 5.0.1
- React-Redux 9.2.0
- Redux Thunk 3.1.0
- Redux Logger 3.0.6

### 2. React Redux Toolkit (Modern Redux)
**Location:** `./react-rtk/`

A modern Redux implementation using Redux Toolkit with Vite, featuring:
- Simplified reducer logic with Immer integration
- Auto-generated action creators via createSlice
- Redux Thunk pre-configured
- Enhanced Redux DevTools debugging
- Vite for faster development

**Tech Stack:**
- React 19.1.0
- Redux Toolkit 2.8.2
- React-Redux 9.2.0
- Vite 6.3.5
- ESLint 9.30.1

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** (v6 or higher) or **yarn**
- **Git**

Check your versions:
```bash
node --version
npm --version
git --version
```

## 🚀 Installation

### Clone the Repository
```bash
git clone https://github.com/Manzar0911/redux-patterns.git
cd redux-patterns
```

### Install Dependencies for Both Projects

#### For React Redux (Traditional)
```bash
cd react_redux
npm install
```

#### For React Redux Toolkit (Modern)
```bash
cd ../react-rtk
npm install
```

## 📁 Project Structure

```
redux-patterns/
├── react_redux/                    # Traditional Redux Implementation
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── BurgerBox.js
│   │   │   ├── CustomerChoice.js
│   │   │   ├── HooksContainer.js
│   │   │   ├── PizzaBox.js
│   │   │   ├── ProductsContainer.js
│   │   │   └── redux/
│   │   │       ├── index.js
│   │   │       ├── rootReducer.js
│   │   │       ├── store.js
│   │   │       ├── burger/
│   │   │       │   ├── BurgerActions.js
│   │   │       │   ├── BurgerReducers.js
│   │   │       │   └── BurgerTypes.js
│   │   │       ├── pizza/
│   │   │       │   ├── PizzaActions.js
│   │   │       │   ├── PizzaReducers.js
│   │   │       │   └── PizzaTypes.js
│   │   │       └── products/
│   │   │           ├── ProductsActions.js
│   │   │           ├── ProductsReducers.js
│   │   │           └── ProductsTypes.js
│   │   ├── App.js
│   │   ├── App.css
│   │   └── index.js
│   ├── package.json
│   └── README.md
│
├── react-rtk/                      # Redux Toolkit Implementation
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   │   └── store.js
│   │   ├── features/
│   │   │   ├── burger/
│   │   │   │   ├── burgerSlice.js
│   │   │   │   └── BurgerView.jsx
│   │   │   ├── pizza/
│   │   │   │   ├── pizzaSlice.js
│   │   │   │   └── PizzaView.jsx
│   │   │   └── products/
│   │   │       ├── productSlice.js
│   │   │       └── ProductView.jsx
│   │   ├── App.jsx
│   │   ├── App.css
│   │   ├── index.css
│   │   └── main.jsx
│   ├── package.json
│   ├── vite.config.js
│   ├── eslint.config.js
│   └── README.md
│
├── .gitignore
└── README.md
```

## 🎮 Getting Started

### Running React Redux (Traditional)

```bash
cd react_redux
npm start
```

- Opens at: `http://localhost:3000`
- Auto-reloads on changes
- Redux Logger logs actions to console
- Redux DevTools available in browser extension

### Running React Redux Toolkit (Modern)

```bash
cd react-rtk
npm run dev
```

- Opens at: `http://localhost:5173` (or next available port)
- Vite provides fast HMR (Hot Module Replacement)
- Redux DevTools available in browser extension

## ✨ Features

### Shared Features Across Both Projects

#### 🍔 Burger Management
- Add burgers to cart
- Remove burgers from cart
- Display burger list and count

#### 🍕 Pizza Management
- Browse available pizzas
- Add pizzas to cart
- Update pizza quantity
- Remove pizzas from cart

#### 📦 Products Management
- Fetch products from API (Axios)
- Display products with details
- Manage product state
- Loading and error states

#### 🪝 React Hooks Integration
- Custom hooks for state management
- useSelector for accessing state
- useDispatch for dispatching actions
- Hook-based component architecture

## 🔄 Key Differences

### Redux vs Redux Toolkit

| Feature | Redux | Redux Toolkit |
|---------|-------|---------------|
| **Action Types** | Separate constants file | Auto-generated |
| **Action Creators** | Manual creation | Auto-generated via createSlice |
| **Reducers** | Pure functions (manual immutability) | Simplified with Immer integration |
| **Boilerplate** | High | Minimal |
| **Learning Curve** | Steep | Gentle |
| **DevTools Setup** | Manual configuration | Pre-configured |
| **Middleware** | Manual setup | Pre-configured (Thunk) |
| **File Organization** | Feature-based or type-based | Feature-based slices |
| **Bundle Size** | Smaller | Slightly larger (includes utilities) |

### Code Example Comparison

**Traditional Redux (react_redux):**
```javascript
// BurgerTypes.js
export const ADD_BURGER = 'ADD_BURGER';
export const REMOVE_BURGER = 'REMOVE_BURGER';

// BurgerActions.js
export const addBurger = (burger) => ({
  type: ADD_BURGER,
  payload: burger
});

// BurgerReducers.js
const initialState = { items: [] };
export const burgerReducer = (state = initialState, action) => {
  switch(action.type) {
    case ADD_BURGER:
      return { ...state, items: [...state.items, action.payload] };
    default:
      return state;
  }
};
```

**Redux Toolkit (react-rtk):**
```javascript
// burgerSlice.js
import { createSlice } from '@reduxjs/toolkit';

const burgerSlice = createSlice({
  name: 'burger',
  initialState: { items: [] },
  reducers: {
    addBurger: (state, action) => {
      state.items.push(action.payload);
    }
  }
});

export const { addBurger } = burgerSlice.actions;
export default burgerSlice.reducer;
```

## 📚 Dependencies

### Common Dependencies
- **react** (^19.1.0) - UI library
- **react-dom** (^19.1.0) - React DOM rendering
- **axios** (^1.10.0) - HTTP client

### React Redux Specific
- **redux** (^5.0.1) - State management
- **react-redux** (^9.2.0) - React bindings for Redux
- **redux-thunk** (^3.1.0) - Async middleware
- **redux-logger** (^3.0.6) - Logging middleware
- **redux-devtools-extension** (^2.13.9) - DevTools integration

### React RTK Specific
- **@reduxjs/toolkit** (^2.8.2) - Modern Redux tools
- **react-redux** (^9.2.0) - React bindings
- **vite** (^6.3.5) - Build tool
- **eslint** (^9.30.1) - Linting

## 🔧 Scripts

### React Redux
```bash
npm start          # Start development server
npm build          # Build for production
npm test           # Run tests
npm eject          # Eject from Create React App (irreversible)
```

### React Redux Toolkit
```bash
npm run dev        # Start Vite dev server
npm run build      # Build for production
npm run lint       # Run ESLint
npm run preview    # Preview production build
```

## 🎓 Learning Outcomes

After working through this repository, you'll understand:

1. **Redux Fundamentals**
   - Store, actions, reducers, and dispatch
   - Unidirectional data flow
   - Action creators and types
   - Middleware concepts

2. **Redux Toolkit Benefits**
   - Simplified reducer logic
   - Auto-generated action creators
   - Immer integration for immutable updates
   - Enhanced DevTools experience

3. **React-Redux Integration**
   - Provider and store setup
   - useSelector hook for state access
   - useDispatch hook for actions
   - Performance optimization

4. **Async Operations**
   - Redux Thunk for async actions
   - Loading states and error handling
   - Axios integration for API calls

5. **Best Practices**
   - Folder structure organization
   - Action naming conventions
   - Reducer logic separation
   - Component-Redux connection patterns

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Support

For questions or issues:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the official Redux documentation: https://redux.js.org/
- Redux Toolkit documentation: https://redux-toolkit.js.org/

## 🔗 Useful Resources

- [Redux Official Documentation](https://redux.js.org/)
- [Redux Toolkit Documentation](https://redux-toolkit.js.org/)
- [React Redux Hooks](https://react-redux.js.org/api/hooks)
- [Redux DevTools Extension](https://github.com/reduxjs/redux-devtools-extension)
- [Redux Style Guide](https://redux.js.org/style-guide/style-guide)

## 📈 Next Steps

1. **Explore both implementations** - Run both projects and compare their structure
2. **Study the Redux flow** - Understand how actions flow through reducers to state
3. **Experiment** - Modify components and actions to learn by doing
4. **Migrate** - Try converting react_redux to use Redux Toolkit patterns
5. **Extend** - Add new features like filtering, sorting, or persistence

---

**Made with ❤️ by [Manzar0911](https://github.com/Manzar0911)**

Happy learning! 🚀
