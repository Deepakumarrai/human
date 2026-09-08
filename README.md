# Human Frontend Application

A modern frontend web application built with **Next.js**, **React**, **TypeScript**, and **Tailwind CSS**.

---

## 🚀 Tech Stack

- **Framework**: [Next.js](https://nextjs.org/) (App Router & Turbopack)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **UI & Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Icons & Utilities**: [Lucide React](https://lucide.dev/), `clsx`, `tailwind-merge`
- **Linting & Code Quality**: ESLint

---

## 📦 Getting Started

### Prerequisites

Ensure you have **Node.js** (v18.18 or higher recommended) and **npm** installed on your system.

```bash
node -v
npm -v
```

### 1. Installation

Install all required project dependencies:

```bash
npm install
```

### 2. Running the Development Server

Start the local development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to view the application.

---

## 🛠️ Available Scripts

| Command | Description |
| :--- | :--- |
| `npm run dev` | Starts the development server on `http://localhost:3000` |
| `npm run build` | Builds the application for production |
| `npm run start` | Runs the built production application |
| `npm run lint` | Runs ESLint to check for code issues |

---

## 📁 Project Structure

```text
human/
├── public/              # Static assets (images, icons, etc.)
├── src/
│   └── app/             # Next.js App Router (pages, layouts, styles)
│       ├── favicon.ico
│       ├── globals.css  # Global styling
│       ├── layout.tsx   # Root layout
│       └── page.tsx     # Home page component
├── next.config.ts       # Next.js configuration
├── package.json         # Project metadata and dependencies
├── postcss.config.mjs   # PostCSS configuration
├── tsconfig.json        # TypeScript configuration
└── README.md            # Project documentation
```

---

## 🌐 Deployment

The easiest way to deploy this Next.js app is using the [Vercel Platform](https://vercel.com/new).

For detailed deployment instructions, check out the [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying).
