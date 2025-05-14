# 📁 Project Structure Next.js 15 — Real World & Best Practices

```
my-app/
├── 📁 app                  # Next.js app directory (routes, pages)
│   ├── 📁 (auth)           # Auth routes (login, register)
│   │   ├── 📁 login
│   │   │   └── 📄 page.tsx           # Login page
│   │   └── 📁 register
│   │       └── 📄 page.tsx           # Register page
│   ├── 📁 (dashboard)      # Protected routes (requires login)
│   │   └── 📄 page.tsx
│   ├── 📄 layout.tsx       # Root layout
│   └── 📄 page.tsx         # Home page
│   └── 📄 global.css       # Global Tailwind/Custom CSS
│
├── 📁 actions          # ✅ Server Actions (mutations/form handlers)
│   ├── 📄 auth.ts
│   └── 📄 product.ts
│
├── 📁 hooks            # Custom hooks 
│   ├── 📄 use-mobile.ts
│   └── 📄 etc.
│
├── 📁 lib                  # Server-side logic, shared libraries
│   ├── 📁 api              # ✅ DAL - Data Access Layer
│   │   ├── 📄 auth.ts      # Fetch login/register
│   │   └── 📄 product.ts   # Fetch product list
│   ├── 📁 auth             # Auth helpers (session, guards)
│   │   ├── 📄 session.ts
│   │   └── 📄 guard.ts
│   └── 📁 utils            # Helper utilities (e.g., formatters)
│       └── 📄 formatter.ts
│
├── 📁 dto                  # ✅ DTO - Data Transfer Objects
│   ├── 📄 sign-in.dto.ts
│   ├── 📄 register.dto.ts
│   └── 📄 product.dto.ts
│
├── 📁 types                # Global types and interfaces
│   ├── 📄 user.ts
│   ├── 📄 product.ts
│   └── 📄 response.ts
│
├── 📁 components           # Reusable UI components
│   ├── 📁 form
│   │   └── 📄 login-form.tsx
│   ├── 📁 product
│   │   ├── 📄 product-list.tsx
│   │   └── 📄 product-card.tsx
│   └── 📁 ui
│       └── 📄 button.tsx
│       └── 📄 input.tsx
│       └── 📄 etc.
│
├── 📁 layouts
│       └── 📄 app-layout.tsx
│       └── 📄 auth-layout.tsx
│
├── 📁 constants            # Static constants (route names, config)
│   └── 📄 routes.ts
│
├── 📄 middleware.ts        # Middleware for auth/routing
├── 📁 public               # Static assets (images, icons, etc)
├── 📄 tsconfig.json
└── 📄 next.config.js
```

---

## 📌 Note

- **DAL (`lib/api/`)**: All the logic to fetch to backend/API
- **DTO (`dto/`)**: Data input/output scheme from form or API
- **Server Actions (`app/actions/`)**: Process forms or actions directly from the client
- **Komponen UI (`components/`)**: Arranged by domain/function
