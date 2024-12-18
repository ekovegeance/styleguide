# Laravel Inertia React TypeScript Coding Style Guide

## Table of Contents
1. [General Principles](#general-principles)
2. [Folder and File Structure](#folder-and-file-structure)
3. [Naming Conventions](#naming-conventions)
4. [Code Formatting](#code-formatting)
5. [Blade Templates](#blade-templates)
6. [Eloquent Models](#eloquent-models)
7. [Controllers](#controllers)
8. [Routes](#routes)
9. [React and TypeScript](#react-and-typescript)
10. [Testing](#testing)
11. [Best Practices](#best-practices)

---

## General Principles
- Follow the [PSR-12](https://www.php-fig.org/psr/psr-12/) coding standard for Laravel.
- Follow [Airbnb JavaScript/React Style Guide](https://github.com/airbnb/javascript) for React and TypeScript.
- Maintain consistent and readable code across both the backend and frontend.
- Adhere to Laravel's and Inertia's conventions for seamless integration.

---

## Folder and File Structure
- Organize backend code into appropriate folders (`Models`, `Controllers`, `Services`, `Jobs`, etc.).
- Place frontend code in the `resources/js` folder.
- Use domain-driven or feature-based folder structures for React components.

### Example Structure
```
app/
  Models/
  Http/
    Controllers/
  Services/
resources/
  js/
    components/
      ui/
    layouts/
    pages/
    utils/
  views/
routes/
  web.php
  api.php
  auth.php
```

---

## Naming Conventions

### Backend
- Use **PascalCase** for class names.
- Use **camelCase** for variables and methods.
- Use **snake_case** for database column names and configuration keys.

### Frontend
- Use **PascalCase** for React components.
- Use **camelCase** for variables, functions, and hooks.
- Use **kebab-case** for file and folder names.
- Use descriptive names for props and state variables.

### Examples
```typescript
// Good (React)
const UserCard: React.FC<{ userName: string }> = ({ userName }) => {
  return <div>{userName}</div>;
};

// Bad
const user_card = (props) => {
  return <div>{props.username}</div>;
};
```

---

## Code Formatting

### Backend
- Use **4 spaces** for indentation.
- Place one blank line between logical blocks of code.
- Limit line length to **120 characters** where possible.

### Frontend
- Use Prettier and ESLint for consistent formatting.
- Prefer single quotes `'` over double quotes `"` in JavaScript/TypeScript.
- Limit JSX lines to **80-120 characters**.

---

## Blade Templates
- Use Blade only for initializing Inertia and managing layouts.
- Keep Blade templates minimal and delegate logic to React components.

### Example
`resources/views/app.blade.php`
```blade
<!DOCTYPE html>
<html lang="en">
<head>
    @viteReactRefresh
    @vite(['resources/js/app.tsx'])
</head>
<body>
    @inertia
</body>
</html>
```

---

## Eloquent Models
- Use meaningful method names for relationships.
- Avoid querying in React components; use controllers to fetch data.
- Use `fillable` or `guarded` attributes to prevent mass assignment vulnerabilities.

### Example
```php
class User extends Model {
    protected $fillable = ['name', 'email'];

    public function posts() {
        return $this->hasMany(Post::class);
    }
}
```

---

## Controllers
- Keep controllers thin by delegating logic to services or actions.
- Return Inertia responses for rendering React pages.
- Use dependency injection to pass services and repositories.

### Example
```php
public function index(Request $request) {
    $users = User::paginate(10);

    return Inertia::render('Users/Index', [
        'users' => $users,
    ]);
}
```

---

## Routes
- Define web routes in `routes/web.php`.
- Use route names for URLs instead of hardcoding paths.
- Group related routes using `Route::group` and middleware.

### Example
```php
Route::middleware(['auth'])->group(function () {
    Route::get('/dashboard', [DashboardController::class, 'index'])->name('dashboard');
});
```

---

## React and TypeScript

### Folder Structure
- Group components, pages, and utilities into meaningful directories.
- Use TypeScript for type safety and better maintainability.

### Component Structure
- Use functional components and React hooks.
- Separate logic into custom hooks where possible.
- Use `Props` interfaces to define component props.

### State Management
- Prefer React Context or Zustand for global state.
- Avoid prop drilling by using context or state libraries.

### Examples
```typescript
// Custom Hook
import { useState } from 'react';

function useCounter(initialValue: number) {
  const [count, setCount] = useState(initialValue);
  const increment = () => setCount(count + 1);
  return { count, increment };
}

// Component
const Counter: React.FC = () => {
  const { count, increment } = useCounter(0);

  return (
    <div>
      <p>{count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
};
```

---

## Testing
- Write unit tests using Jest for React components and Laravel's built-in PHPUnit for backend logic.
- Use factories for creating test data in Laravel.
- Test Inertia responses to ensure proper integration.

### Example
```php
// PHPUnit Test
public function test_dashboard_access() {
    $user = User::factory()->create();

    $response = $this->actingAs($user)->get('/dashboard');

    $response->assertStatus(200);
}
```

```typescript
// Jest Test
import { render, screen } from '@testing-library/react';
import Counter from './Counter';

test('renders counter', () => {
  render(<Counter />);
  const buttonElement = screen.getByText(/increment/i);
  expect(buttonElement).toBeInTheDocument();
});
```

---

## Best Practices
- Use environment variables for sensitive data in both Laravel and React.
- Avoid inline styles in React; use CSS modules or utility-first frameworks like TailwindCSS.
- Follow Laravel's Query Builder or Eloquent ORM instead of raw SQL.
- Use Inertia's shared props for global data like user info.
- Regularly run linters (`eslint`, `phpcs`) and formatters (`prettier`, `phpcbf`) to maintain code quality.

---
