# Sandlip Oasis, Frontend Engineering Handbook

> **The definitive guide to building world-class frontend applications at Sandlip Oasis.**
> Authored by the Sandlip Oasis Engineering Team · Maintained as a living document.

---

<div align="center">

**Repository Name Options**
| Option | Description |
|---|---|
| `sandlip-oasis/frontend-handbook` | ✅ Recommended — clear, professional, discoverable |
| `sandlip-oasis/frontend-engineering-guide` | Descriptive and role-aligned |
| `sandlip-oasis/fe-craft` | Short, memorable, culture-forward |
| `sandlip-oasis/ui-engineering-standards` | Formal, enterprise-grade |

**Repository Description**
> *The Sandlip Oasis Frontend Engineering Handbook — a comprehensive, production-grade guide covering HTML5, CSS3, JavaScript ES6+, and React.js for internal onboarding, training, and engineering standards.*

**Suggested GitHub Topics**
`frontend` `html5` `css3` `javascript` `react` `engineering-standards` `onboarding` `best-practices` `web-development` `accessibility` `performance` `sandlip-oasis` `frontend-architecture` `ui-engineering`

</div>

---

## 📋 Table of Contents

<details>
<summary><strong>Expand Full Table of Contents</strong></summary>

- [About This Handbook](#-about-this-handbook)
- [Sandlip Oasis Engineering Culture](#-sandlip-oasis-engineering-culture)
- [Frontend Engineering Philosophy](#-frontend-engineering-philosophy)
- [How to Use This Guide](#-how-to-use-this-guide)
- [Developer Onboarding](#-developer-onboarding)
- [Recommended Tooling & Environment](#-recommended-tooling--environment)
- [Repository & Folder Structure](#-repository--folder-structure)
- [Git & GitHub Workflow](#-git--github-workflow)
- [HTML5](#-html5)
  - [Fundamentals](#html5-fundamentals)
  - [Semantic HTML](#semantic-html)
  - [Forms & Validation](#forms--validation)
  - [Accessibility (a11y)](#accessibility-a11y)
  - [HTML Best Practices](#html-best-practices)
- [CSS3](#-css3)
  - [Fundamentals](#css3-fundamentals)
  - [Layouts: Flexbox & Grid](#layouts-flexbox--grid)
  - [Responsive Design](#responsive-design)
  - [CSS Variables & Theming](#css-variables--theming)
  - [Animations & Transitions](#animations--transitions)
  - [CSS Architecture (BEM, ITCSS)](#css-architecture)
  - [CSS Best Practices](#css-best-practices)
- [JavaScript (ES6+)](#-javascript-es6)
  - [Core Language Fundamentals](#core-language-fundamentals)
  - [ES6+ Features Deep Dive](#es6-features-deep-dive)
  - [Asynchronous JavaScript](#asynchronous-javascript)
  - [DOM Manipulation](#dom-manipulation)
  - [JavaScript Modules](#javascript-modules)
  - [Error Handling](#error-handling)
  - [JavaScript Best Practices](#javascript-best-practices)
- [React.js](#-reactjs)
  - [Core Concepts](#react-core-concepts)
  - [Hooks Deep Dive](#hooks-deep-dive)
  - [Component Architecture](#component-architecture)
  - [State Management](#state-management)
  - [API Integration](#api-integration)
  - [React Performance](#react-performance)
  - [React Best Practices](#react-best-practices)
- [Frontend Performance Optimization](#-frontend-performance-optimization)
- [Security Best Practices](#-security-best-practices)
- [Testing](#-testing)
- [Debugging Workflows](#-debugging-workflows)
- [Deployment](#-deployment)
- [Coding Standards & Conventions](#-coding-standards--conventions)
- [Common Mistakes & Anti-Patterns](#-common-mistakes--anti-patterns)
- [Frontend Project Checklist](#-frontend-project-checklist)
- [Recommended Libraries & Ecosystem](#-recommended-libraries--ecosystem)
- [Developer Roadmaps](#-developer-roadmaps)
- [Interview Preparation](#-interview-preparation)
- [Learning Resources](#-learning-resources)
- [Contribution Guidelines](#-contribution-guidelines)

</details>

---

## 📖 About This Handbook

This handbook is the **single source of truth** for frontend engineering at Sandlip Oasis. It defines how we build, review, test, and ship UI code — from a developer's first day to their most complex system design decision.

This is not a tutorial. It is an **engineering standard** — grounded in real-world practice, shaped by hard-earned lessons, and continuously improved by the team that uses it.

| Audience | What You'll Find |
|---|---|
| **New Joiners** | Onboarding steps, tooling setup, culture context |
| **Junior Engineers** | Fundamentals, guided code examples, learning paths |
| **Mid-level Engineers** | Architecture patterns, best practices, advanced React |
| **Senior Engineers** | Performance, security, scalability, contribution guidelines |

---

## 🌴 Sandlip Oasis Engineering Culture

At Sandlip Oasis, engineering is a craft. We believe that the best software is built at the intersection of **technical rigor, empathy for users, and pride in craft**.

Our engineering culture is defined by five values:

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   1. CLARITY        — Write code that teaches itself    │
│   2. OWNERSHIP      — Own your work end to end          │
│   3. COLLABORATION  — Great software is a team sport    │
│   4. ITERATION      — Ship, learn, improve, repeat      │
│   5. INCLUSIVITY    — Build for every user              │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

We do not optimize for speed at the cost of quality. We do not accept "it works on my machine." We write code for the engineer who comes after us — because that engineer may be ourselves six months later.

---

## 🧭 Frontend Engineering Philosophy

> *"The UI is the product. Everything else is infrastructure."*

### Core Principles

**1. Semantic First**
HTML communicates meaning to browsers, assistive technologies, and search engines. Div soup is technical debt. Every element choice is a statement.

**2. Progressive Enhancement**
Build a solid, functional baseline. Enhance with CSS. Enrich with JavaScript. Never build a wall — always provide a path for every user.

**3. Performance is a Feature**
A 3-second load is a failed UX. Performance is not a post-launch concern — it is an engineering discipline embedded from the first line of code.

**4. Accessibility is Non-Negotiable**
Building for accessibility is not charity. It is engineering excellence. Every interactive element must be operable with a keyboard. Every image must have meaningful alt text. Every color contrast must meet WCAG standards.

**5. Components are Contracts**
A component makes a promise: given these props, I will produce this UI. That contract must be consistent, documented, and testable.

**6. State is the Source of Truth**
UI is a function of state. When the UI behaves unexpectedly, the answer lives in state — not in a CSS hack.

---

## 🗺️ How to Use This Guide

This guide is organized in a **progressive learning sequence**. You do not need to read it front to back on day one. Use it as a reference, a curriculum, and a standard.

```
New to the team?        → Start with "Developer Onboarding"
Learning HTML/CSS/JS?  → Work through sections in order
Building in React?     → Jump to the React.js section
Shipping to prod?      → Review the Checklist and Security sections
Reviewing a PR?        → Reference Coding Standards & Anti-Patterns
Preparing for interviews? → See the Interview Preparation section
```

> 💡 **Tip:** Bookmark this README. Reference it before opening a Stack Overflow tab.

---

## 🚀 Developer Onboarding

### Week 1 Checklist

```markdown
Day 1
 ☐ Set up development environment (see Tooling section)
 ☐ Clone the main frontend repository
 ☐ Run the project locally
 ☐ Read this handbook (skim in full, deep-read your focus areas)
 ☐ Meet your team lead and onboarding buddy

Day 2–3
 ☐ Complete your first "good first issue" task
 ☐ Submit your first pull request
 ☐ Attend a code review session as an observer
 ☐ Familiarize yourself with the CI/CD pipeline

Day 4–5
 ☐ Deep-read the sections most relevant to your current task
 ☐ Set up your VS Code extensions (see Tooling section)
 ☐ Review 2–3 recent merged PRs to learn team conventions
 ☐ Introduce yourself in #frontend Slack channel
```

### Environment Setup

```bash
# 1. Install Node.js via nvm (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts
nvm use --lts

# 2. Install package manager
npm install -g pnpm   # Preferred at Sandlip Oasis

# 3. Clone the project
git clone https://github.com/sandlip-oasis/<project-name>.git
cd <project-name>

# 4. Install dependencies
pnpm install

# 5. Start development server
pnpm dev
```

> ⚠️ **Warning:** Always use the Node.js version specified in `.nvmrc` or `package.json > engines`. Version mismatches cause silent, hard-to-debug failures.

---

## 🛠️ Recommended Tooling & Environment

### VS Code Extensions

| Extension | Purpose | Priority |
|---|---|---|
| **ESLint** | Live linting and error highlighting | Required |
| **Prettier** | Automatic code formatting | Required |
| **GitLens** | Enhanced Git history and blame | Required |
| **ES7+ React Snippets** | React/JSX code snippets | Required |
| **Tailwind CSS IntelliSense** | Autocomplete for Tailwind | If using Tailwind |
| **Auto Rename Tag** | Sync opening/closing HTML tags | Strongly recommended |
| **Path Intellisense** | File path autocomplete | Strongly recommended |
| **Error Lens** | Inline error messages | Strongly recommended |
| **Thunder Client** | Lightweight REST client in VS Code | Recommended |
| **Code Spell Checker** | Catches typos in comments/strings | Recommended |
| **Bracket Pair Colorization** | Built-in since VS Code 1.67 | Enable in settings |
| **Import Cost** | Shows bundle size of imports | Recommended |

### VS Code Settings (`.vscode/settings.json`)

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

| Tool | Purpose | Notes |
|---|---|---|
| **pnpm** | Package manager | Faster, more disk-efficient than npm |
| **Vite** | Build tool & dev server | Default for new projects |
| **ESLint** | Static code analysis | Config in `.eslintrc.js` |
| **Prettier** | Code formatter | Config in `.prettierrc` |
| **Husky** | Git hooks | Lint/test before commit |
| **lint-staged** | Run linters on staged files only | Works with Husky |
| **commitlint** | Enforce commit message format | Conventional Commits |

---

## 📁 Repository & Folder Structure

### Recommended Project Structure

```
my-app/
├── .github/
│   ├── workflows/           # CI/CD GitHub Actions
│   │   ├── ci.yml
│   │   └── deploy.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── ISSUE_TEMPLATE/
├── .husky/                  # Git hooks
├── .vscode/                 # Shared editor settings
├── public/                  # Static assets (favicon, robots.txt)
├── src/
│   ├── assets/              # Images, fonts, icons
│   │   ├── images/
│   │   └── fonts/
│   ├── components/          # Reusable UI components
│   │   ├── ui/              # Primitives: Button, Input, Modal
│   │   ├── layout/          # Header, Footer, Sidebar, PageWrapper
│   │   └── features/        # Feature-specific components
│   │       ├── auth/
│   │       ├── dashboard/
│   │       └── settings/
│   ├── hooks/               # Custom React hooks
│   ├── pages/               # Route-level page components
│   ├── services/            # API call functions
│   ├── store/               # State management (Redux/Zustand/Context)
│   ├── styles/              # Global styles, variables, themes
│   │   ├── globals.css
│   │   ├── variables.css
│   │   └── themes/
│   ├── utils/               # Pure utility/helper functions
│   ├── types/               # TypeScript types & interfaces (if using TS)
│   ├── constants/           # App-wide constants
│   ├── config/              # Environment config, feature flags
│   ├── App.jsx
│   └── main.jsx
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── .env.example             # Document all required env vars
├── .eslintrc.js
├── .prettierrc
├── .nvmrc
├── index.html
├── vite.config.js
├── package.json
└── README.md
```

### Component Folder Pattern

Each component lives in its own folder for co-location:

```
src/components/ui/Button/
├── Button.jsx          # Component logic
├── Button.module.css   # Scoped styles
├── Button.test.jsx     # Unit tests
├── Button.stories.jsx  # Storybook stories (if applicable)
└── index.js            # Clean re-export
```

```js
// src/components/ui/Button/index.js
export { default } from './Button';
export * from './Button'; // Named exports if any
```

> 💡 **Tip:** Co-locating tests and styles with components reduces navigation overhead and makes components portable.

---

## 🌿 Git & GitHub Workflow

### Branching Strategy

We follow **GitHub Flow** — a lightweight, trunk-based workflow:

```
main (protected)
 └── feature/[ticket-id]-short-description
 └── fix/[ticket-id]-short-description
 └── chore/update-dependencies
 └── docs/update-readme
```

**Branch naming rules:**
```
feature/SO-142-user-authentication
fix/SO-201-login-button-overflow
chore/upgrade-react-18
docs/add-api-integration-guide
refactor/SO-188-extract-auth-hook
```

### Commit Message Convention

We use **Conventional Commits**:

```
<type>(<scope>): <short description>

[optional body]

[optional footer: BREAKING CHANGE or issue reference]
```

| Type | When to Use |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation changes |
| `style` | Formatting, no logic change |
| `refactor` | Code restructure, no behavior change |
| `test` | Adding/updating tests |
| `chore` | Build system, dependency updates |
| `perf` | Performance improvement |

**Examples:**
```bash
git commit -m "feat(auth): add JWT refresh token logic"
git commit -m "fix(button): resolve focus ring not showing in Safari"
git commit -m "perf(images): implement lazy loading on product grid"
git commit -m "docs(readme): update onboarding section for new toolchain"
```

### Pull Request Guidelines

```markdown
## PR Checklist (add to PULL_REQUEST_TEMPLATE.md)

### Description
<!-- What does this PR do? Why? -->

### Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Refactor
- [ ] Documentation

### Testing
- [ ] Unit tests added/updated
- [ ] Tested in Chrome, Firefox, Safari
- [ ] Tested on mobile viewport

### Quality
- [ ] No console.log statements left in code
- [ ] No commented-out code blocks
- [ ] Accessibility considerations addressed
- [ ] Performance impact considered

### Screenshots (if UI change)
<!-- Before / After -->
```

**PR Rules:**
- PRs must be **reviewed by at least 1 engineer** before merging
- Keep PRs **focused and small** — aim for <400 lines changed
- Link to the relevant issue/ticket
- Resolve all review comments before merging
- Squash commits on merge to keep history clean

---

## 🏷️ HTML5

### HTML5 Fundamentals

HTML is the skeleton of the web. Every browser renders HTML into a DOM tree that CSS styles and JavaScript manipulates.

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
    <!-- Content here -->
    <script type="module" src="/main.js"></script>
  </body>
</html>
```

> ⚠️ **Critical:** Always include `lang` attribute on `<html>`. Screen readers use it to select the correct language profile.

### Semantic HTML

Semantic elements communicate meaning — not just appearance. They improve accessibility, SEO, and code readability.

| Element | Purpose |
|---|---|
| `<header>` | Introductory content for a page or section |
| `<nav>` | Primary navigation links |
| `<main>` | The dominant content of the `<body>` (one per page) |
| `<article>` | Self-contained content (blog post, news story) |
| `<section>` | Thematic grouping of content |
| `<aside>` | Supplementary content (sidebar) |
| `<footer>` | Footer for page or section |
| `<figure>` + `<figcaption>` | Image with caption |
| `<time>` | Date/time representation |
| `<address>` | Contact information |

**Non-Semantic (Avoid):**
```html
<!-- ❌ Bad: div soup — no meaning -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
  </div>
</div>
```

**Semantic (Correct):**
```html
<!-- ✅ Good: communicates structure -->
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
    <p>Content...</p>
  </article>
</main>
<footer>
  <p>&copy; 2025 Sandlip Oasis</p>
</footer>
```

### Heading Hierarchy

```html
<!-- ✅ One h1 per page. Headings in logical order. -->
<h1>Main Page Title</h1>          <!-- One per page -->
  <h2>Major Section</h2>
    <h3>Subsection</h3>
      <h4>Sub-subsection</h4>

<!-- ❌ Never skip levels for visual styling -->
<h1>Title</h1>
<h4>Subtitle</h4>  <!-- WRONG: jumped from h1 to h4 -->
```

### Forms & Validation

```html
<form action="/submit" method="POST" novalidate>
  <fieldset>
    <legend>Account Details</legend>

    <!-- Label MUST be associated with input -->
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
      <span id="email-hint" class="hint">We'll never share your email.</span>
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

**Input Type Reference:**

| Type | Use Case |
|---|---|
| `text` | General short text |
| `email` | Email addresses (triggers email keyboard on mobile) |
| `password` | Passwords (masked input) |
| `tel` | Phone numbers (triggers numeric keyboard) |
| `number` | Numeric input with spinners |
| `url` | URL input |
| `search` | Search fields |
| `date` / `time` | Date/time pickers |
| `checkbox` | Boolean toggles |
| `radio` | Single selection from a group |
| `file` | File upload |
| `range` | Slider input |

### Accessibility (a11y)

**WCAG 2.1 Compliance is required for all Sandlip Oasis products.** Target Level AA.

```html
<!-- 1. Images: meaningful alt text -->
<img src="team-photo.jpg" alt="The Sandlip Oasis engineering team at the 2024 retreat" />

<!-- Decorative images: empty alt -->
<img src="decorative-wave.svg" alt="" role="presentation" />

<!-- 2. Buttons vs links -->
<!-- Use <button> for actions, <a> for navigation -->
<button type="button" onclick="openModal()">Open Settings</button>
<a href="/dashboard">Go to Dashboard</a>

<!-- 3. ARIA roles and properties -->
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

<!-- 4. Skip navigation link (critical for keyboard users) -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<!-- 5. Focus management for modals -->
<dialog aria-modal="true" aria-labelledby="modal-title">
  <h2 id="modal-title">Confirm Deletion</h2>
  <p>Are you sure you want to delete this item?</p>
  <button autofocus>Cancel</button>
  <button>Confirm</button>
</dialog>
```

**a11y Checklist:**
```
☐ All images have meaningful alt text
☐ Color is not the only means of conveying information
☐ Color contrast ratio is at least 4.5:1 for normal text
☐ All interactive elements are keyboard-operable
☐ Focus order follows visual reading order
☐ Focus is visible and never removed
☐ Forms have properly associated labels
☐ Error messages are descriptive and announced by screen readers
☐ Dynamic content changes are announced via aria-live regions
☐ Page has a single <h1> and logical heading hierarchy
```

### HTML Best Practices

```html
<!-- ✅ Use boolean attributes correctly -->
<input type="checkbox" checked />
<button disabled>Submit</button>

<!-- ✅ Lazy load images below the fold -->
<img src="hero.jpg" alt="Hero" loading="eager" />       <!-- Above fold -->
<img src="team.jpg" alt="Team" loading="lazy" />        <!-- Below fold -->

<!-- ✅ Preload critical resources -->
<link rel="preload" href="/fonts/brand.woff2" as="font" type="font/woff2" crossorigin />
<link rel="preconnect" href="https://api.sandlipoasis.com" />

<!-- ✅ Structured data for SEO -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Sandlip Oasis",
  "url": "https://sandlipoasis.com"
}
</script>
```

---

## 🎨 CSS3

### CSS3 Fundamentals

The cascade, specificity, and inheritance are the three laws of CSS. Understanding them prevents 90% of CSS bugs.

**Specificity Hierarchy (highest → lowest):**
```
Inline styles           → 1,0,0,0  (style="")
ID selectors            → 0,1,0,0  (#id)
Class / Pseudo-class    → 0,0,1,0  (.class, :hover)
Element / Pseudo-element→ 0,0,0,1  (div, ::before)
Universal selector      → 0,0,0,0  (*)
```

**The Box Model:**
```css
/* box-sizing: border-box is the sane default */
*, *::before, *::after {
  box-sizing: border-box;
}

.element {
  width: 300px;       /* Total rendered width */
  padding: 16px;      /* INCLUDED in width with border-box */
  border: 2px solid;  /* INCLUDED in width with border-box */
  margin: 24px;       /* Outside the box */
}
```

### CSS Custom Properties (Variables)

```css
/* Define at root for global access */
:root {
  /* Color Palette */
  --color-primary: #1a73e8;
  --color-primary-dark: #1558b0;
  --color-primary-light: #e8f0fe;
  --color-secondary: #0d9488;
  --color-danger: #dc2626;
  --color-warning: #d97706;
  --color-success: #16a34a;

  /* Neutrals */
  --color-gray-50: #f9fafb;
  --color-gray-100: #f3f4f6;
  --color-gray-500: #6b7280;
  --color-gray-900: #111827;

  /* Semantic tokens */
  --color-text-primary: var(--color-gray-900);
  --color-text-secondary: var(--color-gray-500);
  --color-bg-surface: #ffffff;
  --color-bg-page: var(--color-gray-50);

  /* Typography */
  --font-sans: 'Inter Variable', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  --font-size-2xl: 1.5rem;
  --font-size-3xl: 1.875rem;
  --font-size-4xl: 2.25rem;
  --line-height-tight: 1.25;
  --line-height-normal: 1.6;

  /* Spacing Scale */
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-3: 0.75rem;
  --space-4: 1rem;
  --space-6: 1.5rem;
  --space-8: 2rem;
  --space-12: 3rem;
  --space-16: 4rem;

  /* Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);

  /* Transitions */
  --transition-fast: 150ms ease;
  --transition-base: 250ms ease;
  --transition-slow: 400ms ease;
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
  :root {
    --color-text-primary: var(--color-gray-50);
    --color-text-secondary: var(--color-gray-400);
    --color-bg-surface: #1f2937;
    --color-bg-page: #111827;
  }
}
```

### Layouts: Flexbox & Grid

**Flexbox — one-dimensional layout:**

```css
/* Common flexbox patterns */

/* Centered content */
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Space between navigation items */
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: var(--space-4);
}

/* Card list that wraps */
.card-list {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-6);
}

/* Sidebar + content layout */
.page-layout {
  display: flex;
  gap: var(--space-8);
}

.sidebar {
  flex: 0 0 280px;    /* Don't grow, don't shrink, fixed at 280px */
}

.content {
  flex: 1;            /* Take remaining space */
  min-width: 0;       /* Prevent overflow (critical!) */
}
```

**CSS Grid — two-dimensional layout:**

```css
/* 12-column grid system */
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-6);
}

.col-span-4 { grid-column: span 4; }
.col-span-6 { grid-column: span 6; }
.col-span-12 { grid-column: span 12; }

/* Auto-fill responsive cards — no media queries needed */
.auto-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: var(--space-6);
}

/* Complex page layout */
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

We use a **mobile-first** approach. Start with mobile styles, then add breakpoints for larger screens.

```css
/* Breakpoint system */
:root {
  --bp-sm:  640px;
  --bp-md:  768px;
  --bp-lg:  1024px;
  --bp-xl:  1280px;
  --bp-2xl: 1536px;
}

/* Mobile-first: base styles apply to all sizes */
.card {
  padding: var(--space-4);
  font-size: var(--font-size-base);
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
    font-size: var(--font-size-lg);
  }
}

/* Fluid typography with clamp() */
h1 {
  font-size: clamp(1.75rem, 4vw + 1rem, 3.5rem);
}

/* Container queries (modern approach) */
.card-container {
  container-type: inline-size;
  container-name: card;
}

@container card (min-width: 400px) {
  .card-inner {
    display: flex;
    gap: var(--space-4);
  }
}
```

**Responsive images:**
```css
/* Images never overflow their container */
img, video {
  max-width: 100%;
  height: auto;
  display: block;
}
```

### Animations & Transitions

```css
/* Transitions: for state changes (hover, focus, active) */
.button {
  background-color: var(--color-primary);
  transition: background-color var(--transition-fast),
              transform var(--transition-fast),
              box-shadow var(--transition-fast);
}

.button:hover {
  background-color: var(--color-primary-dark);
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
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

/* Skeleton loading pulse */
@keyframes skeleton-pulse {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.4; }
}

.skeleton {
  background: var(--color-gray-200);
  border-radius: var(--radius-sm);
  animation: skeleton-pulse 1.5s ease-in-out infinite;
}

/* Respect user motion preferences — ALWAYS */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### CSS Architecture

We use a hybrid approach combining **BEM naming** with **utility classes** for a maintainable codebase.

**BEM (Block Element Modifier):**

```css
/* Block */
.card { }

/* Element (part of the block) */
.card__header { }
.card__body { }
.card__footer { }
.card__title { }

/* Modifier (variation) */
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

**CSS Modules (recommended for React):**
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

const Button = ({ variant = 'primary', children }) => (
  <button className={`${styles.button} ${styles[variant]}`}>
    {children}
  </button>
);
```

### CSS Best Practices

```css
/* ✅ Use logical properties for internationalization */
.element {
  margin-inline: auto;          /* Not margin-left/right */
  padding-block: var(--space-4); /* Not padding-top/bottom */
  border-inline-start: 3px solid; /* Not border-left */
}

/* ✅ Avoid magic numbers — use variables */
/* ❌ Bad */
.header { height: 64px; }

/* ✅ Good */
:root { --header-height: 64px; }
.header { height: var(--header-height); }

/* ✅ Use :is() and :where() for cleaner selectors */
:is(h1, h2, h3, h4, h5, h6) {
  font-weight: 600;
  line-height: var(--line-height-tight);
}

/* ✅ Prevent layout shifts with aspect-ratio */
.video-container {
  aspect-ratio: 16 / 9;
  width: 100%;
}

/* ✅ Use gap instead of margin for flex/grid spacing */
.button-group {
  display: flex;
  gap: var(--space-3);  /* Not margin-right on children */
}
```

---

## ⚡ JavaScript (ES6+)

### Core Language Fundamentals

**Variables: Always prefer `const`, use `let` when reassignment is needed, never use `var`.**

```js
// ✅ Correct
const API_BASE = 'https://api.sandlipoasis.com';
let retryCount = 0;

// ❌ Never
var userData = {};
```

**Equality: Always use strict equality (`===`).**

```js
// ❌ Avoid: type coercion causes subtle bugs
0 == false   // true
'' == false  // true
null == undefined // true

// ✅ Correct: no coercion
0 === false   // false
'' === false  // false
```

### ES6+ Features Deep Dive

**Destructuring:**

```js
// Object destructuring
const user = { name: 'Amara', role: 'engineer', team: 'frontend' };
const { name, role, team = 'unknown' } = user; // default value
const { name: userName } = user; // rename

// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];

// Function parameter destructuring (very common in React)
function UserCard({ name, role, avatarUrl = '/default-avatar.png' }) {
  return <div>{name} - {role}</div>;
}

// Nested destructuring
const { address: { city, country } } = { address: { city: 'Lagos', country: 'Nigeria' } };
```

**Spread & Rest:**

```js
// Spread: expand iterables
const defaults = { theme: 'light', lang: 'en', fontSize: 16 };
const userPrefs = { theme: 'dark', fontSize: 18 };
const finalConfig = { ...defaults, ...userPrefs }; 
// → { theme: 'dark', lang: 'en', fontSize: 18 }

// Array spread
const allUsers = [...adminUsers, ...regularUsers];

// Rest: collect remaining arguments
function log(level, ...messages) {
  console[level](messages.join(' '));
}
log('info', 'User', 'logged', 'in'); // User logged in
```

**Template Literals:**

```js
const name = 'Amara';
const role = 'Senior Engineer';

// ✅ Template literals
const greeting = `Welcome back, ${name}! You are logged in as ${role}.`;

// Multi-line strings
const emailBody = `
  Dear ${name},

  Your account has been updated.
  
  — The Sandlip Oasis Team
`.trim();

// Tagged templates (used in styled-components, SQL, etc.)
const query = sql`SELECT * FROM users WHERE id = ${userId}`;
```

**Arrow Functions:**

```js
// Concise syntax
const double = x => x * 2;
const add = (a, b) => a + b;
const getUser = (id) => ({ id, name: 'Amara' }); // Wrap objects in ()

// Arrow functions do NOT have their own `this`
class Timer {
  constructor() {
    this.seconds = 0;
  }

  start() {
    // ✅ Arrow function captures `this` from enclosing scope
    setInterval(() => {
      this.seconds++;
    }, 1000);
  }
}
```

**Optional Chaining & Nullish Coalescing:**

```js
// Optional chaining (?.) — safe property access
const user = null;
const city = user?.address?.city;       // undefined (not TypeError)
const firstTag = user?.tags?.[0];       // Array access
const name = user?.getName?.();         // Method call

// Nullish coalescing (??) — fallback for null/undefined ONLY
const displayName = user?.name ?? 'Anonymous';  // Only falls back on null/undefined
const count = user?.count ?? 0;

// Difference from ||
const value = 0 || 'default';   // 'default' (0 is falsy)
const value2 = 0 ?? 'default';  // 0 (0 is not null/undefined)
```

**Array Methods:**

```js
const engineers = [
  { name: 'Amara', role: 'frontend', level: 'senior', active: true },
  { name: 'Kofi', role: 'backend', level: 'mid', active: true },
  { name: 'Zara', role: 'frontend', level: 'junior', active: false },
  { name: 'Jide', role: 'frontend', level: 'mid', active: true },
];

// filter: returns new array of matching items
const frontendEngineers = engineers.filter(e => e.role === 'frontend');

// map: transforms each item
const names = engineers.map(e => e.name); // ['Amara', 'Kofi', 'Zara', 'Jide']

// find: returns first match (or undefined)
const senior = engineers.find(e => e.level === 'senior');

// findIndex: returns index of first match (or -1)
const kofiIndex = engineers.findIndex(e => e.name === 'Kofi');

// some: returns true if any item matches
const hasJunior = engineers.some(e => e.level === 'junior'); // true

// every: returns true if all items match
const allActive = engineers.every(e => e.active); // false

// reduce: accumulates a single value
const activeCount = engineers.reduce((count, e) => count + (e.active ? 1 : 0), 0);

// Chaining
const activeFrontendNames = engineers
  .filter(e => e.role === 'frontend' && e.active)
  .map(e => e.name.toUpperCase())
  .sort();

// flat & flatMap
const nested = [[1, 2], [3, 4], [5]];
nested.flat();           // [1, 2, 3, 4, 5]

const sentences = ['hello world', 'foo bar'];
sentences.flatMap(s => s.split(' ')); // ['hello', 'world', 'foo', 'bar']
```

**Object Methods:**

```js
const config = { host: 'localhost', port: 3000, debug: true };

Object.keys(config);    // ['host', 'port', 'debug']
Object.values(config);  // ['localhost', 3000, true]
Object.entries(config); // [['host', 'localhost'], ['port', 3000], ...]

// Build object from entries
const uppercased = Object.fromEntries(
  Object.entries(config).map(([k, v]) => [k.toUpperCase(), v])
);

// Object.assign (prefer spread syntax)
const merged = Object.assign({}, defaults, overrides);
const merged2 = { ...defaults, ...overrides }; // ✅ Preferred

// Freeze an object (shallow immutability)
const STATUS = Object.freeze({ PENDING: 'pending', ACTIVE: 'active' });
```

### Asynchronous JavaScript

**Promises:**

```js
// Creating a promise
function fetchUser(id) {
  return new Promise((resolve, reject) => {
    if (!id) {
      reject(new Error('User ID is required'));
      return;
    }
    setTimeout(() => resolve({ id, name: 'Amara' }), 1000);
  });
}

// Promise chaining
fetchUser(1)
  .then(user => enrichUserData(user))
  .then(enrichedUser => updateUI(enrichedUser))
  .catch(error => handleError(error))
  .finally(() => hideLoadingSpinner());

// Promise combinators
const [user, posts, settings] = await Promise.all([
  fetchUser(id),
  fetchPosts(id),
  fetchSettings(id),
]);

// First to resolve
const fastest = await Promise.race([primaryAPI(), fallbackAPI()]);

// All settle (never rejects)
const results = await Promise.allSettled([fetchA(), fetchB()]);
results.forEach(result => {
  if (result.status === 'fulfilled') console.log(result.value);
  if (result.status === 'rejected') console.error(result.reason);
});
```

**Async/Await:**

```js
// ✅ Clean, readable async code
async function loadDashboard(userId) {
  try {
    // Sequential (one waits for the other)
    const user = await fetchUser(userId);

    // Parallel (both start simultaneously)
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

// Async IIFE (immediately invoked)
(async () => {
  const data = await loadDashboard('user-123');
  renderDashboard(data);
})();
```

**Fetch API:**

```js
// Centralized API client
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

  get: (endpoint, options) =>
    apiClient.request(endpoint, { method: 'GET', ...options }),

  post: (endpoint, body, options) =>
    apiClient.request(endpoint, {
      method: 'POST',
      body: JSON.stringify(body),
      ...options,
    }),

  put: (endpoint, body, options) =>
    apiClient.request(endpoint, {
      method: 'PUT',
      body: JSON.stringify(body),
      ...options,
    }),

  delete: (endpoint, options) =>
    apiClient.request(endpoint, { method: 'DELETE', ...options }),
};

// Usage
const user = await apiClient.get('/users/1');
const newPost = await apiClient.post('/posts', { title: 'Hello', body: 'World' });
```

### JavaScript Modules

```js
// Named exports (multiple per file)
export const formatDate = (date) => new Intl.DateTimeFormat('en-GB').format(date);
export const formatCurrency = (amount, currency = 'USD') =>
  new Intl.NumberFormat('en-US', { style: 'currency', currency }).format(amount);

// Default export (one per file, usually the main thing)
export default class UserService { ... }

// Re-exports (barrel files — use sparingly)
// src/utils/index.js
export { formatDate, formatCurrency } from './formatters';
export { debounce, throttle } from './timing';
export { classNames } from './dom';

// Dynamic imports (code splitting)
const LazyComponent = lazy(() => import('./components/HeavyChart'));
const { default: Chart } = await import('./Chart.js');
```

### Error Handling

```js
// Custom error classes
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

// Error handling strategy
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
// ✅ Pure functions: no side effects, predictable output
const calculateTotal = (items) =>
  items.reduce((sum, item) => sum + item.price * item.quantity, 0);

// ✅ Guard clauses reduce nesting
function processUser(user) {
  if (!user) throw new Error('User is required');
  if (!user.isActive) return null;
  if (!user.hasPermission) throw new PermissionError();

  // Main logic here — no deep nesting
  return transformUser(user);
}

// ✅ Debounce expensive operations
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

// ✅ Avoid mutation — return new data
// ❌ Bad
function addItem(cart, item) {
  cart.items.push(item);  // Mutates original
  return cart;
}

// ✅ Good
function addItem(cart, item) {
  return {
    ...cart,
    items: [...cart.items, item],
    total: cart.total + item.price,
  };
}
```

---

## ⚛️ React.js

### React Core Concepts

React renders a UI as a **function of state**: `UI = f(state)`. Master this mental model before all else.

**JSX:**

```jsx
// JSX is syntactic sugar for React.createElement()
// This JSX:
const element = <h1 className="title">Hello, {name}!</h1>;

// Compiles to:
const element = React.createElement('h1', { className: 'title' }, `Hello, ${name}!`);

// JSX rules:
// 1. Return a single root element (or Fragment)
// 2. className, not class
// 3. htmlFor, not for
// 4. All tags must be closed (self-closing: <img />, <br />)
// 5. camelCase for event handlers (onClick, onChange)
// 6. JavaScript expressions in {}

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

### Hooks Deep Dive

**`useState` — local component state:**

```jsx
import { useState } from 'react';

function Counter() {
  // [state, setter] = useState(initialValue)
  const [count, setCount] = useState(0);

  // ✅ Functional updates — use when next state depends on previous
  const increment = () => setCount(prev => prev + 1);
  const decrement = () => setCount(prev => prev - 1);

  return (
    <div>
      <button onClick={decrement}>−</button>
      <span>{count}</span>
      <button onClick={increment}>+</button>
    </div>
  );
}

// Object state
function ProfileForm() {
  const [form, setForm] = useState({ name: '', email: '', bio: '' });

  const handleChange = (e) => {
    const { name, value } = e.target;
    // ✅ Spread to avoid overwriting other fields
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

**`useEffect` — side effects:**

```jsx
import { useState, useEffect } from 'react';

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    // Setup: runs after render
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

    // Cleanup: runs before next effect or on unmount
    return () => {
      cancelled = true;  // Prevent state update on unmounted component
    };
  }, [userId]); // Dependency array — re-runs when userId changes

  if (loading) return <Skeleton />;
  if (error) return <ErrorMessage message={error} />;
  if (!user) return null;

  return <div>{user.name}</div>;
}

// ✅ Effect dependency cheatsheet
useEffect(() => { ... });          // Runs after every render — rarely what you want
useEffect(() => { ... }, []);      // Runs once after mount
useEffect(() => { ... }, [id]);    // Runs after mount + when id changes
```

**`useCallback` & `useMemo` — memoization:**

```jsx
import { useState, useCallback, useMemo } from 'react';

function ExpensiveComponent({ items, onSelect }) {
  // ✅ useMemo: memoize expensive computations
  const sortedItems = useMemo(
    () => [...items].sort((a, b) => a.name.localeCompare(b.name)),
    [items]  // Recomputes only when items changes
  );

  const total = useMemo(
    () => items.reduce((sum, item) => sum + item.price, 0),
    [items]
  );

  return <div>Total: {total}</div>;
}

function Parent() {
  const [filter, setFilter] = useState('');

  // ✅ useCallback: stable function reference for child props
  // Without this, a new function is created on every Parent render,
  // causing Child to re-render even when logic is the same
  const handleSelect = useCallback((item) => {
    console.log('Selected:', item);
  }, []); // Empty: function never changes

  return <ExpensiveComponent onSelect={handleSelect} />;
}
```

**`useRef` — mutable references without re-render:**

```jsx
import { useRef, useEffect } from 'react';

function FocusInput() {
  const inputRef = useRef(null);

  // Focus on mount
  useEffect(() => {
    inputRef.current?.focus();
  }, []);

  return <input ref={inputRef} placeholder="Auto-focused" />;
}

// Storing previous value
function usePrevious(value) {
  const ref = useRef();
  useEffect(() => {
    ref.current = value;
  });
  return ref.current;
}

// Storing mutable value without triggering re-render
function Timer() {
  const intervalRef = useRef(null);

  const start = () => {
    intervalRef.current = setInterval(() => console.log('tick'), 1000);
  };

  const stop = () => {
    clearInterval(intervalRef.current);
  };

  useEffect(() => () => clearInterval(intervalRef.current), []);

  return (
    <div>
      <button onClick={start}>Start</button>
      <button onClick={stop}>Stop</button>
    </div>
  );
}
```

**Custom Hooks:**

```jsx
// Custom hooks encapsulate reusable stateful logic
// Convention: name starts with "use"

// useLocalStorage — persists state to localStorage
function useLocalStorage(key, initialValue) {
  const [storedValue, setStoredValue] = useState(() => {
    try {
      const item = window.localStorage.getItem(key);
      return item ? JSON.parse(item) : initialValue;
    } catch {
      return initialValue;
    }
  });

  const setValue = useCallback((value) => {
    try {
      const valueToStore = value instanceof Function ? value(storedValue) : value;
      setStoredValue(valueToStore);
      window.localStorage.setItem(key, JSON.stringify(valueToStore));
    } catch (error) {
      console.error(`Error saving to localStorage key "${key}":`, error);
    }
  }, [key, storedValue]);

  return [storedValue, setValue];
}

// useDebounce — delays updating a value
function useDebounce(value, delay = 300) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => setDebouncedValue(value), delay);
    return () => clearTimeout(timer);
  }, [value, delay]);

  return debouncedValue;
}

// useFetch — generic data fetching hook
function useFetch(url) {
  const [state, setState] = useState({ data: null, loading: true, error: null });

  useEffect(() => {
    if (!url) return;

    let cancelled = false;
    setState(prev => ({ ...prev, loading: true, error: null }));

    fetch(url)
      .then(res => {
        if (!res.ok) throw new Error(`HTTP ${res.status}`);
        return res.json();
      })
      .then(data => {
        if (!cancelled) setState({ data, loading: false, error: null });
      })
      .catch(error => {
        if (!cancelled) setState({ data: null, loading: false, error: error.message });
      });

    return () => { cancelled = true; };
  }, [url]);

  return state;
}

// Usage
function SearchResults() {
  const [query, setQuery] = useState('');
  const debouncedQuery = useDebounce(query, 400);
  const { data, loading, error } = useFetch(
    debouncedQuery ? `/api/search?q=${debouncedQuery}` : null
  );

  return (
    <div>
      <input value={query} onChange={e => setQuery(e.target.value)} />
      {loading && <Spinner />}
      {error && <ErrorBanner message={error} />}
      {data && <ResultsList results={data} />}
    </div>
  );
}
```

### Component Architecture

**Component Classification:**

```
UI Components (Presentational)
  └── Pure components — receive props, render UI, emit events
  └── No business logic, no API calls
  └── Highly reusable

Feature Components (Container/Smart)
  └── Own state and side effects
  └── Fetch data, manage complex interactions
  └── Compose UI components

Page Components
  └── Route-level components
  └── Orchestrate feature components
  └── Handle route params
```

**Compound Components Pattern:**

```jsx
// Flexible, composable API for complex components
const Tabs = ({ children, defaultTab }) => {
  const [activeTab, setActiveTab] = useState(defaultTab);

  return (
    <TabContext.Provider value={{ activeTab, setActiveTab }}>
      <div className="tabs">{children}</div>
    </TabContext.Provider>
  );
};

Tabs.List = function TabList({ children }) {
  return <div className="tabs__list" role="tablist">{children}</div>;
};

Tabs.Tab = function Tab({ id, children }) {
  const { activeTab, setActiveTab } = useContext(TabContext);
  return (
    <button
      role="tab"
      aria-selected={activeTab === id}
      onClick={() => setActiveTab(id)}
      className={activeTab === id ? 'tabs__tab--active' : 'tabs__tab'}
    >
      {children}
    </button>
  );
};

Tabs.Panel = function TabPanel({ id, children }) {
  const { activeTab } = useContext(TabContext);
  if (activeTab !== id) return null;
  return <div role="tabpanel" className="tabs__panel">{children}</div>;
};

// Usage — expressive and flexible
<Tabs defaultTab="overview">
  <Tabs.List>
    <Tabs.Tab id="overview">Overview</Tabs.Tab>
    <Tabs.Tab id="analytics">Analytics</Tabs.Tab>
    <Tabs.Tab id="settings">Settings</Tabs.Tab>
  </Tabs.List>
  <Tabs.Panel id="overview"><OverviewPanel /></Tabs.Panel>
  <Tabs.Panel id="analytics"><AnalyticsPanel /></Tabs.Panel>
  <Tabs.Panel id="settings"><SettingsPanel /></Tabs.Panel>
</Tabs>
```

**Render Props Pattern:**

```jsx
function DataProvider({ url, render }) {
  const { data, loading, error } = useFetch(url);
  return render({ data, loading, error });
}

// Usage
<DataProvider
  url="/api/users"
  render={({ data, loading, error }) => (
    loading ? <Spinner /> :
    error   ? <Error /> :
              <UserList users={data} />
  )}
/>
```

### State Management

**Hierarchy of state solutions (choose the simplest that works):**

```
1. Local useState          — One component's private data
2. Lifted state            — Shared between sibling components
3. React Context           — Global UI state (theme, auth, locale)
4. Zustand / Jotai         — Client state with actions, no Redux boilerplate
5. Redux Toolkit           — Large apps, complex state logic, time-travel debugging
6. React Query / SWR       — Server state (caching, refetching, loading states)
```

**Context (for truly global state):**

```jsx
// contexts/AuthContext.jsx
const AuthContext = createContext(null);

export function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const unsubscribe = onAuthStateChanged((user) => {
      setUser(user);
      setLoading(false);
    });
    return unsubscribe;
  }, []);

  const login = useCallback(async (credentials) => {
    const user = await authService.login(credentials);
    setUser(user);
  }, []);

  const logout = useCallback(async () => {
    await authService.logout();
    setUser(null);
  }, []);

  if (loading) return <AppLoadingScreen />;

  return (
    <AuthContext.Provider value={{ user, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
}

// Hook for consuming context
export function useAuth() {
  const context = useContext(AuthContext);
  if (!context) throw new Error('useAuth must be used inside AuthProvider');
  return context;
}

// Usage
function Header() {
  const { user, logout } = useAuth();
  return (
    <header>
      <span>Welcome, {user?.name}</span>
      <button onClick={logout}>Sign Out</button>
    </header>
  );
}
```

**Zustand (recommended for client state):**

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

  updateQuantity: (productId, quantity) => set((state) => ({
    items: state.items.map(item =>
      item.id === productId ? { ...item, quantity } : item
    ),
  })),

  clearCart: () => set({ items: [] }),

  // Derived state (computed)
  get totalItems() { return get().items.reduce((sum, i) => sum + i.quantity, 0); },
  get totalPrice() { return get().items.reduce((sum, i) => sum + i.price * i.quantity, 0); },
}));

// Usage in component
function CartIcon() {
  const totalItems = useCartStore(state => state.totalItems);
  return <span>{totalItems}</span>;
}
```

**React Query (recommended for server state):**

```jsx
import { useQuery, useMutation, useQueryClient } from '@tanstack/react-query';

// Fetch + cache + loading/error states
function UserProfile({ userId }) {
  const { data: user, isLoading, isError } = useQuery({
    queryKey: ['user', userId],
    queryFn: () => apiClient.get(`/users/${userId}`),
    staleTime: 5 * 60 * 1000, // Consider fresh for 5 minutes
  });

  if (isLoading) return <Skeleton />;
  if (isError) return <ErrorState />;
  return <div>{user.name}</div>;
}

// Mutations with optimistic updates
function EditProfile({ user }) {
  const queryClient = useQueryClient();

  const mutation = useMutation({
    mutationFn: (updates) => apiClient.put(`/users/${user.id}`, updates),
    onMutate: async (updates) => {
      // Optimistically update the cache
      await queryClient.cancelQueries(['user', user.id]);
      const previous = queryClient.getQueryData(['user', user.id]);
      queryClient.setQueryData(['user', user.id], { ...user, ...updates });
      return { previous };
    },
    onError: (err, vars, context) => {
      // Roll back on error
      queryClient.setQueryData(['user', user.id], context.previous);
    },
    onSettled: () => {
      queryClient.invalidateQueries(['user', user.id]);
    },
  });
}
```

### API Integration

```jsx
// services/userService.js — centralize all API calls for a domain
export const userService = {
  getUser: (id) => apiClient.get(`/users/${id}`),
  
  updateUser: (id, data) => apiClient.put(`/users/${id}`, data),
  
  uploadAvatar: async (id, file) => {
    const formData = new FormData();
    formData.append('avatar', file);
    return apiClient.request(`/users/${id}/avatar`, {
      method: 'POST',
      body: formData,
      headers: {}, // Let browser set multipart Content-Type
    });
  },
  
  searchUsers: (query, filters = {}) => {
    const params = new URLSearchParams({ q: query, ...filters });
    return apiClient.get(`/users/search?${params}`);
  },
};
```

### React Performance

```jsx
// 1. React.memo — prevent re-render when props haven't changed
const UserCard = React.memo(function UserCard({ user, onSelect }) {
  return (
    <div onClick={() => onSelect(user.id)}>
      {user.name}
    </div>
  );
}, (prevProps, nextProps) => {
  // Custom comparison (optional) — return true to skip re-render
  return prevProps.user.id === nextProps.user.id;
});

// 2. Code splitting — load components on demand
import { lazy, Suspense } from 'react';

const AdminDashboard = lazy(() => import('./pages/AdminDashboard'));
const Analytics = lazy(() => import('./pages/Analytics'));

function App() {
  return (
    <Suspense fallback={<PageSkeleton />}>
      <Routes>
        <Route path="/admin" element={<AdminDashboard />} />
        <Route path="/analytics" element={<Analytics />} />
      </Routes>
    </Suspense>
  );
}

// 3. Virtualization for large lists
import { FixedSizeList } from 'react-window';

function VirtualUserList({ users }) {
  const Row = ({ index, style }) => (
    <div style={style}>
      <UserCard user={users[index]} />
    </div>
  );

  return (
    <FixedSizeList
      height={600}
      itemCount={users.length}
      itemSize={80}
      width="100%"
    >
      {Row}
    </FixedSizeList>
  );
}
```

### React Best Practices

```jsx
// ✅ Key prop: use stable IDs, never array index for dynamic lists
// ❌ Bad — index causes wrong re-renders during reordering/filtering
{items.map((item, index) => <Item key={index} {...item} />)}

// ✅ Good
{items.map(item => <Item key={item.id} {...item} />)}

// ✅ Keep components small and focused
// A component should have one job. If you need to scroll to read it, split it.

// ✅ Lift state to the lowest common ancestor
// Don't lift state all the way to root if only two siblings need it

// ✅ Derive state — don't duplicate it
// ❌ Bad: derived state that can get out of sync
const [items, setItems] = useState([]);
const [count, setCount] = useState(0); // Derived — never use useState for this!

// ✅ Good: derive from single source of truth
const [items, setItems] = useState([]);
const count = items.length; // Derived directly

// ✅ Render early returns for loading/error states
function UserPage({ userId }) {
  const { data: user, isLoading, isError } = useUser(userId);

  if (isLoading) return <PageSkeleton />;
  if (isError)   return <ErrorPage />;
  if (!user)     return <NotFound />;

  return <UserDetail user={user} />;  // Clean, focused happy path
}
```

---

## 🚀 Frontend Performance Optimization

Performance is not a feature — it is a discipline.

### Core Web Vitals Targets

| Metric | Good | Needs Work | Poor |
|---|---|---|---|
| **LCP** (Largest Contentful Paint) | ≤ 2.5s | 2.5–4s | > 4s |
| **INP** (Interaction to Next Paint) | ≤ 200ms | 200–500ms | > 500ms |
| **CLS** (Cumulative Layout Shift) | ≤ 0.1 | 0.1–0.25 | > 0.25 |

### Bundle Optimization

```js
// vite.config.js — code splitting strategy
import { defineConfig } from 'vite';

export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
          router: ['react-router-dom'],
          query: ['@tanstack/react-query'],
          ui: ['@radix-ui/react-dialog', '@radix-ui/react-dropdown-menu'],
        },
      },
    },
    // Analyze bundle with: pnpm build && pnpx vite-bundle-analyzer
  },
});
```

### Image Optimization

```html
<!-- ✅ Modern format with fallback -->
<picture>
  <source srcset="hero.avif" type="image/avif" />
  <source srcset="hero.webp" type="image/webp" />
  <img src="hero.jpg" alt="Hero image" width="1200" height="600" loading="eager" />
</picture>

<!-- ✅ Responsive images with srcset -->
<img
  src="card.jpg"
  srcset="card-400.jpg 400w, card-800.jpg 800w, card-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, (max-width: 1200px) 50vw, 400px"
  alt="Card image"
  loading="lazy"
  decoding="async"
/>
```

### Resource Hints

```html
<head>
  <!-- DNS resolution in advance -->
  <link rel="dns-prefetch" href="//fonts.googleapis.com" />
  
  <!-- Pre-establish connection (DNS + TCP + TLS) -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  
  <!-- Preload critical resources -->
  <link rel="preload" href="/fonts/brand.woff2" as="font" type="font/woff2" crossorigin />
  <link rel="preload" href="/images/hero.webp" as="image" />
  
  <!-- Prefetch future navigations -->
  <link rel="prefetch" href="/dashboard" />
</head>
```

### JavaScript Performance

```js
// ✅ Intersection Observer for lazy operations
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      loadContent(entry.target);
      observer.unobserve(entry.target);
    }
  });
}, { rootMargin: '200px' });

document.querySelectorAll('[data-lazy]').forEach(el => observer.observe(el));

// ✅ Web Workers for CPU-intensive tasks (never block the main thread)
// worker.js
self.addEventListener('message', ({ data }) => {
  const result = heavyComputation(data);
  self.postMessage(result);
});

// main.js
const worker = new Worker('/worker.js');
worker.postMessage(largeDataset);
worker.onmessage = ({ data }) => updateChart(data);

// ✅ RequestIdleCallback for non-critical work
requestIdleCallback(() => {
  sendAnalyticsEvent({ type: 'page_view', page: location.pathname });
});
```

### CSS Performance

```css
/* ✅ Use transform and opacity for animations — GPU-composited */
/* ❌ Causes layout recalculation */
.bad-animation { transition: width 300ms; }

/* ✅ GPU-accelerated */
.good-animation { transition: transform 300ms; }

/* ✅ Contain paint to a layer */
.complex-component {
  will-change: transform;   /* Use sparingly — only when truly needed */
  contain: layout style;    /* Scope layout recalculation */
}

/* ✅ Font loading strategy */
@font-face {
  font-family: 'Brand';
  src: url('/fonts/brand.woff2') format('woff2');
  font-weight: 400;
  font-style: normal;
  font-display: swap;   /* Show fallback immediately, swap when loaded */
}
```

---

## 🔒 Security Best Practices

Security is a shared responsibility. Frontend engineers are the last line of defense for many attack vectors.

### XSS (Cross-Site Scripting) Prevention

```jsx
// ✅ React's JSX auto-escapes content — this is safe
function Comment({ text }) {
  return <p>{text}</p>;  // Safe: escaped by React
}

// ❌ DANGER: dangerouslySetInnerHTML — only use with sanitized content
import DOMPurify from 'dompurify';

function RichContent({ htmlContent }) {
  // Sanitize BEFORE rendering
  const clean = DOMPurify.sanitize(htmlContent, {
    ALLOWED_TAGS: ['b', 'i', 'em', 'strong', 'a', 'p', 'ul', 'li'],
    ALLOWED_ATTR: ['href', 'target'],
  });

  return <div dangerouslySetInnerHTML={{ __html: clean }} />;
}

// ✅ Validate URLs before using as href
function SafeLink({ url, children }) {
  const isSafeUrl = /^https?:\/\//i.test(url) || url.startsWith('/');
  if (!isSafeUrl) return <span>{children}</span>;
  return <a href={url}>{children}</a>;
}
```

### Authentication & Tokens

```js
// ✅ Store tokens in httpOnly cookies (backend sets these)
// Never localStorage for sensitive tokens if possible

// If you must use localStorage (SPAs without backend proxy):
// - Use short-lived access tokens
// - Implement refresh token rotation
// - Clear on logout

// ✅ Logout completely
function logout() {
  localStorage.removeItem('access_token');
  sessionStorage.clear();
  // Revoke token on server
  await apiClient.post('/auth/logout');
  // Clear React Query cache
  queryClient.clear();
  // Hard redirect (clears React state entirely)
  window.location.href = '/login';
}
```

### Content Security Policy

```html
<!-- Add via HTTP header (preferred) or meta tag -->
<meta http-equiv="Content-Security-Policy"
  content="
    default-src 'self';
    script-src 'self' 'nonce-{RANDOM_NONCE}';
    style-src 'self' 'unsafe-inline' https://fonts.googleapis.com;
    font-src 'self' https://fonts.gstatic.com;
    img-src 'self' data: https:;
    connect-src 'self' https://api.sandlipoasis.com;
    frame-ancestors 'none';
  "
/>
```

### Security Checklist

```
☐ Never store sensitive data (passwords, tokens) in localStorage unencrypted
☐ All external URLs are validated before being used in href/src
☐ dangerouslySetInnerHTML always paired with DOMPurify sanitization
☐ API keys are in environment variables (.env), never in source code
☐ Dependencies audited: pnpm audit (run weekly, fix critical vulnerabilities)
☐ HTTPS enforced in production (Strict-Transport-Security header)
☐ User input is validated on both client and server
☐ Sensitive forms have autocomplete="off" where appropriate
☐ No sensitive data logged to console.log in production
☐ Third-party scripts are audited and loaded from trusted sources
```

---

## 🧪 Testing

### Testing Philosophy

```
Testing Pyramid:
                ┌──────────┐
                │  E2E     │  ← Few, slow, high confidence (Playwright)
                │ Tests    │
               ┌┴──────────┴┐
               │Integration │  ← Some, tests component interaction
               │  Tests     │
              ┌┴────────────┴┐
              │  Unit Tests  │  ← Many, fast, focused (Vitest + RTL)
              └──────────────┘
```

### Unit & Integration Testing (Vitest + React Testing Library)

```jsx
// Button.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { describe, it, expect, vi } from 'vitest';
import Button from './Button';

describe('Button', () => {
  it('renders with correct label', () => {
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

  it('is disabled when disabled prop is true', () => {
    render(<Button disabled>Submit</Button>);
    expect(screen.getByRole('button')).toBeDisabled();
  });

  it('shows loading state', () => {
    render(<Button loading>Submit</Button>);
    expect(screen.getByRole('button')).toHaveAttribute('aria-busy', 'true');
    expect(screen.getByText('Submit')).toBeInTheDocument();
    expect(screen.getByRole('progressbar')).toBeInTheDocument();
  });
});
```

**Testing async components:**

```jsx
// UserProfile.test.jsx
import { render, screen, waitFor } from '@testing-library/react';
import { rest } from 'msw';
import { setupServer } from 'msw/node';
import UserProfile from './UserProfile';

// Mock the API with MSW
const server = setupServer(
  rest.get('/api/users/1', (req, res, ctx) => {
    return res(ctx.json({ id: 1, name: 'Amara', role: 'Senior Engineer' }));
  })
);

beforeAll(() => server.listen());
afterEach(() => server.resetHandlers());
afterAll(() => server.close());

describe('UserProfile', () => {
  it('shows loading skeleton initially', () => {
    render(<UserProfile userId={1} />);
    expect(screen.getByTestId('skeleton')).toBeInTheDocument();
  });

  it('renders user data after fetch', async () => {
    render(<UserProfile userId={1} />);
    
    await waitFor(() => {
      expect(screen.getByText('Amara')).toBeInTheDocument();
      expect(screen.getByText('Senior Engineer')).toBeInTheDocument();
    });
  });

  it('shows error state on API failure', async () => {
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

### E2E Testing (Playwright)

```js
// tests/e2e/auth.spec.js
import { test, expect } from '@playwright/test';

test.describe('Authentication', () => {
  test('user can log in with valid credentials', async ({ page }) => {
    await page.goto('/login');

    await page.getByLabel('Email address').fill('amara@sandlipoasis.com');
    await page.getByLabel('Password').fill('securepassword');
    await page.getByRole('button', { name: /sign in/i }).click();

    await expect(page).toHaveURL('/dashboard');
    await expect(page.getByText('Welcome back, Amara')).toBeVisible();
  });

  test('shows error for invalid credentials', async ({ page }) => {
    await page.goto('/login');

    await page.getByLabel('Email address').fill('wrong@example.com');
    await page.getByLabel('Password').fill('wrongpassword');
    await page.getByRole('button', { name: /sign in/i }).click();

    await expect(page.getByRole('alert')).toContainText('Invalid email or password');
    await expect(page).toHaveURL('/login');
  });
});
```

### Testing Checklist

```
Unit Tests
☐ All utility functions are unit tested
☐ Custom hooks are tested with renderHook
☐ Edge cases and error paths are covered

Component Tests
☐ Components render correctly with required props
☐ User interactions (click, type, submit) are tested
☐ Loading, error, and empty states are tested
☐ Accessibility is verified with jest-axe

E2E Tests
☐ Critical user journeys are covered (login, checkout, etc.)
☐ Tests run against a staging environment
☐ Tests are part of CI pipeline

Coverage Targets
☐ Utilities: 95%+
☐ Components: 80%+
☐ Integration: key flows covered
```

---

## 🔍 Debugging Workflows

### Browser DevTools Mastery

```
Elements Panel
  → Inspect and live-edit HTML/CSS
  → Test responsive views (device emulation)
  → Audit accessibility (Accessibility tab)
  → Computed styles and box model visualization

Console
  → console.table(arrayOfObjects)  — tabular view of data
  → console.group('Label') / console.groupEnd()  — organize logs
  → console.time('label') / console.timeEnd('label')  — timing
  → console.trace()  — call stack trace
  → $0  — reference last clicked element in Elements
  → queryObjects(ClassName)  — find all instances of a class

Network Panel
  → Filter by type: XHR/Fetch for API calls
  → Throttle to simulate slow connections (3G, offline)
  → Inspect request/response headers and body
  → Right-click → "Copy as cURL" to reproduce in terminal

Performance Panel
  → Record page interactions
  → Identify long tasks (>50ms) in the flame chart
  → Find layout thrash and style recalculations
  → Memory leaks

Application Panel
  → Inspect localStorage, sessionStorage, cookies
  → Clear site data for a clean state
  → Service Workers and cache inspection
```

### React Developer Tools

```
Components Tab
  → Inspect props and state of any component
  → Trigger re-renders to test behavior
  → Find what caused a re-render (highlight updates)

Profiler Tab
  → Record an interaction
  → See which components re-rendered and why
  → Identify rendering bottlenecks
  → Flame chart: time spent in each component
```

### Debugging Checklist

```
Before asking for help:
☐ Reproduce the bug in isolation (minimal repro)
☐ Check the browser console for errors
☐ Verify the correct data is being passed (console.log, DevTools)
☐ Check the Network tab for failed API requests
☐ Confirm the component's state matches expectations
☐ Read the error message in full — don't just scan it
☐ Check git blame — when did this code last change?
☐ Search the codebase for related error text
```

---

## 🚢 Deployment

### Environment Strategy

```
local       → Developer machine (localhost)
development → Feature branch deployments (Vercel/Netlify preview)
staging     → Pre-production mirror (manual QA + automated tests)
production  → Live user traffic (auto-deploy from main)
```

### Environment Variables

```bash
# .env.example — commit this; document all vars
VITE_API_BASE_URL=https://api.sandlipoasis.com
VITE_APP_ENV=production
VITE_SENTRY_DSN=
VITE_ANALYTICS_KEY=

# .env.local — never commit; personal overrides
VITE_API_BASE_URL=http://localhost:3001
```

```js
// config/env.js — centralize and validate at startup
const requiredVars = ['VITE_API_BASE_URL'];

for (const varName of requiredVars) {
  if (!import.meta.env[varName]) {
    throw new Error(`Missing required environment variable: ${varName}`);
  }
}

export const config = {
  apiBaseUrl: import.meta.env.VITE_API_BASE_URL,
  isDev: import.meta.env.DEV,
  isProd: import.meta.env.PROD,
};
```

### CI/CD Pipeline (GitHub Actions)

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

      - name: Type check
        run: pnpm tsc --noEmit

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
Pre-deploy
☐ All tests passing in CI
☐ Bundle size reviewed (no unexpected increases)
☐ Core Web Vitals checked on staging
☐ Accessibility audit run (Lighthouse)
☐ Security headers configured
☐ Environment variables set in target environment
☐ Feature flags configured correctly

Post-deploy
☐ Monitor error tracking (Sentry) for 30 minutes
☐ Verify Core Web Vitals in production
☐ Check critical user journeys manually
☐ Confirm analytics/tracking events firing
```

---

## 📐 Coding Standards & Conventions

### Naming Conventions

```js
// Variables and functions — camelCase
const userProfile = {};
function fetchUserData() {}

// React components — PascalCase
function UserProfileCard() {}
const UserProfileCard = () => {};

// Constants — SCREAMING_SNAKE_CASE
const MAX_RETRY_ATTEMPTS = 3;
const API_TIMEOUT_MS = 5000;

// CSS classes — kebab-case (BEM)
.user-card {}
.user-card__header {}
.user-card--featured {}

// Files
// Components: PascalCase
UserProfileCard.jsx
UserProfileCard.test.jsx
UserProfileCard.module.css

// Non-component JS: camelCase
apiClient.js
useAuthStore.js
formatCurrency.js

// Pages: PascalCase (they are components)
DashboardPage.jsx
SettingsPage.jsx
```

### Code Style Rules

```js
// ✅ Prefer explicit over clever
// ❌ Clever but unreadable
const result = arr.reduce((a, b) => ({...a, [b.id]: b}), {});

// ✅ Clear
const result = {};
for (const item of arr) {
  result[item.id] = item;
}

// ✅ Functions do one thing
// ❌ Overloaded function
async function handleUser(user, action) {
  if (action === 'save') { ... }
  else if (action === 'delete') { ... }
  else if (action === 'notify') { ... }
}

// ✅ Separate functions
async function saveUser(user) { ... }
async function deleteUser(userId) { ... }
async function notifyUser(userId) { ... }

// ✅ Early returns over deep nesting
// ❌ Nested hell
function processOrder(order) {
  if (order) {
    if (order.isValid) {
      if (order.items.length > 0) {
        // actual logic buried 3 levels deep
      }
    }
  }
}

// ✅ Guard clauses
function processOrder(order) {
  if (!order) throw new Error('Order is required');
  if (!order.isValid) throw new ValidationError('Invalid order');
  if (!order.items.length) throw new Error('Order has no items');

  // Clean, focused logic here
}
```

---

## 🚨 Common Mistakes & Anti-Patterns

### HTML Anti-Patterns

```html
<!-- ❌ Div soup -->
<div class="button" onclick="submit()">Submit</div>
<!-- ✅ Use semantic elements -->
<button type="submit">Submit</button>

<!-- ❌ Missing label (inaccessible) -->
<input type="text" placeholder="Enter email" />
<!-- ✅ Associated label -->
<label for="email">Email</label>
<input type="text" id="email" placeholder="Enter email" />

<!-- ❌ Inline styles -->
<p style="color: red; font-size: 14px;">Error message</p>
<!-- ✅ Use classes -->
<p class="error-message">Error message</p>
```

### CSS Anti-Patterns

```css
/* ❌ !important as a first resort */
.button { color: red !important; }

/* ❌ Overly specific selectors */
div.page > ul.nav-list > li.nav-item > a.nav-link { }

/* ❌ Magic numbers */
.element { margin-top: 37px; }

/* ❌ Hardcoded colors (not using variables) */
.button { background: #1a73e8; }

/* ✅ */
.button { background: var(--color-primary); }
```

### JavaScript Anti-Patterns

```js
// ❌ Mutating state or function arguments
function addUser(users, user) {
  users.push(user);  // Mutates original array
  return users;
}

// ❌ Callback hell
fetchUser(id, function(user) {
  fetchPosts(user.id, function(posts) {
    fetchComments(posts[0].id, function(comments) {
      // ← You've entered the pyramid of doom
    });
  });
});

// ❌ Swallowing errors silently
try {
  await doSomething();
} catch (e) {} // ← Error eaten alive

// ❌ Comparing floating point directly
0.1 + 0.2 === 0.3  // false!
// ✅
Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON

// ❌ Using var
var x = 1;

// ❌ == instead of ===
if (x == '1') {}
```

### React Anti-Patterns

```jsx
// ❌ Direct state mutation
state.items.push(newItem);  // Will NOT trigger re-render
setItems(state.items);

// ✅ Create new reference
setItems([...state.items, newItem]);

// ❌ Derived state in useState (gets out of sync)
const [firstName, setFirstName] = useState('Amara');
const [fullName, setFullName] = useState('Amara Osei'); // ← Duplicated

// ✅ Derive it
const [firstName, setFirstName] = useState('Amara');
const [lastName, setLastName] = useState('Osei');
const fullName = `${firstName} ${lastName}`; // Derived

// ❌ useEffect for data transformation
useEffect(() => {
  setFilteredItems(items.filter(i => i.active));
}, [items]);

// ✅ Derive it
const filteredItems = items.filter(i => i.active); // Just compute it

// ❌ Missing cleanup in useEffect
useEffect(() => {
  const interval = setInterval(tick, 1000);
  // ← Missing return () => clearInterval(interval)
}, []);

// ❌ Object/array as useEffect dependency without useMemo
useEffect(() => {
  fetchData(options);
}, [{ userId, page }]); // New object on every render → infinite loop!
```

---

## ✅ Frontend Project Checklist

### Before Development Starts

```
☐ Requirements are clarified and signed off
☐ Design mockups reviewed and accessible assets provided
☐ API contracts defined (OpenAPI spec or agreed endpoints)
☐ Project folder structure set up per this guide
☐ Linting, formatting, and pre-commit hooks configured
☐ CI/CD pipeline established
☐ Environment variables documented in .env.example
```

### During Development

```
☐ Semantic HTML used throughout
☐ Components are accessible (keyboard, ARIA, focus management)
☐ Responsive on mobile, tablet, and desktop
☐ Loading, error, and empty states handled
☐ Forms have proper validation and error messages
☐ No console.log statements in production code
☐ No hardcoded colors, sizes, or magic numbers
☐ No commented-out code blocks
☐ API errors are caught and surfaced to the user
```

### Pre-PR Checklist

```
☐ Code is self-reviewed (read your own diff first)
☐ Unit tests written for new logic
☐ Tests passing locally (pnpm test)
☐ Linting passing (pnpm lint)
☐ Build succeeds (pnpm build)
☐ Tested in Chrome, Firefox, and Safari
☐ Tested on mobile viewport (DevTools device emulation)
☐ Accessibility checked (keyboard navigation + screen reader)
☐ No new bundle size regressions (check with import cost)
```

### Pre-Launch Checklist

```
☐ Lighthouse audit: Performance ≥ 90, Accessibility = 100
☐ Core Web Vitals in green on real devices (PageSpeed Insights)
☐ CSP headers configured
☐ Error tracking (Sentry) connected and tested
☐ Analytics events verified
☐ Favicon and OG meta tags in place
☐ robots.txt and sitemap.xml present
☐ 404 page implemented
☐ All environment variables set in production
☐ Final E2E test run against production URL
```

---

## 📚 Recommended Libraries & Ecosystem

### Core Libraries

| Category | Library | Notes |
|---|---|---|
| **Framework** | React 18 | Concurrent features, transitions |
| **Build Tool** | Vite | Fast dev server, modern bundling |
| **Routing** | React Router v6 | Data loaders, nested routes |
| **Server State** | TanStack Query v5 | Caching, background refetch |
| **Client State** | Zustand | Minimal boilerplate, great DX |
| **Forms** | React Hook Form | Performant, schema validation |
| **Validation** | Zod | TypeScript-first schema validation |
| **Styling** | CSS Modules + CSS Variables | Scoped styles, no runtime |
| **UI Primitives** | Radix UI | Accessible, unstyled headless components |
| **Icons** | Lucide React | Consistent, tree-shakeable icon set |
| **Animations** | Framer Motion | Production-grade animations |
| **HTTP** | Axios or native Fetch | Prefer native Fetch with wrapper |
| **Date/Time** | date-fns | Lightweight, tree-shakeable |
| **Testing** | Vitest + RTL | Fast, Vite-native test runner |
| **E2E Testing** | Playwright | Cross-browser, robust, modern |
| **API Mocking** | MSW (Mock Service Worker) | Network-level API mocking |
| **Documentation** | Storybook | Component documentation and development |
| **Error Tracking** | Sentry | Production error monitoring |
| **Analytics** | PostHog | Open-source, privacy-respecting |

### TypeScript (Strongly Recommended)

```tsx
// Define prop types with interfaces
interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'ghost' | 'danger';
  size?: 'sm' | 'md' | 'lg';
  loading?: boolean;
  disabled?: boolean;
  onClick?: (event: React.MouseEvent<HTMLButtonElement>) => void;
  children: React.ReactNode;
  className?: string;
}

function Button({
  variant = 'primary',
  size = 'md',
  loading = false,
  disabled,
  onClick,
  children,
  className,
}: ButtonProps) {
  return (
    <button
      className={`btn btn--${variant} btn--${size} ${className ?? ''}`}
      disabled={disabled || loading}
      aria-busy={loading}
      onClick={onClick}
    >
      {loading && <Spinner size="sm" />}
      {children}
    </button>
  );
}
```

---

## 🗺️ Developer Roadmaps

### Junior Frontend Engineer Path

```
Month 1–2: Foundations
  ├── HTML5 semantics and accessibility basics
  ├── CSS3: Box model, Flexbox, Grid, responsive design
  ├── JavaScript: ES6+, DOM manipulation, async/await
  └── Git basics: branching, committing, PRs

Month 3–4: React Fundamentals
  ├── Components, JSX, props, state
  ├── Core hooks: useState, useEffect, useRef
  ├── React Router: nested routes, params
  └── Forms: controlled inputs, validation

Month 5–6: Building Real Features
  ├── API integration with React Query
  ├── Error handling and loading states
  ├── Component testing with RTL
  └── Deploy a complete feature end-to-end
```

### Mid-Level Frontend Engineer Path

```
Deepen Fundamentals
  ├── TypeScript: interfaces, generics, utility types
  ├── Advanced hooks: useCallback, useMemo, useReducer
  ├── Custom hooks: extract, reuse, test
  └── Performance: profiling, memoization, code splitting

Architecture & Patterns
  ├── Component patterns: compound, render props, HOC
  ├── State management: Context, Zustand, Redux Toolkit
  ├── Accessibility: WCAG 2.1 AA compliance
  └── Testing: integration tests, E2E with Playwright

Craft & Standards
  ├── Code review: giving and receiving feedback
  ├── Technical documentation
  ├── Performance optimization: Core Web Vitals
  └── Security: XSS, CSRF, CSP
```

### Senior Frontend Engineer Path

```
Technical Leadership
  ├── System design: scalable frontend architecture
  ├── Design system creation and governance
  ├── Performance engineering at scale
  └── Cross-team API design and contracts

Engineering Culture
  ├── Mentoring junior and mid-level engineers
  ├── RFC (Request for Comments) writing
  ├── Driving technical standards and conventions
  └── Incident response and post-mortems

Advanced Topics
  ├── Micro-frontends
  ├── SSR/SSG/ISR with Next.js
  ├── Web Workers and Worklets
  ├── WebAssembly
  └── Build tool internals (Rollup, esbuild)
```

---

## 🎯 Interview Preparation

### Core Topics

**HTML/CSS:**
- Explain the CSS cascade, specificity, and inheritance
- How does Flexbox differ from Grid? When do you use each?
- What are semantic elements and why do they matter?
- Explain responsive design and mobile-first approach
- What is the critical rendering path?

**JavaScript:**
- Explain closures with a practical example
- What is the event loop? How does `async/await` work under the hood?
- Explain `this` in different contexts
- What is prototypal inheritance?
- Difference between `==` and `===`; when does type coercion happen?
- Explain `var`, `let`, `const` and their scoping rules

**React:**
- What is the Virtual DOM and how does reconciliation work?
- Explain the rules of hooks
- When would you use `useCallback` vs `useMemo`?
- What is the difference between controlled and uncontrolled components?
- How does React's Context API differ from state management libraries?
- Explain the `useEffect` dependency array and cleanup

**System Design:**
- How would you architect a real-time chat application?
- Design a component library from scratch
- How would you implement infinite scroll at scale?
- Design an authentication system for a SPA

### Practical Exercises

```
☐ Build a debounced search with API integration (no libraries)
☐ Implement a custom useLocalStorage hook
☐ Create a reusable Modal component (focus trap, keyboard nav)
☐ Build a responsive data table with sorting and pagination
☐ Implement an infinite scroll list with React Query
☐ Write unit tests for a custom hook
☐ Debug and fix a React performance issue using the profiler
```

---

## 🎓 Learning Resources

### Official Documentation (Start Here)

| Resource | URL |
|---|---|
| MDN Web Docs | https://developer.mozilla.org |
| React Documentation | https://react.dev |
| Can I Use | https://caniuse.com |
| web.dev by Google | https://web.dev |
| TC39 Proposals (JS futures) | https://github.com/tc39/proposals |
| WCAG Guidelines | https://www.w3.org/WAI/WCAG21/quickref/ |

### Books Worth Reading

| Book | Why |
|---|---|
| *JavaScript: The Good Parts* — Crockford | Core JS design philosophy |
| *Clean Code* — Uncle Bob | Writing maintainable code |
| *Designing Data-Intensive Applications* — Kleppmann | System thinking for engineers |
| *The Pragmatic Programmer* — Hunt & Thomas | Engineering mindset |

### Tools for Practice

| Resource | Purpose |
|---|---|
| **CSS Tricks** | CSS guides and demos |
| **JavaScript.info** | Best modern JS tutorial |
| **React Patterns** | Advanced React patterns |
| **VisBug** | Design debugging in browser |
| **Excalidraw** | Diagram your architecture |
| **Bundle Phobia** | Check npm package sizes |

---

## 🤝 Contribution Guidelines

### Contributing to This Handbook

This document is a living guide. Every Sandlip Oasis frontend engineer is empowered to improve it.

**How to contribute:**

1. Open an issue describing what's missing, incorrect, or unclear
2. Fork the repository and create a `docs/` branch
3. Make your changes with clear, concise writing
4. Submit a PR with a description of what was changed and why
5. At least one senior engineer must review documentation PRs

**What makes a good contribution:**
- Fixes an inaccuracy or outdated information
- Adds a real-world example from experience
- Improves clarity without adding length
- Fills a genuine knowledge gap

**What not to contribute:**
- Content that duplicates existing material
- Opinionated preferences without team consensus
- Content copy-pasted from external sources

### Code of Conduct in Reviews

- Be specific and actionable ("This should use `useCallback` because X" not "this is wrong")
- Distinguish between blocking issues and suggestions
- Use "we" not "you" ("We prefer const here..." not "You should use const...")
- Acknowledge good work, not just problems
- Review the code, not the person

---

## 📎 Appendix

### Useful Snippets Reference

```js
// Debounce
const debounce = (fn, ms) => {
  let t; return (...args) => { clearTimeout(t); t = setTimeout(() => fn(...args), ms); };
};

// Throttle
const throttle = (fn, ms) => {
  let last = 0;
  return (...args) => {
    const now = Date.now();
    if (now - last >= ms) { last = now; fn(...args); }
  };
};

// Deep clone (when structuredClone isn't available)
const deepClone = (obj) => JSON.parse(JSON.stringify(obj));

// Class names helper (poor man's clsx)
const cn = (...classes) => classes.filter(Boolean).join(' ');

// Sleep (for testing/demo purposes only)
const sleep = (ms) => new Promise(resolve => setTimeout(resolve, ms));

// Truncate text
const truncate = (str, maxLength) =>
  str.length > maxLength ? `${str.slice(0, maxLength)}…` : str;

// Format file size
const formatBytes = (bytes) => {
  if (bytes === 0) return '0 B';
  const k = 1024;
  const sizes = ['B', 'KB', 'MB', 'GB'];
  const i = Math.floor(Math.log(bytes) / Math.log(k));
  return `${parseFloat((bytes / k ** i).toFixed(2))} ${sizes[i]}`;
};
```

---

<div align="center">

---

**Sandlip Oasis Engineering**

Built with care by the Sandlip Oasis frontend engineering team.

*This handbook is maintained as a living document. Last substantive revision tracked in git history.*

*If something is wrong, outdated, or missing — open an issue. We build this together.*

---

> *"Any fool can write code that a computer can understand. Good programmers write code that humans can understand."*
> — Martin Fowler

</div>
