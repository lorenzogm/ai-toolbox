# GitHub Copilot Instructions

## Project Overview
This project is a frontend application built with modern web technologies following strict conventions for maintainability and consistency.

## Tech Stack
- **TypeScript**: Primary language for type safety
- **React**: UI library for building components
- **Tailwind CSS**: Utility-first CSS framework for styling
- **React Router**: For client-side routing
- **ESLint**: Code linting and formatting

## Naming Conventions

### Files and Directories
- **Always use kebab-case** for all file and directory names
- Examples: `user-profile.tsx`, `navigation-bar.ts`, `api-client.js`

### React Components
- **Use PascalCase** for React component names
- Component files should match the component name but in kebab-case
- Examples: `UserProfile` component in `user-profile.tsx`, `NavigationBar` component in `navigation-bar.tsx`

### Variables, Functions, and Other Identifiers
- **Use camelCase** for variables, functions, properties, and methods
- Examples: `userData`, `handleUserLogin()`, `isLoggedIn`, `fetchUserProfile()`

## Folder Structure

```
src/
├── ui/
│   └── components/
│       ├── button.tsx          # Button component
│       ├── input.tsx           # Input component
│       ├── card.tsx            # Card component
│       ├── modal.tsx           # Modal component
│       └── ...                 # Other reusable UI components
├── pages/
│   ├── home-page.tsx
│   ├── user-profile-page.tsx
│   └── ...
└── types/
    ├── user.ts
    └── ...
```

### File Collocation Principles
- **Avoid global utility folders**: Instead of centralized `hooks/` or `utils/` folders, collocate related files near where they are used
- **Keep related code together**: Place helper functions, custom hooks, and utilities in the same directory as the components that use them
- **Example**: If a `user-profile-page.tsx` needs a custom hook, create `user-profile-page.hook.ts` in the same directory

## UI Component Guidelines

### Core Principles
1. **Presentational Only**: UI components should be purely presentational
2. **No Data Fetching**: Components should not perform API calls or data fetching
3. **No Global State**: Components should not manage or access global state
4. **No Framework Dependencies**: UI components should not depend on routing or other framework-specific features

### HTML Tag Component Mapping
Every HTML tag used in the application should have a corresponding React component:

- `<button>` → `Button` component
- `<input>` → `Input` component
- `<div>` → `Container` or `Box` component (when styled)
- `<p>` → `Text` or `Paragraph` component
- `<h1>`, `<h2>`, etc. → `Heading` component with size prop
- `<img>` → `Image` component
- `<a>` → `Link` component
- `<form>` → `Form` component
- `<select>` → `Select` component
- `<textarea>` → `Textarea` component

### Component Structure
All UI components should follow this structure:

```typescript
import React from 'react';

interface ComponentNameProps {
  // Props with descriptive names using camelCase
  children?: React.ReactNode;
  className?: string;
  // Other props...
}

export function ComponentName(props: ComponentNameProps) {
  return (
    <div className={`base-styles ${props.className || ''}`}>
      {props.children}
    </div>
  );
}
```

### Props Guidelines
- Use TypeScript interfaces for all component props
- Props should be named using camelCase
- **Avoid props destructuring**: Use `props.propName` instead of destructuring
- Include `children` and `className` props for maximum flexibility
- Use descriptive prop names that clearly indicate their purpose
- Access props through the props object: `props.children`, `props.className`, etc.

### Styling Guidelines
- Use Tailwind CSS classes for all styling
- Create reusable component variants using props
- Avoid inline styles
- Use conditional classes for different states

Example:
```typescript
interface ButtonProps {
  variant?: 'primary' | 'secondary';
  size?: 'small' | 'medium' | 'large';
  disabled?: boolean;
  children: React.ReactNode;
  className?: string;
}

export function Button(props: ButtonProps) {
  const variant = props.variant || 'primary';
  const size = props.size || 'medium';
  const disabled = props.disabled || false;
  const className = props.className || '';

  const baseClasses = 'font-medium rounded focus:outline-none focus:ring-2';
  const variantClasses = {
    primary: 'bg-blue-600 text-white hover:bg-blue-700',
    secondary: 'bg-gray-200 text-gray-900 hover:bg-gray-300',
  };
  const sizeClasses = {
    small: 'px-3 py-1.5 text-sm',
    medium: 'px-4 py-2 text-base',
    large: 'px-6 py-3 text-lg',
  };

  return (
    <button
      className={`${baseClasses} ${variantClasses[variant]} ${sizeClasses[size]} ${disabled ? 'opacity-50 cursor-not-allowed' : ''} ${className}`}
      disabled={disabled}
    >
      {props.children}
    </button>
  );
}
```

## Code Generation Guidelines

When generating code, always:

1. **Follow naming conventions** strictly
2. **Create TypeScript interfaces** for all props and data structures
3. **Use function declarations** instead of arrow functions for components
4. **Import React explicitly** when using JSX
5. **Export components using named exports**
6. **Include proper TypeScript types** for all parameters and return values
7. **Use Tailwind classes** for styling
8. **Implement proper component composition** with children props
9. **Add className prop** to all components for styling flexibility
10. **Avoid props destructuring** - always use `props.propName` pattern
11. **Use single useState** when state is needed - combine related state into one useState call
12. **Collocate related files** - avoid global utils/hooks folders, keep files near where they're used

## State Management Guidelines

### Single useState Pattern
When components need state, use a single `useState` call to manage related state:

```typescript
interface ComponentState {
  isLoading: boolean;
  data: any[];
  error: string | null;
}

export function DataComponent(props: DataComponentProps) {
  const [state, setState] = React.useState<ComponentState>({
    isLoading: false,
    data: [],
    error: null,
  });

  const updateState = (updates: Partial<ComponentState>) => {
    setState(prevState => ({ ...prevState, ...updates }));
  };

  // Use state.isLoading, state.data, state.error
  // Update with updateState({ isLoading: true })
}
```

## ESLint Configuration
Follow these ESLint rules:
- Prefer const over let when variables are not reassigned
- Use function declarations for component definitions
- Always use semicolons
- Use single quotes for strings
- No unused variables or imports
- Proper TypeScript type annotations

## Example Component Implementation

```typescript
// file: ui/components/card.tsx
import React from 'react';

interface CardProps {
  children: React.ReactNode;
  title?: string;
  className?: string;
  variant?: 'default' | 'outlined' | 'elevated';
}

export function Card(props: CardProps) {
  const variant = props.variant || 'default';
  const className = props.className || '';

  const baseClasses = 'rounded-lg p-6';
  const variantClasses = {
    default: 'bg-white',
    outlined: 'bg-white border border-gray-200',
    elevated: 'bg-white shadow-lg',
  };

  return (
    <div className={`${baseClasses} ${variantClasses[variant]} ${className}`}>
      {props.title && (
        <h3 className="text-lg font-semibold mb-4 text-gray-900">
          {props.title}
        </h3>
      )}
      {props.children}
    </div>
  );
}
```

These instructions ensure consistent, maintainable, and scalable frontend code generation that follows modern React and TypeScript best practices.