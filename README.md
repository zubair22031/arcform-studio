# ARCFORM Studio - Architecture, Design & BIM Website

A professional portfolio website for architecture, design, and BIM services with a full admin panel for content management.

## Features

- 🏗️ **Public Website**: Hero section, services, project portfolio, team, contact form
- 🔐 **Admin Panel**: Full CMS to manage projects, services, team, messages, and site settings
- 📱 **Responsive**: Works on all devices
- ⚡ **Fast**: Built with Next.js 16 and optimized for performance

## Tech Stack

- **Frontend**: Next.js 16 (App Router), React 19, Tailwind CSS 4
- **Backend**: Next.js API Routes
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: JWT-based admin authentication

---

## 🚀 Deployment Guide (Permanent Hosting)

### Step 1: Create a Free PostgreSQL Database (Neon)

1. Go to [https://neon.tech](https://neon.tech) and sign up (free)
2. Create a new project
3. Copy the connection string (looks like: `postgresql://user:password@ep-xxx.region.aws.neon.tech/dbname?sslmode=require`)

### Step 2: Deploy to Vercel (Free)

1. Go to [https://vercel.com](https://vercel.com) and sign up with GitHub
2. Click **"Add New Project"**
3. Import this repository (upload to GitHub first, or use Vercel CLI)
4. Add Environment Variable:
   - Name: `DATABASE_URL`
   - Value: *Your Neon connection string from Step 1*
5. Click **Deploy**

### Step 3: Initialize the Database

After deployment, run this command locally or use Vercel's terminal:

```bash
npx drizzle-kit push
```

Then seed the database by visiting: `https://your-domain.vercel.app/api/seed` (you'll need to create this endpoint, or run the seed script locally connected to your Neon database).

---

## 🔑 Default Admin Login

- **Email**: `admin@studio.com`
- **Password**: `admin123`

⚠️ **Important**: Change the password after first login!

---

## 📁 Project Structure

```
src/
├── app/
│   ├── page.tsx              # Homepage
│   ├── ContactForm.tsx       # Contact form component
│   ├── projects/[slug]/      # Project detail pages
│   ├── admin/                # Admin login
│   ├── admin/dashboard/      # Admin panel pages
│   └── api/                  # API routes
├── db/
│   ├── schema.ts             # Database schema
│   ├── index.ts              # Database connection
│   └── seed.ts               # Seed data
└── lib/
    └── auth.ts               # Authentication utilities
```

---

## 🛠️ Local Development

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your DATABASE_URL

# Push database schema
npx drizzle-kit push

# Seed the database
npx tsx src/db/seed.ts

# Run development server
npm run dev
```

---

## 📧 Support

For questions or customization, contact the developer.

---

© 2025 ARCFORM Studio
