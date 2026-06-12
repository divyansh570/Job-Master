# Job-Master 💼

Job-Master is a robust, scalable web application designed to bridge the gap between talented job seekers and recruiters looking for top-tier talent. This platform focuses on eliminating the cluttered noise of traditional job boards by offering real-time tracking, intuitive UI/UX, and streamlined application workflows.

---

## 🚀 Detailed Features & System Capabilities

### 1. Unified Authentication & Dual Role Dashboards
- **Job Seeker Experience:** An interactive portal where users can build out professional profiles, upload resumes, keep track of application statuses (e.g., *Applied, Interviewing, Offered, Rejected*), and bookmark jobs.
- **Recruiter Management Portal:** A comprehensive workspace for HR teams and hiring managers to post detailed job descriptions, edit active listings, and move applicants through different hiring stages with visual indicators.

### 2. Intelligent Search & Granular Filtering Engine
- Dynamic filtering that searches across multiple metadata parameters (e.g., Job Type: *Full-time/Remote/Hybrid*, Experience Level, Salary Range, and Specific Tech Stacks like MERN, Java, Python).
- Optimized for instant UI updates without requiring page reloads, providing a desktop-app-like experience.

### 3. Application Pipeline Tracking
- A linear progression workflow that acts like a visual funnel for applications, helping candidates stay updated on where exactly they stand in the recruitment loop.

---

## 🛠️ Architecture & Tech Stack Justification

- **Vite + React.js:** Chosen over traditional setups for lightning-fast Hot Module Replacement (HMR) and optimized production builds. React’s component-driven architecture ensures features can be added modularly without breaking existing code.
- **Tailwind CSS + PostCSS:** A utility-first styling approach that eliminates the need for giant, unmanageable CSS files. Styling is handled directly inside components, making theme changes (like Dark Mode) extremely clean.
- **Custom Components Configuration (`components.json`):** Integrated to support consistent design tokens (borders, shadows, primary color schemes), making the UI predictable and highly professional.

---

## 📁 Deep-Dive Project Structure

The codebase is organized using a feature-and-role separation pattern. This prevents code duplication and keeps the repository clean as the project scales into a production-grade application.

```text
Job-Master/
├── public/                 # Static assets directly served by the server
│   └── favicon.ico         # Application icon shown in browser tabs
├── src/
│   ├── assets/             # Media and global structural definitions
│   │   └── index.css       # Core Tailwind injections and base component styling
│   │
│   ├── components/         # Reusable presentation atomic elements
│   │   ├── ui/             # Low-level primitives (Buttons, Inputs, Badges, Modals)
│   │   ├── Navbar.jsx      # Global navigational header with role-based links
│   │   └── ProtectedRoute.jsx # Wrapper component to handle page access control
│   │
│   ├── hooks/              # Custom React Hooks to separate logic from UI layout
│   │   └── useAuth.js      # Custom abstraction for managing user sessions
│   │
│   ├── pages/              # Higher-level views corresponding to application routes
│   │   ├── Home.jsx        # Landing page with value propositions and call-to-actions
│   │   ├── Login.jsx       # Universal secure gateway interface
│   │   ├── Dashboard.jsx   # Context-aware user workspace (Recruiter vs. Candidate)
│   │   └── JobDetails.jsx  # Individual job profile views with application actions
│   │
│   ├── context/            # Global state stores accessible by any deep component
│   │   └── AuthContext.jsx # Handles global authentication state, tokens, and roles
│   │
│   ├── utils/              # Helper engines and pure functional configurations
│   │   └── helpers.js      # Currencies formatting, date conversion, and input validation
│   │
│   ├── App.jsx             # Orchestrates client-side routing, hooks layout layouts
│   └── main.jsx            # The absolute bootstrap entry point mounting React to the DOM
│
├── .eslintrc.cjs           # Production-grade linter rules for enforcing strict code standards
├── .gitignore              # Specifies system architectures, keys, and dependency directories to skip
├── components.json         # Stores design framework paths and configuration structures
├── index.html              # The foundational DOM template where React injects components
├── jsconfig.json           # Simplifies paths by setting up module aliases (e.g., using @/components)
├── package.json            # Manifest tracking external scripts, metadata, and dependencies
├── postcss.config.js       # Pre-processes styling rules into highly-compatible browser instructions
└── tailwind.config.js      # Layout architecture where custom colors, animations, and typography are defined
