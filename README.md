# Sandlip Oasis, Frontend Engineering Handbook

> The definitive guide to building frontend applications at Sandlip Oasis.
> Authored by the Sandlip Oasis Engineering Team. Maintained as a living document.

---

## Table of Contents

- [About This Handbook](#about-this-handbook)
- [Sandlip Oasis Engineering Culture](#sandlip-oasis-engineering-culture)
- [Frontend Engineering Philosophy](#frontend-engineering-philosophy)
- [How to Use This Guide](#how-to-use-this-guide)
- [Developer Onboarding](#developer-onboarding)
- [Recommended Tooling and Environment](#recommended-tooling-and-environment)
- [Repository and Folder Structure](#repository-and-folder-structure)
- [Git and GitHub Workflow](#git-and-github-workflow)
- [HTML5](#html5)
- [CSS3](#css3)
- [JavaScript ES6+](#javascript-es6)
- [React.js](#reactjs)
- [Frontend Performance Optimization](#frontend-performance-optimization)
- [Security Best Practices](#security-best-practices)
- [Testing](#testing)
- [Debugging Workflows](#debugging-workflows)
- [Deployment](#deployment)
- [Coding Standards and Conventions](#coding-standards-and-conventions)
- [Common Mistakes and Anti-Patterns](#common-mistakes-and-anti-patterns)
- [Frontend Project Checklist](#frontend-project-checklist)
- [Recommended Libraries and Ecosystem](#recommended-libraries-and-ecosystem)
- [Developer Roadmaps](#developer-roadmaps)
- [Interview Preparation](#interview-preparation)
- [Learning Resources](#learning-resources)
- [Contribution Guidelines](#contribution-guidelines)

---

## About This Handbook

This handbook is the single source of truth for frontend engineering at Sandlip Oasis. It covers how we write, review, test, and ship UI code — from a developer's first day to their most advanced system design decisions.

This is not just a tutorial. It is a living engineering standard built from real-world practice and shaped by lessons the team has earned over time.

| Audience | What You Will Find |
|---|---|
| New joiners | Onboarding steps, tooling setup, team culture |
| Junior engineers | Fundamentals, guided code examples, learning paths |
| Mid-level engineers | Architecture patterns, best practices, advanced React |
| Senior engineers | Performance, security, scalability, contribution guidelines |

---

## Sandlip Oasis Engineering Culture

At Sandlip Oasis, engineering is a craft. We believe the best software is built at the intersection of technical rigor, empathy for users, and pride in what we ship.

Our culture is defined by five values:

```
1. Clarity        — Write code that teaches itself
2. Ownership      — Own your work from start to finish
3. Collaboration  — Great software is a team effort
4. Iteration      — Ship, learn, improve, repeat
5. Inclusivity    — Build for every user
```

We do not optimize for speed at the cost of quality. We write code for the engineer who comes after us, because that engineer is often ourselves six months later.

---

## Frontend Engineering Philosophy

> "The UI is the product. Everything else is infrastructure."

### Core Principles

**Semantic First**

HTML communicates meaning to browsers, assistive technologies, and search engines. Every element you choose is a statement. Avoid div soup — it is technical debt.

**Progressive Enhancement**

Build a solid, functional baseline in HTML. Enhance it with CSS. Enrich it with JavaScript. Never build a wall for any user.

**Performance is a Feature**

A slow page is a broken experience. Performance is not a post-launch concern — it is an engineering discipline embedded from the first line of code.

**Accessibility is Non-Negotiable**

Building accessibly is not a bonus. It is engineering excellence. Every interactive element must work with a keyboard. Every image must have meaningful alt text. Every color contrast must meet WCAG standards.

**Components are Contracts**

A component makes a promise: given these props, I will produce this UI. That contract must be consistent, documented, and testable.

**State is the Source of Truth**

UI is a function of state. When the UI behaves unexpectedly, the answer lives in state — not in a CSS patch.

---

## How to Use This Guide

This guide is organized in a progressive learning sequence. You do not need to read it front to back on day one. Use it as a reference, a curriculum, and a team standard.

```
New to the team?           Start with the Developer Onboarding section
Learning HTML, CSS, JS?    Work through sections in order
Building in React?         Jump to the React.js section
Shipping to production?    Review the Checklist and Security sections
Reviewing a pull request?  Reference Coding Standards and Anti-Patterns
Preparing for interviews?  See the Interview Preparation section
```

Tip: Bookmark this file. Reference it before opening a Stack Overflow tab.

---

## Developer Onboarding

### Week One Checklist

```
Day 1
  - Set up your development environment (see Tooling section)
  - Clone the main frontend repository
  - Run the project locally
  - Read through this handbook
  - Meet your team lead and onboarding buddy

Day 2 to 3
  - Complete your first "good first issue" task
  - Submit your first pull request
  - Attend a code review session as an observer
  - Familiarize yourself with the CI/CD pipeline

Day 4 to 5
  - Deep-read the sections most relevant to your current task
  - Set up your VS Code extensions (see Tooling section below)
  - Review two or three recently merged pull requests to learn team conventions
  - Introduce yourself in the #frontend Slack channel
```

### Environment Setup

```bash
# 1. Install Node.js via nvm (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts
nvm use --lts

# 2. Install the package manager we use at Sandlip Oasis
npm install -g pnpm

# 3. Clone the project
git clone https://github.com/sandlip-oasis/<project-name>.git
cd <project-name>

# 4. Install dependencies
pnpm install

# 5. Start the development server
pnpm dev
```

Warning: Always use the Node.js version specified in `.nvmrc` or `package.json > engines`. Version mismatches cause silent, hard-to-debug failures.

---

## Recommended Tooling and Environment

### VS Code Extensions

| Extension | Purpose | Priority |
|---|---|---|
| ESLint | Live linting and error highlighting | Required |
| Prettier | Automatic code formatting | Required |
| GitLens | Enhanced Git history and blame | Required |
| ES7+ React Snippets | React and JSX code snippets | Required |
| Auto Rename Tag | Syncs opening and closing HTML tags | Recommended |
| Path Intellisense | File path autocomplete | Recommended |
| Error Lens | Shows error messages inline | Recommended |
| Import Cost | Shows bundle size of imports | Recommended |
| Code Spell Checker | Catches typos in comments and strings | Recommended |
| Thunder Client | Lightweight REST client inside VS Code | Recommended |
| Tailwind CSS IntelliSense | Autocomplete for Tailwind classes | If using Tailwind |

### Shared VS Code Settings

Add this to `.vscode/settings.json` at the root of the project so all team members share the same editor behavior:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.tabSize": 2,
  "editor.rulers": [80, 120],
  "files.trimTrailingWhitespace": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

### Node.js Toolchain

| Tool | Purpose |
|---|---|
| pnpm | Package manager — faster and more disk-efficient than npm |
| Vite | Build tool and development server |
| ESLint | Static code analysis |
| Prettier | Code formatter |
| Husky | Runs scripts before Git commits |
| lint-staged | Runs linters only on staged files |
| commitlint | Enforces consistent commit message format |

---

## Repository and Folder Structure

### Project Structure

```
my-app/
├── .github/
│   ├── workflows/
│   │   ├── ci.yml
│   │   └── deploy.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── ISSUE_TEMPLATE/
├── .husky/
├── .vscode/
├── public/
├── src/
│   ├── assets/
│   │   ├── images/
│   │   └── fonts/
│   ├── components/
│   │   ├── ui/              # Reusable primitives: Button, Input, Modal
│   │   ├── layout/          # Header, Footer, Sidebar, PageWrapper
│   │   └── features/        # Feature-specific components
│   │       ├── auth/
│   │       ├── dashboard/
│   │       └── settings/
│   ├── hooks/               # Custom React hooks
│   ├── pages/               # Route-level page components
│   ├── services/            # API call functions
│   ├── store/               # State management
│   ├── styles/
│   │   ├── globals.css
│   │   ├── variables.css
│   │   └── themes/
│   ├── utils/               # Pure helper functions
│   ├── types/               # TypeScript types and interfaces
│   ├── constants/           # App-wide constants
│   ├── config/              # Environment config and feature flags
│   ├── App.jsx
│   └── main.jsx
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── .env.example
├── .eslintrc.js
├── .prettierrc
├── .nvmrc
├── vite.config.js
├── package.json
└── README.md
```

### Component Folder Pattern

Each component lives in its own folder so that related files stay together:

```
src/components/ui/Button/
├── Button.jsx           # Component logic
├── Button.module.css    # Scoped styles
├── Button.test.jsx      # Unit tests
├── Button.stories.jsx   # Storybook stories (if applicable)
└── index.js             # Clean re-export
```

```js
// src/components/ui/Button/index.js
export { default } from './Button';
```

Keeping tests and styles next to the component reduces navigation overhead and makes components easy to move or share across projects.

---

## Git and GitHub Workflow

### Branching Strategy

We follow GitHub Flow — a simple, trunk-based workflow:

```
main (protected)
  └── feature/[ticket-id]-short-description
  └── fix/[ticket-id]-short-description
  └── chore/update-dependencies
  └── docs/update-readme
```

Branch naming examples:

```
feature/SO-142-user-authentication
fix/SO-201-login-button-overflow
chore/upgrade-react-18
docs/add-api-integration-guide
refactor/SO-188-extract-auth-hook
```

### Commit Message Convention

We follow the Conventional Commits format:

```
<type>(<scope>): <short description>

[optional body]

[optional footer]
```

| Type | When to Use |
|---|---|
| feat | New feature |
| fix | Bug fix |
| docs | Documentation only |
| style | Formatting, no logic change |
| refactor | Code restructure, no behavior change |
| test | Adding or updating tests |
| chore | Build system or dependency updates |
| perf | Performance improvement |

Examples:

```bash
git commit -m "feat(auth): add JWT refresh token logic"
git commit -m "fix(button): resolve focus ring not showing in Safari"
git commit -m "perf(images): implement lazy loading on product grid"
git commit -m "docs(readme): update onboarding section for new toolchain"
```

### Pull Request Guidelines

Use this template when opening a pull request:

```markdown
## Description
What does this PR do? Why?

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Refactor
- [ ] Documentation

## Testing
- [ ] Unit tests added or updated
- [ ] Tested in Chrome, Firefox, and Safari
- [ ] Tested on a mobile viewport

## Quality
- [ ] No console.log statements left in code
- [ ] No commented-out code blocks
- [ ] Accessibility considerations addressed

## Screenshots (if UI changed)
Before and after screenshots
```

Pull request rules:

- Every PR must be reviewed by at least one engineer before merging
- Keep PRs focused — aim for fewer than 400 lines changed
- Link to the relevant issue or ticket
- Resolve all review comments before merging
- Squash commits on merge to keep history clean

---

## HTML5

### What HTML Does

HTML is the structure of every web page. Browsers read HTML and build a Document Object Model (DOM) — a tree of elements that CSS styles and JavaScript controls.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="Page description for SEO" />
    <title>Page Title — Sandlip Oasis</title>
    <link rel="stylesheet" href="/styles/globals.css" />
  </head>
  <body>
    <!-- Page content goes here -->
    <script type="module" src="/main.js"></script>
  </body>
</html>
```

Always include the `lang` attribute on the `<html>` element. Screen readers use it to select the correct language voice.

### Semantic HTML

Semantic elements tell the browser — and people using assistive tools — what a piece of content means, not just how it looks.

| Element | Purpose |
|---|---|
| `<header>` | Introductory content for a page or section |
| `<nav>` | Primary navigation links |
| `<main>` | The dominant content of the page (use once per page) |
| `<article>` | Self-contained content such as a blog post |
| `<section>` | A thematic grouping of content |
| `<aside>` | Supplementary content such as a sidebar |
| `<footer>` | Footer for a page or section |
| `<figure>` and `<figcaption>` | An image paired with a caption |
| `<time>` | A date or time value |
| `<address>` | Contact information |

Using `<div>` for everything destroys meaning. Here is the difference:

```html
<!-- Bad: no meaning communicated to the browser or assistive tools -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
  </div>
</div>

<!-- Good: structure is clear to browsers, screen readers, and developers -->
<header>
  <nav aria-label="Primary navigation">
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h1>Article Title</h1>
    <p>Content here...</p>
  </article>
</main>

<footer>
  <p>&copy; 2025 Sandlip Oasis</p>
</footer>
```

### Heading Hierarchy

Use one `<h1>` per page. Never skip heading levels for visual purposes — use CSS for sizing instead.

```html
<!-- Correct -->
<h1>Main Page Title</h1>
  <h2>Major Section</h2>
    <h3>Subsection</h3>

<!-- Wrong: jumped from h1 to h4 -->
<h1>Title</h1>
<h4>Subtitle</h4>
```

### Forms and Validation

Forms are one of the most important and most broken parts of the web. Write them carefully.

```html
<form action="/submit" method="POST" novalidate>
  <fieldset>
    <legend>Account Details</legend>

    <div class="form-group">
      <label for="email">Email address</label>
      <input
        type="email"
        id="email"
        name="email"
        required
        autocomplete="email"
        aria-describedby="email-hint email-error"
        placeholder="you@example.com"
      />
      <span id="email-hint" class="hint">We will never share your email.</span>
      <span id="email-error" class="error" role="alert" hidden>
        Please enter a valid email address.
      </span>
    </div>

    <div class="form-group">
      <label for="password">Password</label>
      <input
        type="password"
        id="password"
        name="password"
        required
        minlength="8"
        autocomplete="new-password"
        aria-describedby="password-requirements"
      />
      <ul id="password-requirements">
        <li>At least 8 characters</li>
        <li>At least one number</li>
      </ul>
    </div>

    <button type="submit">Create Account</button>
  </fieldset>
</form>
```

Common input types and when to use them:

| Type | Use Case |
|---|---|
| text | General short text |
| email | Email addresses — triggers the email keyboard on mobile |
| password | Passwords — input is masked |
| tel | Phone numbers — triggers numeric keyboard on mobile |
| number | Numeric input |
| date | Date picker |
| search | Search fields |
| checkbox | A boolean toggle |
| radio | One choice from a group |
| file | File upload |

### Accessibility

Accessibility (a11y) means building products that every person can use, including people who use screen readers, keyboard-only navigation, or other assistive technology.

We target WCAG 2.1 Level AA compliance on all Sandlip Oasis products.

```html
<!-- Images: describe what the image shows -->
<img src="team-photo.jpg" alt="The Sandlip Oasis engineering team at the 2024 retreat" />

<!-- Decorative images: use an empty alt so screen readers skip them -->
<img src="decorative-wave.svg" alt="" role="presentation" />

<!-- Use button for actions, anchor for navigation -->
<button type="button" onclick="openModal()">Open Settings</button>
<a href="/dashboard">Go to Dashboard</a>

<!-- Skip navigation link: lets keyboard users jump past repeated navigation -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<!-- Expandable menus: use ARIA to communicate state -->
<button
  aria-expanded="false"
  aria-controls="dropdown-menu"
  id="menu-trigger"
>
  Menu
</button>
<ul id="dropdown-menu" role="menu" aria-labelledby="menu-trigger" hidden>
  <li role="menuitem"><a href="/profile">Profile</a></li>
  <li role="menuitem"><a href="/logout">Logout</a></li>
</ul>
```

Accessibility checklist:

```
- All images have meaningful alt text
- Color is not the only way information is communicated
- Text contrast ratio is at least 4.5:1
- All interactive elements are operable with a keyboard
- Focus is always visible and never removed
- Forms have properly associated labels
- Error messages describe the problem clearly
- Dynamic content updates are announced to screen readers
- The page has one h1 and a logical heading hierarchy
```

### HTML Best Practices

```html
<!-- Lazy load images that are below the visible area -->
<img src="hero.jpg" alt="Hero" loading="eager" />    <!-- Above the fold -->
<img src="team.jpg" alt="Team" loading="lazy" />     <!-- Below the fold -->

<!-- Preload fonts and critical images early -->
<link rel="preload" href="/fonts/brand.woff2" as="font" type="font/woff2" crossorigin />
<link rel="preconnect" href="https://api.sandlipoasis.com" />

<!-- Boolean attributes do not need a value -->
<input type="checkbox" checked />
<button disabled>Submit</button>
```

---

## CSS3

### The Box Model

Every element on a page is a box. That box has content, padding, a border, and a margin. Set `box-sizing: border-box` globally so that padding and borders are included in the element's declared width — this is the behavior most developers expect.

```css
*, *::before, *::after {
  box-sizing: border-box;
}

.card {
  width: 300px;    /* Total rendered width, including padding and border */
  padding: 16px;
  border: 2px solid;
  margin: 24px;    /* Outside the box — not included in width */
}
```

### The Cascade and Specificity

CSS rules can conflict. The browser resolves conflicts using specificity — a scoring system:

```
Inline styles        1,0,0,0   (style="")
ID selectors         0,1,0,0   (#id)
Class selectors      0,0,1,0   (.class, :hover)
Element selectors    0,0,0,1   (div, p, h1)
Universal selector   0,0,0,0   (*)
```

Higher specificity wins. Avoid overly specific selectors — they become hard to override without `!important`, which creates its own problems.

### CSS Variables

CSS variables (custom properties) make your design consistent and easy to update. Define them once, use them everywhere.

```css
:root {
  /* Colors */
  --color-primary: #1a73e8;
  --color-primary-dark: #1558b0;
  --color-danger: #dc2626;
  --color-success: #16a34a;

  /* Neutrals */
  --color-gray-50: #f9fafb;
  --color-gray-100: #f3f4f6;
  --color-gray-500: #6b7280;
  --color-gray-900: #111827;

  /* Semantic tokens — use these in components, not raw colors */
  --color-text-primary: var(--color-gray-900);
  --color-text-secondary: var(--color-gray-500);
  --color-bg-surface: #ffffff;
  --color-bg-page: var(--color-gray-50);

  /* Typography */
  --font-sans: 'Inter Variable', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  --font-size-2xl: 1.5rem;
  --font-size-4xl: 2.25rem;

  /* Spacing */
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-4: 1rem;
  --space-6: 1.5rem;
  --space-8: 2rem;
  --space-12: 3rem;

  /* Border radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);

  /* Transitions */
  --transition-fast: 150ms ease;
  --transition-base: 250ms ease;
}

/* Dark mode: override only the semantic tokens */
@media (prefers-color-scheme: dark) {
  :root {
    --color-text-primary: var(--color-gray-50);
    --color-text-secondary: #9ca3af;
    --color-bg-surface: #1f2937;
    --color-bg-page: #111827;
  }
}
```

### Layouts: Flexbox and Grid

**Flexbox** is for one-dimensional layouts — a row or a column.

```css
/* Center something horizontally and vertically */
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Navigation bar with logo on the left, links on the right */
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: var(--space-4);
}

/* Sidebar and main content side by side */
.page-layout {
  display: flex;
  gap: var(--space-8);
}

.sidebar {
  flex: 0 0 280px;   /* Does not grow, does not shrink, always 280px */
}

.content {
  flex: 1;           /* Takes the remaining space */
  min-width: 0;      /* Prevents content overflow — always include this */
}
```

**CSS Grid** is for two-dimensional layouts — rows and columns at the same time.

```css
/* A card grid that wraps automatically — no media queries needed */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: var(--space-6);
}

/* Full page layout with named areas */
.app-shell {
  display: grid;
  grid-template-areas:
    "header  header"
    "sidebar main  "
    "footer  footer";
  grid-template-columns: 280px 1fr;
  grid-template-rows: 64px 1fr 48px;
  min-height: 100vh;
}

.app-header  { grid-area: header; }
.app-sidebar { grid-area: sidebar; }
.app-main    { grid-area: main; }
.app-footer  { grid-area: footer; }
```

### Responsive Design

We use a mobile-first approach. Write base styles for small screens, then add `min-width` media queries to adapt for larger screens.

```css
/* Base styles apply to all screen sizes */
.card {
  padding: var(--space-4);
}

/* Tablet and up */
@media (min-width: 768px) {
  .card {
    padding: var(--space-6);
  }
}

/* Desktop and up */
@media (min-width: 1024px) {
  .card {
    padding: var(--space-8);
  }
}

/* Fluid typography: scales smoothly between a minimum and maximum size */
h1 {
  font-size: clamp(1.75rem, 4vw + 1rem, 3.5rem);
}

/* Images should never overflow their container */
img, video {
  max-width: 100%;
  height: auto;
  display: block;
}
```

### Animations and Transitions

```css
/* Transitions: smooth state changes on hover or focus */
.button {
  background-color: var(--color-primary);
  transition: background-color var(--transition-fast),
              transform var(--transition-fast);
}

.button:hover {
  background-color: var(--color-primary-dark);
  transform: translateY(-1px);
}

.button:active {
  transform: translateY(0);
}

/* Keyframe animations */
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-in {
  animation: fade-in 300ms ease forwards;
}

/* Always respect the user's motion preferences */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### CSS Architecture (BEM Naming)

We use BEM (Block Element Modifier) for naming CSS classes. It makes stylesheets predictable and avoids naming collisions.

```css
/* Block: the component itself */
.card { }

/* Element: a part of the block, connected with double underscore */
.card__header { }
.card__body { }
.card__title { }
.card__footer { }

/* Modifier: a variation, connected with double dash */
.card--featured { }
.card--compact { }
.card__title--large { }
```

```html
<div class="card card--featured">
  <div class="card__header">
    <h2 class="card__title card__title--large">Featured Post</h2>
  </div>
  <div class="card__body">
    <p>Content here...</p>
  </div>
</div>
```

For React projects, we use CSS Modules to scope styles to a single component:

```css
/* Button.module.css */
.button {
  padding: var(--space-2) var(--space-4);
  border-radius: var(--radius-md);
  font-weight: 500;
  cursor: pointer;
  transition: all var(--transition-fast);
}

.primary {
  background: var(--color-primary);
  color: white;
}

.secondary {
  background: transparent;
  border: 1px solid var(--color-primary);
  color: var(--color-primary);
}
```

```jsx
import styles from './Button.module.css';

function Button({ variant = 'primary', children }) {
  return (
    <button className={`${styles.button} ${styles[variant]}`}>
      {children}
    </button>
  );
}
```

### CSS Best Practices

```css
/* Use variables instead of magic numbers */

/* Bad */
.header { height: 64px; }

/* Good */
:root { --header-height: 64px; }
.header { height: var(--header-height); }

/* Use gap for spacing inside flex and grid containers */
.button-group {
  display: flex;
  gap: var(--space-3);   /* Not margin-right on individual children */
}

/* Maintain consistent aspect ratios for media elements */
.video-container {
  aspect-ratio: 16 / 9;
  width: 100%;
}

/* Use :is() for cleaner grouped selectors */
:is(h1, h2, h3, h4, h5, h6) {
  font-weight: 600;
  line-height: 1.25;
}
```

---

## JavaScript ES6+

### Variables

Always use `const` by default. Use `let` when you need to reassign a value. Never use `var`.

```js
const API_BASE = 'https://api.sandlipoasis.com';  // Will never change
let retryCount = 0;                                // Will be incremented later
```

### Equality

Always use strict equality (`===`). The loose equality operator (`==`) performs type coercion and produces surprising results.

```js
// Loose equality — avoid
0 == false         // true
'' == false        // true
null == undefined  // true

// Strict equality — always use this
0 === false        // false
'' === false       // false
```

### Destructuring

Destructuring lets you unpack values from objects or arrays into named variables.

```js
// Object destructuring
const user = { name: 'Amara', role: 'engineer', team: 'frontend' };
const { name, role } = user;
const { name: userName } = user;         // Rename the variable
const { team = 'unknown' } = user;       // Use a default value

// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];

// In function parameters (common in React)
function UserCard({ name, role, avatarUrl = '/default-avatar.png' }) {
  return <div>{name} — {role}</div>;
}
```

### Spread and Rest

```js
// Spread: expand an object or array into another
const defaults = { theme: 'light', lang: 'en', fontSize: 16 };
const userPrefs = { theme: 'dark' };
const config = { ...defaults, ...userPrefs };
// Result: { theme: 'dark', lang: 'en', fontSize: 16 }

// Spread arrays
const allUsers = [...adminUsers, ...regularUsers];

// Rest: collect remaining arguments into an array
function log(level, ...messages) {
  console[level](messages.join(' '));
}
log('info', 'User', 'logged', 'in');
```

### Template Literals

```js
const name = 'Amara';
const role = 'Senior Engineer';

const greeting = `Welcome back, ${name}. You are logged in as ${role}.`;

// Multi-line strings
const emailBody = `
  Dear ${name},

  Your account has been updated.

  The Sandlip Oasis Team
`.trim();
```

### Arrow Functions

```js
const double = x => x * 2;
const add = (a, b) => a + b;
const getUser = (id) => ({ id, name: 'Amara' });  // Wrap object literal in ()

// Arrow functions do not have their own `this`
// This makes them ideal for class methods and callbacks
class Timer {
  constructor() {
    this.seconds = 0;
  }

  start() {
    // `this` correctly refers to the Timer instance
    setInterval(() => {
      this.seconds++;
    }, 1000);
  }
}
```

### Optional Chaining and Nullish Coalescing

These two operators prevent most null reference errors.

```js
// Optional chaining: safely access nested properties
const user = null;
const city = user?.address?.city;     // undefined, not a TypeError
const firstTag = user?.tags?.[0];     // Safe array access
const name = user?.getName?.();       // Safe method call

// Nullish coalescing: use a fallback only for null or undefined
const displayName = user?.name ?? 'Anonymous';

// The key difference from ||
const count = 0 || 'default';    // 'default' because 0 is falsy
const count2 = 0 ?? 'default';   // 0 because 0 is not null or undefined
```

### Array Methods

These are the most used tools in JavaScript for working with lists of data.

```js
const engineers = [
  { name: 'Amara', role: 'frontend', level: 'senior', active: true },
  { name: 'Kofi',  role: 'backend',  level: 'mid',    active: true },
  { name: 'Zara',  role: 'frontend', level: 'junior', active: false },
  { name: 'Jide',  role: 'frontend', level: 'mid',    active: true },
];

// filter: keep items that match a condition
const frontendEngineers = engineers.filter(e => e.role === 'frontend');

// map: transform every item into something new
const names = engineers.map(e => e.name);
// ['Amara', 'Kofi', 'Zara', 'Jide']

// find: return the first item that matches
const senior = engineers.find(e => e.level === 'senior');

// some: returns true if at least one item matches
const hasJunior = engineers.some(e => e.level === 'junior');  // true

// every: returns true only if all items match
const allActive = engineers.every(e => e.active);  // false

// reduce: accumulate a single value from the whole array
const activeCount = engineers.reduce((count, e) => count + (e.active ? 1 : 0), 0);

// Chain methods together for expressive transformations
const activeFrontendNames = engineers
  .filter(e => e.role === 'frontend' && e.active)
  .map(e => e.name)
  .sort();
```

### Asynchronous JavaScript

JavaScript runs one operation at a time. Async code lets the program start a long operation, move on, and come back when the result is ready.

**Promises:**

```js
function fetchUser(id) {
  return new Promise((resolve, reject) => {
    if (!id) {
      reject(new Error('User ID is required'));
      return;
    }
    setTimeout(() => resolve({ id, name: 'Amara' }), 1000);
  });
}

fetchUser(1)
  .then(user => enrichUserData(user))
  .then(enriched => updateUI(enriched))
  .catch(error => handleError(error))
  .finally(() => hideLoadingSpinner());
```

**Async/Await** makes async code read like regular synchronous code:

```js
async function loadDashboard(userId) {
  try {
    const user = await fetchUser(userId);

    // Start both requests at the same time rather than waiting for each sequentially
    const [posts, notifications] = await Promise.all([
      fetchPosts(userId),
      fetchNotifications(userId),
    ]);

    return { user, posts, notifications };
  } catch (error) {
    if (error.status === 401) {
      redirectToLogin();
    } else {
      throw new Error(`Failed to load dashboard: ${error.message}`);
    }
  }
}
```

### A Reusable API Client

Instead of writing fetch calls scattered throughout your app, centralize them in one place:

```js
const apiClient = {
  baseURL: import.meta.env.VITE_API_BASE_URL,

  async request(endpoint, options = {}) {
    const token = localStorage.getItem('auth_token');

    const response = await fetch(`${this.baseURL}${endpoint}`, {
      headers: {
        'Content-Type': 'application/json',
        ...(token && { Authorization: `Bearer ${token}` }),
        ...options.headers,
      },
      ...options,
    });

    if (!response.ok) {
      const error = await response.json().catch(() => ({}));
      throw Object.assign(new Error(error.message ?? response.statusText), {
        status: response.status,
        data: error,
      });
    }

    if (response.status === 204) return null;
    return response.json();
  },

  get: (endpoint) =>
    apiClient.request(endpoint, { method: 'GET' }),

  post: (endpoint, body) =>
    apiClient.request(endpoint, { method: 'POST', body: JSON.stringify(body) }),

  put: (endpoint, body) =>
    apiClient.request(endpoint, { method: 'PUT', body: JSON.stringify(body) }),

  delete: (endpoint) =>
    apiClient.request(endpoint, { method: 'DELETE' }),
};

// Usage
const user = await apiClient.get('/users/1');
const newPost = await apiClient.post('/posts', { title: 'Hello', body: 'World' });
```

### Error Handling

```js
// Create specific error classes so you can handle errors by type
class APIError extends Error {
  constructor(message, status, data) {
    super(message);
    this.name = 'APIError';
    this.status = status;
    this.data = data;
  }
}

class ValidationError extends Error {
  constructor(message, fields) {
    super(message);
    this.name = 'ValidationError';
    this.fields = fields;
  }
}

function handleError(error) {
  if (error instanceof ValidationError) {
    showFormErrors(error.fields);
  } else if (error instanceof APIError) {
    if (error.status === 401) redirectToLogin();
    else if (error.status === 403) showPermissionDenied();
    else if (error.status >= 500) showServerError();
    else showToast(error.message, 'error');
  } else {
    console.error('Unexpected error:', error);
    showToast('Something went wrong. Please try again.', 'error');
  }
}
```

### JavaScript Best Practices

```js
// Write pure functions: same input always gives the same output, no side effects
const calculateTotal = (items) =>
  items.reduce((sum, item) => sum + item.price * item.quantity, 0);

// Use guard clauses to avoid deeply nested if statements
function processUser(user) {
  if (!user) throw new Error('User is required');
  if (!user.isActive) return null;
  if (!user.hasPermission) throw new PermissionError();

  // Main logic is clean and easy to read
  return transformUser(user);
}

// Return new data instead of mutating arguments

// Bad
function addItem(cart, item) {
  cart.items.push(item);  // Modifies the original
  return cart;
}

// Good
function addItem(cart, item) {
  return {
    ...cart,
    items: [...cart.items, item],
    total: cart.total + item.price,
  };
}

// Debounce operations that fire frequently, like search inputs
function debounce(fn, delay) {
  let timeoutId;
  return (...args) => {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn(...args), delay);
  };
}

const handleSearch = debounce(async (query) => {
  const results = await searchAPI(query);
  renderResults(results);
}, 300);
```

---

## React.js

React renders a UI as a function of state: `UI = f(state)`. Master this mental model before everything else. When the UI behaves unexpectedly, the first question is always: what does state contain right now?

### JSX

JSX is a syntax extension that lets you write HTML-like code inside JavaScript files.

```jsx
// JSX rules:
// 1. Return a single root element, or use a Fragment: <>...</>
// 2. Use className, not class
// 3. Use htmlFor, not for (on label elements)
// 4. All tags must be closed, including self-closing: <img />, <br />
// 5. JavaScript expressions go inside curly braces {}

function UserCard({ user }) {
  return (
    <>
      <h2>{user.name}</h2>
      {user.isPremium && <span className="badge">Premium</span>}
      {user.role === 'admin' ? <AdminPanel /> : <UserPanel />}
    </>
  );
}
```

### useState — Local Component State

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  // Use a function update when the new state depends on the previous value
  const increment = () => setCount(prev => prev + 1);
  const decrement = () => setCount(prev => prev - 1);

  return (
    <div>
      <button onClick={decrement}>-</button>
      <span>{count}</span>
      <button onClick={increment}>+</button>
    </div>
  );
}

// Object state: always spread to avoid overwriting other fields
function ProfileForm() {
  const [form, setForm] = useState({ name: '', email: '', bio: '' });

  const handleChange = (e) => {
    const { name, value } = e.target;
    setForm(prev => ({ ...prev, [name]: value }));
  };

  return (
    <form>
      <input name="name" value={form.name} onChange={handleChange} />
      <input name="email" value={form.email} onChange={handleChange} />
      <textarea name="bio" value={form.bio} onChange={handleChange} />
    </form>
  );
}
```

### useEffect — Side Effects

Use `useEffect` for things that happen outside of rendering: fetching data, setting up subscriptions, or touching the DOM directly.

```jsx
import { useState, useEffect } from 'react';

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;

    async function fetchUser() {
      try {
        setLoading(true);
        setError(null);
        const data = await apiClient.get(`/users/${userId}`);
        if (!cancelled) setUser(data);
      } catch (err) {
        if (!cancelled) setError(err.message);
      } finally {
        if (!cancelled) setLoading(false);
      }
    }

    fetchUser();

    // Cleanup: runs when userId changes or the component is removed
    return () => {
      cancelled = true;
    };
  }, [userId]);  // Re-runs whenever userId changes

  if (loading) return <Skeleton />;
  if (error) return <ErrorMessage message={error} />;
  if (!user) return null;

  return <div>{user.name}</div>;
}
```

Dependency array quick reference:

```js
useEffect(() => { ... });          // Runs after every render — rarely what you want
useEffect(() => { ... }, []);      // Runs once after the component mounts
useEffect(() => { ... }, [id]);    // Runs after mount and whenever id changes
```

### useCallback and useMemo — Memoization

These hooks prevent unnecessary recalculations and re-renders. Use them when you have measured a performance problem, not as a default habit.

```jsx
import { useMemo, useCallback } from 'react';

function ProductList({ products, onSelect }) {
  // useMemo: the sorted result is only recalculated when products changes
  const sortedProducts = useMemo(
    () => [...products].sort((a, b) => a.name.localeCompare(b.name)),
    [products]
  );

  // useCallback: gives onSelect a stable reference
  // Without this, a new function is created on every render,
  // causing memoized children to re-render unnecessarily
  const handleSelect = useCallback((id) => {
    onSelect(id);
  }, [onSelect]);

  return (
    <ul>
      {sortedProducts.map(p => (
        <ProductItem key={p.id} product={p} onSelect={handleSelect} />
      ))}
    </ul>
  );
}
```

### useRef — DOM References and Mutable Values

```jsx
import { useRef, useEffect } from 'react';

// Accessing a DOM element directly
function SearchInput() {
  const inputRef = useRef(null);

  useEffect(() => {
    inputRef.current?.focus();
  }, []);

  return <input ref={inputRef} placeholder="Search..." />;
}

// Storing a mutable value without triggering a re-render
function Timer() {
  const intervalRef = useRef(null);

  const start = () => {
    intervalRef.current = setInterval(() => console.log('tick'), 1000);
  };

  const stop = () => clearInterval(intervalRef.current);

  useEffect(() => () => clearInterval(intervalRef.current), []);

  return (
    <div>
      <button onClick={start}>Start</button>
      <button onClick={stop}>Stop</button>
    </div>
  );
}
```

### Custom Hooks

Custom hooks let you extract and reuse stateful logic between components. Any function that starts with `use` and calls other hooks is a custom hook.

```jsx
// useDebounce: delays updating a value until the user stops typing
function useDebounce(value, delay = 300) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => setDebouncedValue(value), delay);
    return () => clearTimeout(timer);
  }, [value, delay]);

  return debouncedValue;
}

// useLocalStorage: persists state to the browser's localStorage
function useLocalStorage(key, initialValue) {
  const [storedValue, setStoredValue] = useState(() => {
    try {
      const item = window.localStorage.getItem(key);
      return item ? JSON.parse(item) : initialValue;
    } catch {
      return initialValue;
    }
  });

  const setValue = (value) => {
    try {
      const valueToStore = value instanceof Function ? value(storedValue) : value;
      setStoredValue(valueToStore);
      window.localStorage.setItem(key, JSON.stringify(valueToStore));
    } catch (error) {
      console.error(error);
    }
  };

  return [storedValue, setValue];
}

// Usage
function SearchPage() {
  const [query, setQuery] = useState('');
  const debouncedQuery = useDebounce(query, 400);

  useEffect(() => {
    if (debouncedQuery) fetchResults(debouncedQuery);
  }, [debouncedQuery]);

  return <input value={query} onChange={e => setQuery(e.target.value)} />;
}
```

### Component Architecture

Think about components in three layers:

```
UI Components (Presentational)
  Receive props and render UI. No API calls. No business logic.
  Reusable by design.
  Examples: Button, Card, Modal, Badge, Avatar.

Feature Components
  Own state and side effects. Fetch data and handle interactions.
  Compose UI components together.
  Examples: UserProfileCard, LoginForm, SearchResults.

Page Components
  Route-level components. Orchestrate feature components.
  Handle URL parameters and routing logic.
  Examples: DashboardPage, SettingsPage, UserProfilePage.
```

### State Management

Choose the simplest tool that solves the problem:

```
Local useState         One component's private data
Lifted state           Shared between siblings via a common parent
React Context          Global UI state: theme, auth, locale
Zustand or Jotai       Client state with actions, minimal boilerplate
Redux Toolkit          Large apps with complex, interconnected state
React Query or SWR     Server state: caching, background refetching, loading states
```

**React Context for global state:**

```jsx
const AuthContext = createContext(null);

export function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    authService.getSession().then((user) => {
      setUser(user);
      setLoading(false);
    });
  }, []);

  const login = async (credentials) => {
    const user = await authService.login(credentials);
    setUser(user);
  };

  const logout = async () => {
    await authService.logout();
    setUser(null);
  };

  if (loading) return <AppLoadingScreen />;

  return (
    <AuthContext.Provider value={{ user, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
}

export function useAuth() {
  const context = useContext(AuthContext);
  if (!context) throw new Error('useAuth must be used inside AuthProvider');
  return context;
}
```

**Zustand for client state:**

```jsx
import { create } from 'zustand';

const useCartStore = create((set, get) => ({
  items: [],

  addItem: (product) => set((state) => ({
    items: [...state.items, { ...product, quantity: 1 }],
  })),

  removeItem: (productId) => set((state) => ({
    items: state.items.filter(item => item.id !== productId),
  })),

  clearCart: () => set({ items: [] }),

  get totalItems() {
    return get().items.reduce((sum, i) => sum + i.quantity, 0);
  },
}));
```

**React Query for server state:**

```jsx
import { useQuery } from '@tanstack/react-query';

function UserProfile({ userId }) {
  const { data: user, isLoading, isError } = useQuery({
    queryKey: ['user', userId],
    queryFn: () => apiClient.get(`/users/${userId}`),
    staleTime: 5 * 60 * 1000,  // Data stays fresh for 5 minutes
  });

  if (isLoading) return <Skeleton />;
  if (isError) return <ErrorState />;

  return <div>{user.name}</div>;
}
```

### React Performance

```jsx
// React.memo: skip re-rendering a component when its props have not changed
const UserCard = React.memo(function UserCard({ user }) {
  return <div>{user.name}</div>;
});

// Code splitting: load heavy components only when the user navigates to them
import { lazy, Suspense } from 'react';

const AdminDashboard = lazy(() => import('./pages/AdminDashboard'));

function App() {
  return (
    <Suspense fallback={<PageSkeleton />}>
      <Routes>
        <Route path="/admin" element={<AdminDashboard />} />
      </Routes>
    </Suspense>
  );
}
```

### React Best Practices

```jsx
// Use stable IDs as keys, never array indexes
// Bad: causes incorrect behavior when the list is reordered or filtered
{items.map((item, index) => <Item key={index} {...item} />)}

// Good
{items.map(item => <Item key={item.id} {...item} />)}

// Derive values from state instead of duplicating state

const [items, setItems] = useState([]);
const count = items.length;                  // Derived — no separate useState needed
const activeItems = items.filter(i => i.active);  // Derived

// Handle all states clearly at the top of the component
function UserPage({ userId }) {
  const { data: user, isLoading, isError } = useUser(userId);

  if (isLoading) return <PageSkeleton />;
  if (isError)   return <ErrorPage />;
  if (!user)     return <NotFound />;

  return <UserDetail user={user} />;
}
```

---

## Frontend Performance Optimization

Performance is a feature. A slow application loses users regardless of how good it looks.

### Core Web Vitals Targets

| Metric | Target | What It Measures |
|---|---|---|
| LCP (Largest Contentful Paint) | Under 2.5 seconds | How quickly the main content appears |
| INP (Interaction to Next Paint) | Under 200ms | How quickly the page responds to input |
| CLS (Cumulative Layout Shift) | Under 0.1 | How much the layout shifts unexpectedly |

### Bundle Optimization

```js
// vite.config.js
import { defineConfig } from 'vite';

export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
          router: ['react-router-dom'],
          query: ['@tanstack/react-query'],
        },
      },
    },
  },
});
```

### Image Optimization

```html
<!-- Serve modern formats with a JPEG fallback for older browsers -->
<picture>
  <source srcset="hero.avif" type="image/avif" />
  <source srcset="hero.webp" type="image/webp" />
  <img src="hero.jpg" alt="Hero" width="1200" height="600" loading="eager" />
</picture>

<!-- Responsive images: load the right size for the screen -->
<img
  src="card.jpg"
  srcset="card-400.jpg 400w, card-800.jpg 800w, card-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, (max-width: 1200px) 50vw, 400px"
  alt="Product"
  loading="lazy"
  decoding="async"
/>
```

### Resource Hints

```html
<head>
  <!-- Pre-establish connection to the API domain -->
  <link rel="preconnect" href="https://api.sandlipoasis.com" />

  <!-- Preload a font file so it does not delay text rendering -->
  <link rel="preload" href="/fonts/brand.woff2" as="font" type="font/woff2" crossorigin />

  <!-- Prefetch the next page the user is likely to visit -->
  <link rel="prefetch" href="/dashboard" />
</head>
```

### CSS Performance

```css
/* Use transform and opacity for animations — they run on the GPU
   and do not trigger layout recalculations */

/* Bad: recalculates layout on every animation frame */
.element { transition: width 300ms; }

/* Good: composited on the GPU */
.element { transition: transform 300ms; }

/* Show text immediately with the fallback font,
   then swap to the loaded custom font */
@font-face {
  font-family: 'Brand';
  src: url('/fonts/brand.woff2') format('woff2');
  font-display: swap;
}
```

---

## Security Best Practices

### XSS Prevention

React's JSX automatically escapes content, so rendering user data in JSX is safe by default. The main danger zone is `dangerouslySetInnerHTML`.

```jsx
// Safe by default — React escapes this automatically
function Comment({ text }) {
  return <p>{text}</p>;
}

// Dangerous — always sanitize HTML before rendering it
import DOMPurify from 'dompurify';

function RichContent({ htmlContent }) {
  const clean = DOMPurify.sanitize(htmlContent, {
    ALLOWED_TAGS: ['b', 'i', 'em', 'strong', 'a', 'p', 'ul', 'li'],
    ALLOWED_ATTR: ['href'],
  });
  return <div dangerouslySetInnerHTML={{ __html: clean }} />;
}

// Validate URLs before using them in href attributes
function SafeLink({ url, children }) {
  const isSafe = /^https?:\/\//i.test(url) || url.startsWith('/');
  if (!isSafe) return <span>{children}</span>;
  return <a href={url}>{children}</a>;
}
```

### Secrets and Environment Variables

Never commit secrets, API keys, or credentials to source control.

```bash
# .env.example — commit this; it documents what variables the app needs
VITE_API_BASE_URL=https://api.sandlipoasis.com
VITE_APP_ENV=production

# .env.local — never commit this file; add it to .gitignore
VITE_API_BASE_URL=http://localhost:3001
```

### Security Checklist

```
- Sensitive data is never stored in plain text
- User-generated HTML is sanitized with DOMPurify before rendering
- External URLs are validated before being used in href or src
- API keys are stored in environment variables, never in source code
- Dependencies are audited regularly: pnpm audit
- No sensitive data is logged to the console in production builds
- HTTPS is enforced in all production environments
```

---

## Testing

### The Testing Pyramid

```
       E2E Tests (Playwright)
  ─────────────────────────────────
      Integration Tests
  ─────────────────────────────────────
         Unit Tests (Vitest + React Testing Library)
```

Write many fast unit tests, fewer integration tests, and a small number of E2E tests covering your most critical user journeys.

### Unit and Component Testing

```jsx
// Button.test.jsx
import { render, screen } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { describe, it, expect, vi } from 'vitest';
import Button from './Button';

describe('Button', () => {
  it('renders its label', () => {
    render(<Button>Click me</Button>);
    expect(screen.getByRole('button', { name: /click me/i })).toBeInTheDocument();
  });

  it('calls onClick when clicked', async () => {
    const user = userEvent.setup();
    const handleClick = vi.fn();

    render(<Button onClick={handleClick}>Submit</Button>);
    await user.click(screen.getByRole('button'));

    expect(handleClick).toHaveBeenCalledTimes(1);
  });

  it('is disabled when the disabled prop is set', () => {
    render(<Button disabled>Submit</Button>);
    expect(screen.getByRole('button')).toBeDisabled();
  });
});
```

Testing async components with MSW (Mock Service Worker):

```jsx
import { render, screen, waitFor } from '@testing-library/react';
import { rest } from 'msw';
import { setupServer } from 'msw/node';
import UserProfile from './UserProfile';

const server = setupServer(
  rest.get('/api/users/1', (req, res, ctx) =>
    res(ctx.json({ id: 1, name: 'Amara', role: 'Senior Engineer' }))
  )
);

beforeAll(() => server.listen());
afterEach(() => server.resetHandlers());
afterAll(() => server.close());

describe('UserProfile', () => {
  it('renders user data after fetching', async () => {
    render(<UserProfile userId={1} />);

    await waitFor(() => {
      expect(screen.getByText('Amara')).toBeInTheDocument();
    });
  });

  it('shows an error state when the API fails', async () => {
    server.use(
      rest.get('/api/users/1', (req, res, ctx) => res(ctx.status(500)))
    );
    render(<UserProfile userId={1} />);

    await waitFor(() => {
      expect(screen.getByRole('alert')).toBeInTheDocument();
    });
  });
});
```

### E2E Testing with Playwright

```js
// tests/e2e/auth.spec.js
import { test, expect } from '@playwright/test';

test('user can log in with valid credentials', async ({ page }) => {
  await page.goto('/login');

  await page.getByLabel('Email address').fill('amara@sandlipoasis.com');
  await page.getByLabel('Password').fill('securepassword');
  await page.getByRole('button', { name: /sign in/i }).click();

  await expect(page).toHaveURL('/dashboard');
  await expect(page.getByText('Welcome back, Amara')).toBeVisible();
});

test('shows an error for invalid credentials', async ({ page }) => {
  await page.goto('/login');

  await page.getByLabel('Email address').fill('wrong@example.com');
  await page.getByLabel('Password').fill('wrongpassword');
  await page.getByRole('button', { name: /sign in/i }).click();

  await expect(page.getByRole('alert')).toContainText('Invalid email or password');
});
```

### Coverage Targets

| Area | Target |
|---|---|
| Utility functions | 95% and above |
| UI components | 80% and above |
| Critical user flows | Covered by E2E tests |

---

## Debugging Workflows

### Browser DevTools Panels

**Elements panel** — Inspect and live-edit HTML and CSS. Test responsive layouts using device emulation. Check the Accessibility tab to audit the accessibility tree.

**Console panel:**

```js
console.table(arrayOfObjects)   // Renders array data as a readable table
console.group('Label')          // Group related log messages together
console.time('label')           // Start a performance timer
console.timeEnd('label')        // Stop the timer and print elapsed time
console.trace()                 // Print the current call stack
$0                              // Reference the last element clicked in Elements
```

**Network panel** — Filter by Fetch/XHR to see API calls. Throttle to simulate a slow connection. Right-click any request and choose "Copy as cURL" to reproduce it in a terminal.

**Performance panel** — Record an interaction and identify long tasks (anything over 50ms blocks the main thread). Find unnecessary layout recalculations and slow rendering.

**Application panel** — Inspect localStorage, sessionStorage, and cookies. Clear site data for a clean state.

### React Developer Tools

Install the React Developer Tools browser extension. It adds two panels:

- **Components** — Inspect props and state of any mounted component. Highlight updates to visualize what is re-rendering.
- **Profiler** — Record an interaction and see which components re-rendered, how long each took, and what caused the render.

### Before Asking for Help

```
1. Can you reproduce the bug consistently? What are the exact steps?
2. Check the browser console for error messages
3. Verify the data is what you expect — add a temporary log or use DevTools
4. Check the Network tab for failed or unexpected API responses
5. Read the error message in full — do not just scan the first line
6. Check git history — when did this code last change?
7. Try to isolate the problem — can you reproduce it in a smaller example?
```

---

## Deployment

### Environment Strategy

```
local         Your development machine (localhost)
development   Automatic preview deployments for each pull request
staging       Pre-production environment for QA and automated testing
production    Live user traffic, deployed automatically from main
```

### Environment Variables

```bash
# .env.example — commit this file to document all required variables
VITE_API_BASE_URL=https://api.sandlipoasis.com
VITE_APP_ENV=production
VITE_SENTRY_DSN=

# .env.local — never commit this file
VITE_API_BASE_URL=http://localhost:3001
```

Validate required variables at startup:

```js
// src/config/env.js
const required = ['VITE_API_BASE_URL'];

for (const name of required) {
  if (!import.meta.env[name]) {
    throw new Error(`Missing required environment variable: ${name}`);
  }
}

export const config = {
  apiBaseUrl: import.meta.env.VITE_API_BASE_URL,
  isDev: import.meta.env.DEV,
  isProd: import.meta.env.PROD,
};
```

### CI/CD Pipeline

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  quality:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pnpm/action-setup@v3
      - uses: actions/setup-node@v4
        with:
          node-version-file: '.nvmrc'
          cache: 'pnpm'

      - name: Install dependencies
        run: pnpm install --frozen-lockfile

      - name: Lint
        run: pnpm lint

      - name: Unit tests
        run: pnpm test --coverage

      - name: Build
        run: pnpm build

      - name: E2E tests
        run: pnpm playwright test
```

### Deployment Checklist

```
Before deploying
  - All tests passing in CI
  - Bundle size reviewed — no unexpected increases
  - Lighthouse audit run on staging (target: Performance 90+, Accessibility 100)
  - Environment variables set in the target environment

After deploying
  - Monitor error tracking (Sentry) for 30 minutes
  - Verify critical user journeys manually in production
  - Confirm analytics events are firing correctly
```

---

## Coding Standards and Conventions

### Naming Conventions

```js
// Variables and functions — camelCase
const userProfile = {};
function fetchUserData() {}

// React components — PascalCase
function UserProfileCard() {}

// Constants — SCREAMING_SNAKE_CASE
const MAX_RETRY_ATTEMPTS = 3;
const API_TIMEOUT_MS = 5000;

// CSS classes — kebab-case with BEM
// .user-card {}
// .user-card__header {}
// .user-card--featured {}

// Files:
//   Components — PascalCase:    UserProfileCard.jsx
//   Everything else — camelCase: apiClient.js, useAuthStore.js
```

### Code Style Rules

Be explicit, not clever. Code is read far more often than it is written. Optimizing for the reader is always the right investment.

```js
// Bad: clever but hard to understand
const map = arr.reduce((a, b) => ({...a, [b.id]: b}), {});

// Good: clear intent
const usersById = {};
for (const user of users) {
  usersById[user.id] = user;
}

// Use early returns to keep the happy path clean

// Bad: logic buried three levels deep
function processOrder(order) {
  if (order) {
    if (order.isValid) {
      if (order.items.length > 0) {
        // the actual work is here
      }
    }
  }
}

// Good: guard clauses at the top, clean logic at the bottom
function processOrder(order) {
  if (!order) throw new Error('Order is required');
  if (!order.isValid) throw new ValidationError('Invalid order');
  if (!order.items.length) throw new Error('Order has no items');

  // the actual work is easy to find and read
}
```

---

## Common Mistakes and Anti-Patterns

### HTML

```html
<!-- Bad: using a div as a button — not accessible by keyboard or screen reader -->
<div class="button" onclick="submit()">Submit</div>

<!-- Good: use the right element -->
<button type="submit">Submit</button>


<!-- Bad: input with no associated label -->
<input type="text" placeholder="Enter email" />

<!-- Good: label is associated via the for/id pair -->
<label for="email">Email</label>
<input type="text" id="email" placeholder="Enter email" />
```

### CSS

```css
/* Bad: using !important as a first resort */
.button { color: red !important; }

/* Bad: overly specific selectors that cannot be overridden */
div.page > ul.nav-list > li.nav-item > a.nav-link { }

/* Bad: magic number with no explanation */
.element { margin-top: 37px; }

/* Bad: hardcoded color instead of a variable */
.button { background: #1a73e8; }

/* Good */
.button { background: var(--color-primary); }
```

### JavaScript

```js
// Bad: mutating a function argument
function addUser(users, user) {
  users.push(user);  // Modifies the original array
  return users;
}

// Good: return new data
function addUser(users, user) {
  return [...users, user];
}

// Bad: swallowing errors silently
try {
  await doSomething();
} catch (e) {}  // Error disappears — you will never know what went wrong

// Bad: floating point comparison
0.1 + 0.2 === 0.3  // false in JavaScript

// Good
Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON  // true
```

### React

```jsx
// Bad: mutating state directly — React cannot detect the change
state.items.push(newItem);
setItems(state.items);

// Good: create a new array reference
setItems([...state.items, newItem]);


// Bad: storing derived data in its own useState — it will get out of sync
const [items, setItems] = useState([]);
const [count, setCount] = useState(0);  // This is just items.length

// Good: derive it
const [items, setItems] = useState([]);
const count = items.length;


// Bad: missing cleanup in useEffect — memory leak
useEffect(() => {
  const interval = setInterval(tick, 1000);
}, []);

// Good: always return a cleanup function
useEffect(() => {
  const interval = setInterval(tick, 1000);
  return () => clearInterval(interval);
}, []);


// Bad: passing a new object as a dependency — causes an infinite loop
useEffect(() => {
  fetchData(filters);
}, [{ page, userId }]);  // New object reference created on every render

// Good: use primitive values as dependencies
useEffect(() => {
  fetchData({ page, userId });
}, [page, userId]);
```

---

## Frontend Project Checklist

### Before Development Starts

```
- Requirements are clarified and documented
- Design mockups reviewed and design assets are available
- API contracts defined with the backend team
- Project folder structure set up per this guide
- Linting, formatting, and pre-commit hooks configured
- CI/CD pipeline established
- Environment variables documented in .env.example
```

### During Development

```
- Semantic HTML used throughout
- All interactive components work with keyboard navigation
- ARIA attributes added where native semantics are insufficient
- All interactive elements have a visible focus style
- Responsive on mobile, tablet, and desktop viewports
- Loading, error, and empty states handled for all data fetches
- Forms have validation and clear, descriptive error messages
- No console.log statements committed to the codebase
- No hardcoded colors or magic numbers — use CSS variables and constants
```

### Before Submitting a Pull Request

```
- Read your own diff before requesting a review
- Unit tests written for new logic
- All tests pass locally
- Linting passes with no errors
- Build succeeds
- Tested in Chrome, Firefox, and Safari
- Tested on a mobile viewport using DevTools device emulation
- Keyboard navigation tested on new interactive elements
```

### Before Launching

```
- Lighthouse audit: Performance 90 or above, Accessibility 100
- Core Web Vitals checked on real devices using PageSpeed Insights
- Error tracking connected and tested
- Favicon and Open Graph meta tags in place
- 404 page implemented
- robots.txt and sitemap.xml present
- All environment variables set in the production environment
```

---

## Recommended Libraries and Ecosystem

| Category | Library | Notes |
|---|---|---|
| Framework | React 18 | Concurrent rendering, transitions |
| Build tool | Vite | Fast development, modern bundling |
| Routing | React Router v6 | Nested routes, data loaders |
| Server state | TanStack Query v5 | Caching, background refetching |
| Client state | Zustand | Minimal boilerplate |
| Forms | React Hook Form | Performant, integrates with Zod |
| Validation | Zod | TypeScript-first schema validation |
| Styling | CSS Modules with CSS Variables | Scoped styles, no runtime cost |
| UI Primitives | Radix UI | Accessible, unstyled headless components |
| Icons | Lucide React | Consistent, tree-shakeable icon set |
| Animations | Framer Motion | Production-grade animations |
| Date handling | date-fns | Lightweight and tree-shakeable |
| Unit testing | Vitest and React Testing Library | Fast, native to Vite |
| E2E testing | Playwright | Cross-browser, reliable, modern |
| API mocking | Mock Service Worker (MSW) | Network-level mocking in tests |
| Component docs | Storybook | Isolated component development |
| Error tracking | Sentry | Production error monitoring |

---

## Developer Roadmaps

### Junior Frontend Engineer (Months 1 to 6)

```
Months 1 to 2: Foundations
  - HTML5 semantics and accessibility basics
  - CSS: box model, Flexbox, Grid, responsive design
  - JavaScript: ES6+, DOM, async/await, Fetch API
  - Git: branching, committing, opening pull requests

Months 3 to 4: React Fundamentals
  - Components, JSX, props, and state
  - Core hooks: useState, useEffect, useRef
  - React Router: routes, nested routes, URL params
  - Forms: controlled inputs, validation, error handling

Months 5 to 6: Building Real Features
  - API integration with React Query
  - Loading, error, and empty state patterns
  - Component testing with React Testing Library
  - Deploy a complete feature from start to finish
```

### Mid-Level Frontend Engineer

```
Deepen Core Skills
  - TypeScript: interfaces, generics, utility types
  - Advanced hooks: useCallback, useMemo, useReducer
  - Custom hooks: write, test, and reuse them
  - Performance: profiling, memoization, code splitting

Architecture and Patterns
  - Component composition patterns
  - State management: Context, Zustand, Redux Toolkit
  - Accessibility: WCAG 2.1 AA compliance and auditing
  - Integration and E2E testing with Playwright

Engineering Habits
  - Code review: giving specific, constructive feedback
  - Writing technical documentation
  - Core Web Vitals and performance optimization
  - Frontend security fundamentals
```

### Senior Frontend Engineer

```
Technical Leadership
  - Frontend system design and scalable architecture
  - Design system creation and maintenance
  - Cross-team API contract design
  - Build tool internals and performance optimization

Engineering Culture
  - Mentoring junior and mid-level engineers
  - Writing technical proposals and RFCs
  - Driving team standards and engineering practices
  - Incident response and retrospectives

Advanced Topics
  - Server-side rendering and static generation with Next.js
  - Web Workers for offloading CPU-intensive work
  - Micro-frontend architecture
  - Accessibility auditing and remediation at scale
```

---

## Interview Preparation

### Topics to Know Well

**HTML and CSS:**
- What is the CSS cascade and how does specificity work?
- When do you use Flexbox vs Grid?
- What are semantic HTML elements and why do they matter?
- What is a mobile-first approach to responsive design?
- What is the critical rendering path?

**JavaScript:**
- Explain closures with a practical example
- What is the event loop? How does async/await work under the hood?
- What is the difference between `var`, `let`, and `const`?
- How does `this` behave in regular functions vs arrow functions?
- What is prototypal inheritance?

**React:**
- What is the Virtual DOM and how does reconciliation work?
- What are the rules of hooks and why do they exist?
- When would you use `useCallback` vs `useMemo`?
- What is the difference between controlled and uncontrolled components?
- How do you handle loading and error states in a React application?

**System Design:**
- How would you architect a real-time notification system?
- How would you build a component library from scratch?
- How would you implement infinite scroll for a large dataset?

### Practical Exercises

```
- Build a debounced search that calls an API, using no external libraries
- Implement a useLocalStorage custom hook from scratch
- Create an accessible modal with a focus trap and keyboard close (Escape key)
- Build a sortable, paginated data table
- Write unit tests for a custom hook using renderHook
- Debug a React performance issue using the Profiler tab
```

---

## Learning Resources

### Official Documentation

| Resource | URL |
|---|---|
| MDN Web Docs | https://developer.mozilla.org |
| React Documentation | https://react.dev |
| Can I Use | https://caniuse.com |
| web.dev by Google | https://web.dev |
| WCAG 2.1 Quick Reference | https://www.w3.org/WAI/WCAG21/quickref/ |
| JavaScript.info | https://javascript.info |

### Books Worth Reading

| Book | Why Read It |
|---|---|
| JavaScript: The Good Parts by Douglas Crockford | Core language design and philosophy |
| Clean Code by Robert C. Martin | Writing code that is easy to read and maintain |
| The Pragmatic Programmer by Hunt and Thomas | Engineering mindset and professional habits |

---

## Contribution Guidelines

### Contributing to This Handbook

Every Sandlip Oasis frontend engineer is empowered to improve this document.

**How to contribute:**

1. Open an issue describing what is missing, incorrect, or unclear
2. Create a branch named `docs/your-topic`
3. Make your changes with clear, concise writing
4. Submit a pull request that describes what changed and why
5. A senior engineer must review and approve all documentation pull requests

**What makes a good contribution:**

- Fixes an inaccuracy or outdated piece of information
- Adds a real example drawn from actual project experience
- Improves clarity without adding unnecessary length
- Fills a genuine knowledge gap for new engineers

**What to avoid:**

- Duplicating content that already exists in the guide
- Subjective style preferences presented as team standards
- Content copied verbatim from external sources

### How to Give Good Code Review Feedback

Be specific and actionable. "This should use `useCallback` because this function is passed as a prop to a memoized child component" is helpful. "This is wrong" is not.

Distinguish between blocking issues and optional suggestions. Make it clear which is which in your comment.

Use "we" rather than "you." The standard is shared: "We prefer `const` here" rather than "You should use `const`."

Acknowledge good work, not only problems. A review is a conversation, not a list of complaints.

Review the code, not the person.

---

## Repository Setup Reference

**Suggested repository names:**

| Name | Notes |
|---|---|
| `sandlip-oasis/frontend-handbook` | Recommended — clear, simple, discoverable |
| `sandlip-oasis/frontend-engineering-guide` | Descriptive and role-aligned |
| `sandlip-oasis/ui-engineering-standards` | Formal and enterprise-grade |

**Repository description:**

The Sandlip Oasis Frontend Engineering Handbook — a comprehensive guide covering HTML5, CSS3, JavaScript ES6+, and React.js for internal onboarding, training, and engineering standards.

**Suggested GitHub topics:**

`frontend` `html5` `css3` `javascript` `react` `engineering-standards` `onboarding` `best-practices` `accessibility` `performance` `sandlip-oasis`

---

*This handbook is maintained as a living document by the Sandlip Oasis engineering team. If something is wrong, outdated, or missing, open an issue. We build this together.*

---

> "Any fool can write code that a computer can understand. Good programmers write code that humans can understand." — Martin Fowler
