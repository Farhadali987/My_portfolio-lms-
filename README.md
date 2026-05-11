# 🚀 Portfolio & Learning Management System (LMS)

A modern, full-stack portfolio website with an integrated learning platform built with Next.js 14, Prisma, and Tailwind CSS.

## ✨ Features

### Portfolio Features

- **Home Page**: Hero section with stats and featured courses
- **About Page**: Professional experience, education, and bio
- **Skills Page**: Interactive skill visualization with progress bars
- **Projects Page**: GitHub integration showing your repositories
- **Certificates Page**: Display PDF certificates with search functionality
- **Gallery Page**: Image gallery with category filtering
- **Contact Page**: Contact form and social media links

### LMS Features

- **Course Catalog**: Browse available courses with difficulty levels
- **Course Detail Pages**: Lesson lists with progress tracking
- **Lesson Viewer**: Markdown-based content with navigation
- **User Dashboard**: Track enrolled courses and progress
- **Progress Tracking**: Mark lessons as complete/incomplete
- **Achievements**: Unlock badges as you learn

### Authentication

- **Sign Up / Login**: JWT-based authentication
- **Protected Routes**: Dashboard requires authentication
- **Session Management**: 30-day session persistence

## 📚 Included Courses

1. **Python Programming Fundamentals** (10 lessons)
   - Variables, data types, operators
   - Control flow, loops, functions
   - OOP, file handling, error handling

2. **Relational Databases & SQL** (8 lessons)
   - Database concepts, SELECT queries
   - JOINs, aggregate functions
   - Database design, transactions

3. **Agentic AI & Autonomous Systems** (10 lessons)
   - AI agents, LLMs, prompt engineering
   - Building agents, multi-agent systems
   - Tool use, production deployment

## 🛠️ Tech Stack

- **Frontend**: Next.js 14, React, Tailwind CSS, Framer Motion
- **Backend**: Next.js API Routes, Prisma ORM
- **Database**: SQLite (dev) / PostgreSQL (production)
- **Authentication**: JWT with httpOnly cookies
- **Content**: React Markdown for lesson content
- **Icons**: Lucide React

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

1. **Clone the repository**

   ```bash
   cd portfolio-lms
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Set up environment variables**
   Create a `.env` file:

   ```env
   # Database (SQLite for development)
   DATABASE_URL="file:./dev.db"

   # JWT Secret (generate a secure random string)
   JWT_SECRET="your-super-secret-jwt-key"

   # GitHub API (optional)
   GITHUB_USERNAME="your-github-username"
   GITHUB_TOKEN="your-github-token"
   ```

4. **Set up database**

   ```bash
   # Generate Prisma client
   npx prisma generate

   # Push schema to database
   npx prisma db push

   # Seed database with courses
   npm run db:seed
   ```

5. **Run development server**

   ```bash
   npm run dev
   ```

6. **Open in browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 📖 Usage

### Demo Account

- **Email**: admin@example.com
- **Password**: admin123

### Creating a New Account

1. Click "Login" in the navbar
2. Click "Sign up" link
3. Fill in your details
4. Start learning!

### Enrolling in Courses

1. Browse courses at `/courses`
2. Click on a course to view details
3. Click on any lesson to start learning
4. Mark lessons as complete to track progress

### Dashboard Features

- View enrolled courses
- Track overall progress
- See recent activity
- Unlock achievements

## 📁 Project Structure

```
portfolio-lms/
├── prisma/
│   ├── schema.prisma      # Database schema
│   └── seed.ts            # Database seeding
├── src/
│   ├── app/
│   │   ├── (auth)/        # Login, signup pages
│   │   ├── (dashboard)/   # Protected dashboard
│   │   ├── api/           # API routes
│   │   ├── courses/       # Course pages
│   │   ├── projects/      # GitHub projects
│   │   ├── certificates/  # Certificate gallery
│   │   ├── gallery/       # Image gallery
│   │   └── ...            # Other pages
│   ├── components/
│   │   ├── ui/            # Reusable UI components
│   │   ├── layout/        # Layout components
│   │   ├── courses/       # Course-specific components
│   │   └── dashboard/     # Dashboard components
│   ├── lib/
│   │   ├── auth.ts        # Authentication utilities
│   │   ├── db.ts          # Prisma client
│   │   ├── github.ts      # GitHub API
│   │   └── utils.ts       # Helper functions
│   └── data/
│       ├── courses.ts     # Course content
│       └── skills.ts      # Skills data
└── .env                   # Environment variables
```

## 🎨 Customization

### Adding Your Content

1. **Update Personal Info**
   - Edit `src/app/about/page.tsx` for your bio
   - Update `src/data/skills.ts` with your skills
   - Modify `src/app/certificates/page.tsx` with your certificates

2. **GitHub Integration**
   - Set `GITHUB_USERNAME` in `.env`
   - Optionally add `GITHUB_TOKEN` for higher rate limits

3. **Add More Courses**
   - Edit `prisma/seed.ts` to add courses
   - Run `npm run db:seed` to update database

4. **Gallery Images**
   - Add images to `public/` folder
   - Update `src/app/gallery/page.tsx` with image paths

### Styling

- Modify `tailwind.config.ts` for theme colors
- Edit `src/app/globals.css` for global styles
- Update component styles with Tailwind classes

## 🚀 Deployment

### Production Database

For production, use PostgreSQL:

```env
DATABASE_URL="postgresql://user:password@host:5432/portfolio_lms"
```

### Deploy to Vercel

1. Push code to GitHub
2. Import project in Vercel
3. Set environment variables
4. Deploy

### Deploy to Other Platforms

```bash
npm run build
npm run start
```

## 📊 Database Schema

```prisma
User
├── id
├── email
├── password (hashed)
├── name
└── enrollments, progress

Course
├── id
├── title
├── description
├── difficulty
├── thumbnail
└── lessons, enrollments

Lesson
├── id
├── courseId
├── title
├── content (Markdown)
├── order
└── progress

Enrollment
├── id
├── userId
├── courseId
└── enrolledAt

Progress
├── id
├── userId
├── lessonId
├── completed
└── completedAt
```

## 🔒 Security

- Passwords hashed with bcrypt
- JWT tokens stored in httpOnly cookies
- Protected API routes
- Input validation on forms

## 📝 API Routes

- `POST /api/auth/signup` - Create account
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout
- `POST /api/progress` - Update lesson progress
- `GET /api/progress` - Get user progress
- `GET /api/github` - Fetch GitHub repos

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Farhad Ali**

- Portfolio: [farhad.dev](https://farhad.dev)
- GitHub: [@farhad-ali](https://github.com/farhad-ali)
- LinkedIn: [Farhad Ali](https://linkedin.com/in/farhad-ali)

## 🙏 Acknowledgments

- Next.js team for the amazing framework
- Prisma for the excellent ORM
- Tailwind CSS for the utility-first CSS framework
- Lucide React for beautiful icons
- Framer Motion for smooth animations

---

Built with ❤️ using Next.js & Tailwind CSS
"# PERSONALxPORTFOLIO-"

