# Quickstart: Initial Portfolio Build

This guide provides the steps to set up and run the development environment for the portfolio project.

## Prerequisites

- Node.js (v18 or later)
- npm or yarn

## 1. Initial Setup

### Clone and Install Dependencies

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/arjun-dev/portfolio-2025.git
    cd portfolio-2025
    ```

2.  **Install project dependencies**:
    ```bash
    npm install
    ```

    This will install React, Vite, TailwindCSS, DaisyUI, and other required packages.

## 2. Running the Development Server

To start the local development server with Hot Module Replacement (HMR):

```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the next available port).

## 3. Component Development with Storybook

Storybook is used to develop and document UI components in isolation.

To run the Storybook server:

```bash
npm run storybook
```

Storybook will be available at `http://localhost:6006`. New components (Atoms, Molecules, Organisms) should be created here first, following the Atomic Design methodology.

## 4. Building for Production

To create a production-ready build of the application:

```bash
npm run build
```

The optimized and bundled files will be placed in the `dist/` directory.

## 5. Running End-to-End Tests

This project uses Playwright for end-to-end testing.

1.  **Install Playwright browsers** (one-time setup):
    ```bash
    npx playwright install
    ```

2.  **Run tests**:
    ```bash
    npx playwright test
    ```

3.  **View the test report**:
    ```bash
    npx playwright show-report
    ```

## Development Workflow Summary

1.  Create or select a feature branch (e.g., `002-add-blog-section`).
2.  Create new components in Storybook (`npm run storybook`).
3.  Integrate components into pages/sections in the main app (`npm run dev`).
4.  Write tests for new functionality.
5.  Submit a Pull Request for review.
