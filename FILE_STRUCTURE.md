# Portfolio Project - File Structure Documentation

## Overview
This is a Mac-style portfolio application built with **Next.js 15**, **React 19**, **TypeScript**, and **Tailwind CSS 4**. The application features a unique macOS window interface with a scrollable content area.

---

## Root Directory Structure

```
0.2/
├── portfolio-app/           # Main Next.js application
├── package.json            # Root-level dependencies (Vercel Speed Insights)
├── package-lock.json       # Root dependency lock file
├── plan.md                 # Project planning and implementation guide
├── README.md               # Project readme
└── Ecru and Platinum color pallete.png  # Design reference
```

---

## Main Application Structure (`portfolio-app/`)

### Configuration Files

```
portfolio-app/
├── package.json            # Application dependencies and scripts
├── package-lock.json       # Dependency lock file
├── tsconfig.json          # TypeScript configuration
├── next.config.ts         # Next.js configuration
├── next-env.d.ts          # Next.js TypeScript declarations
├── postcss.config.mjs     # PostCSS configuration for Tailwind
└── README.md              # Application-specific readme
```

#### Key Dependencies
- **Framework**: Next.js 15.5.4 with Turbopack
- **UI Library**: React 19.1.0
- **Styling**: Tailwind CSS v4 with @tailwindcss/postcss
- **Icons**: lucide-react 0.545.0
- **Analytics**: @vercel/speed-insights 1.2.0
- **Language**: TypeScript 5

#### NPM Scripts
```json
"dev": "next dev --turbopack"    // Development server with Turbopack
"build": "next build"            // Production build
"start": "next start"            // Start production server
"lint": "next lint"              // Run ESLint
```

---

### App Directory (`app/`)

Next.js 15 App Router structure:

```
app/
├── layout.tsx             # Root layout (HTML structure, fonts, metadata)
├── page.tsx              # Home page (main entry point)
├── globals.css           # Global styles, Tailwind directives, custom CSS
└── favicon.ico           # Site favicon
```

**Purpose:**
- `layout.tsx`: Defines the HTML structure, metadata, and global layout
- `page.tsx`: Main page that composes all portfolio sections within MacWindow
- `globals.css`: Contains Tailwind imports, custom scrollbar styles, and global CSS

---

### Components Directory (`components/`)

Reusable React components organized by function:

```
components/
├── MacWindow.tsx              # macOS-style window frame with traffic lights
├── Header.tsx                 # Sticky navigation header with scroll effects
├── Hero.tsx                   # Hero section with intro and social links
├── Sidebar.tsx                # Side navigation (if applicable)
├── Experience.tsx             # Work experience timeline/cards
├── Education.tsx              # Education history section
├── Projects.tsx               # Project showcase grid/cards
├── Skills.tsx                 # Skills and technologies section
├── Contact.tsx                # Contact form or contact information
└── InteractiveBackground.tsx  # Animated background component
```

#### Component Descriptions

**MacWindow.tsx**
- Creates the macOS window frame aesthetic
- Features traffic light buttons (close, minimize, maximize)
- Provides scrollable content area
- Handles fullscreen functionality

**Header.tsx**
- Sticky navigation that stays at top of window
- Scroll-based transparency effects
- Navigation links to different sections
- Resume download button

**Hero.tsx**
- Full viewport height intro section
- Name, title, and brief bio
- Social media links (GitHub, LinkedIn, Email)
- Hover effects and animations

**Experience.tsx / Education.tsx / Skills.tsx**
- Portfolio content sections
- Timeline or card-based layouts
- Placeholder content ready for customization

**Projects.tsx**
- Grid layout for project showcases
- Project cards with descriptions
- Links to live demos and repositories

**Contact.tsx**
- Contact form or contact information
- Social media links
- Email integration (if applicable)

**InteractiveBackground.tsx**
- Animated background effects
- Moves behind the Mac window
- Visual enhancement for the portfolio

---

### Public Directory (`public/`)

Static assets served from the root:

