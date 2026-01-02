# Next.js Dashboard

A full-featured financial dashboard application built with Next.js 15, featuring invoice management, customer tracking, and real-time analytics.

## Features

- 📊 **Dashboard Overview** - View revenue charts, latest invoices, and key metrics
- 📝 **Invoice Management** - Create, edit, and delete invoices with full CRUD operations
- 👥 **Customer Management** - Browse and manage customer information
- 🔐 **Authentication** - Secure login system with NextAuth.js v5
- 🔍 **Search & Filtering** - Real-time search with debouncing
- 📱 **Responsive Design** - Mobile-friendly interface with Tailwind CSS
- ⚡ **Server Actions** - Optimistic UI updates and server-side data mutations
- 🎨 **Modern UI** - Beautiful components with Heroicons and custom fonts
- 💾 **Database Integration** - PostgreSQL database with type-safe queries
- 🚨 **Error Handling** - Custom error boundaries and not-found pages
- ⏳ **Loading States** - Skeleton loaders for better UX

## Tech Stack

- **Framework:** [Next.js 15](https://nextjs.org/) (App Router)
- **Language:** [TypeScript](https://www.typescriptlang.org/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **Database:** [PostgreSQL](https://www.postgresql.org/) via [postgres](https://github.com/porsager/postgres)
- **Authentication:** [NextAuth.js v5](https://next-auth.js.org/)
- **Icons:** [Heroicons](https://heroicons.com/)
- **Forms:** [@tailwindcss/forms](https://github.com/tailwindlabs/tailwindcss-forms)
- **Validation:** [Zod](https://zod.dev/)
- **Password Hashing:** [bcrypt](https://github.com/kelektiv/node.bcrypt.js)
- **Package Manager:** [pnpm](https://pnpm.io/)

## Prerequisites

- Node.js 18.17 or later
- pnpm (recommended) or npm
- PostgreSQL database

## Getting Started

### 1. Clone the repository

```bash
git clone <repository-url>
cd nextjs-dashboard
```

### 2. Install dependencies

```bash
pnpm install
```

### 3. Set up environment variables

Create a `.env` file in the root directory:

```env
# Database
POSTGRES_URL=your_postgres_connection_string

# NextAuth
AUTH_SECRET=your_auth_secret
AUTH_URL=http://localhost:3000
```

To generate an auth secret:
```bash
openssl rand -base64 32
```

### 4. Seed the database

```bash
pnpm dev
```

Then navigate to `http://localhost:3000/seed` to seed the database with sample data.

### 5. Run the development server

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

- `pnpm dev` - Start development server with Turbopack
- `pnpm build` - Build for production
- `pnpm start` - Start production server
- `pnpm lint` - Run ESLint

## Project Structure

```
nextjs-dashboard/
├── app/
│   ├── dashboard/          # Dashboard pages
│   │   ├── (overview)/     # Dashboard overview with parallel routes
│   │   ├── customers/      # Customer management
│   │   └── invoices/       # Invoice CRUD operations
│   ├── lib/                # Utilities and data functions
│   │   ├── actions.ts      # Server actions
│   │   ├── data.ts         # Database queries
│   │   └── definitions.ts  # TypeScript types
│   ├── login/              # Authentication pages
│   ├── ui/                 # Reusable UI components
│   └── layout.tsx          # Root layout
├── public/                 # Static assets
├── auth.config.ts          # Auth configuration
├── auth.ts                 # Auth setup
└── middleware.ts           # Route protection
```

## Key Features Explained

### Server Actions

The app uses Next.js Server Actions for data mutations, providing:
- Type-safe form submissions
- Automatic revalidation
- Optimistic UI updates

### Route Groups

Uses route groups `(overview)` for organizing related routes without affecting URL structure.

### Error Handling

- Custom error boundaries for graceful error handling
- Not-found pages for invalid resources
- Form validation with Zod

### Performance Optimization

- Streaming with `loading.tsx` files
- Parallel data fetching
- Route segment caching
- Optimized images with Next.js Image

## Database Schema

The application uses the following main tables:
- `users` - User authentication
- `customers` - Customer information
- `invoices` - Invoice records
- `revenue` - Revenue data for charts

## Authentication

Default login credentials (after seeding):
- Email: user@nextmail.com
- Password: 123456

## Deployment

### Deploy to Vercel

The easiest way to deploy is using [Vercel](https://vercel.com):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

1. Push your code to GitHub
2. Import your repository to Vercel
3. Add environment variables
4. Deploy

### Manual Deployment

```bash
pnpm build
pnpm start
```

Ensure your production database is configured and environment variables are set.

## Learn More

This project is built following the [Next.js Learn Course](https://nextjs.org/learn). To learn more about the technologies used:

- [Next.js Documentation](https://nextjs.org/docs)
- [Next.js App Router](https://nextjs.org/docs/app)
- [Server Actions](https://nextjs.org/docs/app/building-your-application/data-fetching/server-actions-and-mutations)
- [NextAuth.js Documentation](https://next-auth.js.org/)

## License

This project is open source and available under the [MIT License](LICENSE).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
