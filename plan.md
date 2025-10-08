# Mac-Style Portfolio Application

## Project Structure

1. Initialize Next.js 14+ with TypeScript and Tailwind CSS
2. Create App Router structure with main page at `app/page.tsx`
3. Build reusable components in `components/` directory

## Implementation Steps

### 1. Project Setup

- Initialize Next.js project with TypeScript: `npx create-next-app@latest`
- Configure Tailwind CSS (should be auto-configured)
- Clean up default boilerplate files

### 2. Global Styles (`app/globals.css`)

- Set body background with placeholder for moving background
- Remove default scrollbars using CSS (`overflow: hidden` on html/body)
- Add smooth scrolling behavior

### 3. Mac Window Component (`components/MacWindow.tsx`)

- Create container with max-w-6xl, h-[90vh], centered with flexbox
- Style: bg-gray-900, rounded-xl, shadow-2xl
- **Title Bar**: bg-gray-800 with traffic light buttons
- Red button (close): decorative with 'x' icon on hover
- Yellow button (minimize): decorative with '-' icon on hover
- Green button (maximize): triggers fullscreen API
- **Content Area**: flex-grow, overflow-y-auto for scrolling

### 4. Header Component (`components/Header.tsx`)

- Sticky positioning with scroll-based transparency
- Use React state to detect scroll within content area
- Layout: Name (left), Nav links (center), Resume button (right)
- Transparent → bg-gray-800/90 backdrop-blur on scroll
- Navigation links: About, Experience, Projects, Contact

### 5. Hero Section (`components/Hero.tsx`)

- Full viewport height within window content area
- Centered content with flexbox
- Placeholder name (e.g., "John Doe")
- Placeholder title (e.g., "Full Stack Developer")
- Brief bio paragraph
- Social media icons (GitHub, LinkedIn, Email) with hover effects

### 6. Content Sections

Create placeholder sections in `components/`:

- **About.tsx**: Brief about section with placeholder text
- **Experience.tsx**: Timeline or card-based experience section
- **Projects.tsx**: Grid of project cards
- **Contact.tsx**: Simple contact form or links

### 7. Main Page (`app/page.tsx`)

- Import and compose all components
- MacWindow wraps Header and all content sections
- Ensure proper scroll behavior within window

## Key Technical Details

- Use `'use client'` directive for components with interactivity
- Implement scroll detection with `useEffect` and `addEventListener`
- Traffic light hover effects using Tailwind group utilities
- Social icons: use lucide-react or heroicons library
- Background: placeholder gradient/color that can be replaced

## Files to Create

- `app/page.tsx` - Main page composition
- `app/globals.css` - Global styles and background
- `components/MacWindow.tsx` - Window frame with traffic lights
- `components/Header.tsx` - Sticky navigation header
- `components/Hero.tsx` - Hero section with intro
- `components/About.tsx` - About section placeholder
- `components/Experience.tsx` - Experience section placeholder
- `components/Projects.tsx` - Projects section placeholder
- `components/Contact.tsx` - Contact section placeholder