```
public/
├── Joshua (2).JPG         # Profile photo
├── file.svg               # Icon asset
├── globe.svg              # Icon asset
├── window.svg             # Icon asset
├── next.svg               # Next.js logo
└── vercel.svg             # Vercel logo
```

**Purpose:** Static files accessible at `/filename` in the application

---

## Build Process

### Development Build
```bash
cd portfolio-app
npm run dev
```
- Starts development server with Turbopack (fast refresh)
- Runs on http://localhost:3000
- Hot module replacement enabled
- TypeScript type checking in real-time

### Production Build
```bash
cd portfolio-app
npm run build
npm start
```
- Creates optimized production bundle
- Static generation and server-side rendering
- Image optimization
- Code splitting and minification
- Served on http://localhost:3000

---

## Technology Stack

### Core Technologies
- **Next.js 15.5.4**: React framework with App Router
- **React 19.1.0**: UI library with latest features
- **TypeScript 5**: Type-safe JavaScript
- **Tailwind CSS 4**: Utility-first CSS framework

### Development Tools
- **ESLint**: Code linting with Next.js config
- **Turbopack**: Fast bundler for development
- **PostCSS**: CSS transformation for Tailwind

### UI/UX Libraries
- **lucide-react**: Modern icon library
- **@vercel/speed-insights**: Performance monitoring

---

## Design Architecture

### Layout Pattern
```
┌─────────────────────────────────────┐
│     Page Background (Animated)      │
│  ┌───────────────────────────────┐  │
│  │   MacWindow Component         │  │
│  │  ┌─ ─ ─ Traffic Lights       │  │
│  │  │                            │  │
│  │  │  Header (Sticky)           │  │
│  │  │                            │  │
│  │  │  Content Area (Scrollable) │  │
│  │  │    - Hero                  │  │
│  │  │    - Experience            │  │
│  │  │    - Projects              │  │
│  │  │    - Skills                │  │
│  │  │    - Education             │  │
│  │  │    - Contact               │  │
│  │  │                            │  │
│  └──┴────────────────────────────┘  │
│                                      │
└──────────────────────────────────────┘
```

### Component Hierarchy
```
App Layout
└── Page
    ├── InteractiveBackground
    └── MacWindow
        ├── Header (sticky)
        └── Content
            ├── Hero
            ├── Experience
            ├── Education
            ├── Skills
            ├── Projects
            └── Contact
```

---

## Key Features

1. **macOS Window Aesthetic**
   - Traffic light buttons with hover effects
   - Rounded corners and shadow effects
   - Fullscreen functionality

2. **Smooth Scrolling**
   - Scroll within the window frame
   - Scroll-based header effects
   - Custom scrollbar styling

3. **Responsive Design**
   - Mobile-first approach with Tailwind
   - Breakpoint-based layouts
   - Adaptive typography

4. **Interactive Elements**
   - Animated background
   - Hover effects on links and buttons
   - Smooth transitions

5. **Performance Optimized**
   - Next.js image optimization
   - Code splitting
   - Vercel Speed Insights integration
   - Turbopack for fast development

---

## Deployment

This project is optimized for deployment on **Vercel**:
- Push to Git repository
- Import project to Vercel
- Automatic builds and deployments
- Speed Insights enabled by default

---

## Getting Started

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager

### Installation
```bash
# Navigate to the app directory
cd portfolio-app

# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
npm start
```

### Development Workflow
1. Edit components in `components/` directory
2. Update page composition in `app/page.tsx`
3. Modify global styles in `app/globals.css`
4. Test changes in browser with hot reload
5. Run `npm run lint` to check for issues
6. Build and deploy when ready

---

## Notes

- This is version **0.2** of the portfolio application
- The project uses the **Ecru and Platinum** color palette (reference image included)
- All components are client-side rendered using `'use client'` directive where needed
- The application is a submodule or nested Git repository (see git status)

---

## Future Enhancements

- Add more interactive animations
- Implement dark/light mode toggle
- Add blog section
- Include testimonials section
- Implement project filtering
- Add loading states and transitions

