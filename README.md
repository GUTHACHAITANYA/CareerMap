# 🗺️ CareerMap - AI-Powered Career Intelligence Platform

<p align="center">
  <b>Architect your professional evolution with personalized career roadmaps, AI mock interviews, smart resume building, and real-time job matching.</b>
</p>

---

## ✨ Features

- **🤖 Next-Gen AI Career Engine:** Powered by Google Gemini AI (`@google/genai`) for customized career pathing, skill gap analysis, and tailored recommendations.
- **🎙️ AI Mock Interview Studio:** Practice real-time interactive technical and behavioral interviews with performance scoring, audio/video capabilities, and detailed feedback across communication, technical skills, confidence, and integrity.
- **📄 ATS Resume Builder & Analyzer:** Create dynamic, professional resumes with real-time scoring, tailored enhancement suggestions, and export to PDF.
- **📊 Interactive Visual Roadmaps:** Dynamic visualizations using **D3.js** and **Recharts** to map your skill progression and career trajectories.
- **💼 Opportunity Matching:** Real-time job and internship aggregation tailored to your target role and skill profile.
- **🔐 Secure Authentication & OTP Verification:** Multi-factor email OTP verification (via Nodemailer & Resend) and secure JWT session management with bcrypt-hashed credentials.
- **🌓 Modern Responsive UI:** Built with React 19, Tailwind CSS v4, Motion (Framer Motion) animations, and Lucide icons.

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** [React 19](https://react.dev/) & [Vite](https://vitejs.dev/)
- **Routing:** [React Router DOM v7](https://reactrouter.com/)
- **Styling:** [Tailwind CSS v4](https://tailwindcss.com/)
- **Animations:** [Motion](https://motion.dev/) (Framer Motion)
- **Data Visualization:** [D3.js](https://d3js.org/) & [Recharts](https://recharts.org/)
- **Icons & Assets:** [Lucide React](https://lucide.dev/)
- **Document Generation:** [jsPDF](https://github.com/parallax/jsPDF) & [React Dropzone](https://react-dropzone.js.org/)

### Backend
- **Runtime:** [Node.js](https://nodejs.org/) & [Express.js](https://expressjs.com/)
- **TypeScript Runner:** [TSX](https://github.com/privatenumber/tsx)
- **AI Integration:** [Google GenAI SDK](https://www.npmjs.com/package/@google/genai)
- **Email Service:** [Nodemailer](https://nodemailer.com/) (SMTP/Gmail) & [Resend API](https://resend.com/)
- **Authentication:** JSON Web Tokens (`jsonwebtoken`), `bcryptjs`, `cookie-parser`

### Database
- **Database:** PostgreSQL ([Supabase](https://supabase.com/) / local PostgreSQL)
- **ORM:** [Drizzle ORM](https://orm.drizzle.team/)
- **Migrations:** [Drizzle Kit](https://orm.drizzle.team/kit-docs/overview)

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v18.0.0 or higher recommended)
- **npm** (v9.0.0 or higher)

### 1. Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/CareerMap.git
cd CareerMap
npm install
```

### 2. Environment Configuration

Create a `.env` file in the project root:

```bash
cp .env.example .env
```

Configure your environment variables:

```env
# 1. Google Gemini API Key (Get from Google AI Studio)
GEMINI_API_KEY=your_gemini_api_key

# 2. Application URL
APP_URL=http://localhost:3000

# 3. PostgreSQL Database Connection URL (Supabase, Neon, or local)
DATABASE_URL=postgresql://user:password@host:5432/postgres

# 4. JWT Secret for secure authentication
JWT_SECRET=your-secret-random-key

# 5. Email Verification Configuration (Gmail / SMTP / Resend)
EMAIL_SERVICE=gmail
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-16-character-app-password
RESEND_API_KEY=your_resend_api_key   # Optional fallback
```

### 3. Database Migration

Run the migration script to set up tables (`users`, `resumes`, `interviews`, `quiz_results`, `code_snippets`):

```bash
npx tsx apply-migration.ts
```

To verify database tables:

```bash
npx tsx check-tables.ts
```

### 4. Running the Development Server

Start the development server (runs backend and Vite frontend together):

```bash
npm run dev
```

Visit **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## 🏗️ Project Architecture

```
CareerMap/
├── src/
│   ├── components/       # Reusable UI components (Navbar, Footer, Modal, etc.)
│   ├── context/          # State management (AuthContext, ThemeContext)
│   ├── data/             # Static reference datasets and configurations
│   ├── db/               # Drizzle schema definitions (schema.ts)
│   ├── pages/            # Page views (Dashboard, Roadmap, Interview, Resume, Jobs)
│   ├── services/         # Client API services and job catalog aggregations
│   ├── utils/            # Helper utilities and formatters
│   ├── App.tsx           # Main application routing and shell
│   └── main.tsx          # Application entry point
├── drizzle/              # Drizzle SQL migration files
├── public/               # Public assets and icons
├── server.ts             # Express application & API backend + Vite middleware
├── package.json          # Dependencies and npm scripts
└── vite.config.ts        # Vite build & plugin configurations
```

---

## 📜 Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts server with live auto-reload via `tsx watch` |
| `npm run build` | Compiles Vite frontend and bundles backend into `dist/` |
| `npm start` | Runs the compiled production build from `dist/` |
| `npm run lint` | Runs TypeScript type checking (`tsc --noEmit`) |
| `npm run clean` | Cleans up the `dist` build directory |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
