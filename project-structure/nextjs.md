# 📁 Project Structure Next.js 15 — Real World & Best Practices

```
my-app/
├── 📁 app                  # Next.js app directory (routes, pages)
│   ├── 📁 (auth)           # Auth routes (signin, signup)
│   │   ├── 📁 signin
│   │   │   └── 📄 page.tsx   # Signin page
│   │   └── 📁 signup
│   │       └── 📄 page.tsx   # Signup page
│   ├── 📁 (dashboard)      # Protected routes (requires signin)
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
│   ├── 📁 auth             # Auth helpers (session, guards)
│   │   ├── 📄 session.ts
│   │   └── 📄 guard.ts
│   │
│   ├── 📁 data              # ✅ DAL - Data Access Layer
│   │   ├── 📄 auth.ts      # Fetch signin/signup
│   │   └── 📄 product.ts   # Fetch product list
│   │
│   ├── 📁 definitions      #  Schemas validation
│   │   ├── 📄 auth.ts      
│   │   └── 📄 product.ts   
│   │
│   ├── 📁 dto                  # ✅ DTO - Data Transfer Objects
│   │   ├── 📄 sign-in.dto.ts
│   │   └── 📄 register.dto.ts
│   │
│   └── 📁 utils            # Helper utilities (e.g., formatters)
│       └── 📄 formatter.ts
│
│
├── 📁 components           # Reusable UI components
│   ├── 📁 auth
│   │   └── 📄 signup-form.tsx
│   │   └── 📄 signin-form.tsx
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
│       └── 📄 etc.
│
├── 📁 types                # Global types and interfaces
│   ├── 📄 user.ts
│   ├── 📄 product.ts
│   └── 📄 response.ts
│
├── 📄 middleware.ts        # Middleware for auth/routing
├── 📁 public               # Static assets (images, icons, etc)
├── 📄 tsconfig.json
└── 📄 next.config.js
```

---

## 📌 Note

- **DAL (`lib/data/`)**: All the logic to fetch to database/API
- **DTO (`lib/dto/`)**: Data input/output scheme from form or API
- **Server Actions (`app/actions/`)**: Process forms or actions directly from the client
- **Component UI (`components/`)**: Arranged by domain/function
