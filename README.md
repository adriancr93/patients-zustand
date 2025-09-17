
# 📝 React Form Libraries Guide

## 📋 When to Use a Form Library in React?

If your project will have very large, complex forms, multiple forms, or advanced validations, a form library will solve many problems and make your code more maintainable.

Some libraries offer robust validation out of the box, while others integrate well with popular validation dependencies.

---

## 🚀 Available Options

- **React Hook Form**
- **Formik** with Yup
- **Zod** for validations


-----------------------

## 🐻 Zustand

Simple global state management

**What is Zustand?**

Zustand is a library for managing global state in your React applications.
Its API is very straightforward and can be used with both JavaScript and TypeScript.
It is one of the main alternatives to Redux Toolkit.

### Installation

```bash
npm install zustand
```

### Basic Usage Example

```tsx
// store.ts
import { create } from 'zustand';

interface BearState {
	bears: number;
	increase: () => void;
}

export const useBearStore = create<BearState>((set) => ({
	bears: 0,
	increase: () => set((state) => ({ bears: state.bears + 1 })),
}));
```

```tsx
// In your component
import { useBearStore } from './store';

function BearCounter() {
	const bears = useBearStore((state) => state.bears);
	const increase = useBearStore((state) => state.increase);
	return (
		<div>
			<h2>{bears} bears</h2>
			<button onClick={increase}>Increase</button>
		</div>
	);
}
```