# Tasks: Initial Portfolio Build (MVP)

**Input**: Design documents from `specs/001-portfolio-atomic-design/`
**Prerequisites**: plan.md, spec.md, data-model.md

**Tests**: Test tasks are not included as they were not explicitly requested. Component testing will be done via Storybook.

**Organization**: Tasks are grouped by user story (or foundational component phase) to enable independent implementation and testing.

## Format: `[ID] [P?] [Story] Description`
- **[P]**: Can run in parallel
- **[Story]**: Which user story this task belongs to (e.g., US1, US2)

---
## Phase 1: Setup (Shared Infrastructure)
**Purpose**: Project initialization and basic structure.

- [ ] T001 Initialize Vite + React + TypeScript project in `H:\portfolio\`
- [ ] T002 Install core dependencies: `react`, `react-dom`, `gsap`, `react-icons`, `lucide-react`, `react-hook-form`, `@hookform/resolvers`, `yup`, `@emailjs/browser` in `H:\portfolio\package.json`
- [ ] T003 Install dev dependencies: `tailwindcss`, `postcss`, `autoprefixer`, `daisyui`, `storybook`, `playwright` in `H:\portfolio\package.json`
- [ ] T004 [P] Configure TailwindCSS by creating `H:\portfolio\tailwind.config.js` and `H:\portfolio\postcss.config.js`
- [ ] T005 [P] Configure DaisyUI themes within `H:\portfolio\tailwind.config.js`
- [ ] T006 [P] Initialize Storybook configuration in `H:\portfolio\.storybook\`
- [ ] T007 [P] Create the Atomic Design folder structure inside `H:\portfolio\src\` (`components/atoms`, `components/molecules`, etc.)
- [ ] T008 [P] Create the initial data folder and files: `src/data/projects.ts`, `src/data/skills.ts`, `src/data/about.ts`

---
## Phase 2: Foundational Atoms
**Purpose**: Build the smallest, most reusable UI components. These are prerequisites for molecules and organisms.

- [ ] T009 [P] Create the `Button` atom in `src/components/atoms/Button/Button.tsx` and its Storybook story.
- [ ] T010 [P] Create the `Typography` atom in `src/components/atoms/Typography/Typography.tsx` and its Storybook story.
- [ ] T011 [P] Create the `Icon` atom in `src/components/atoms/Icon/Icon.tsx` as a wrapper for `react-icons`.
- [ ] T012 [P] Create the `Badge` atom in `src/components/atoms/Badge/Badge.tsx` and its Storybook story.
- [ ] T013 [P] Create the `Avatar` atom in `src/components/atoms/Avatar/Avatar.tsx` and its Storybook story.
- [ ] T014 [P] Create the `Link` atom in `src/components/atoms/Link/Link.tsx` and its Storybook story.
- [ ] T015 [P] Create the `Card` atom in `src/components/atoms/Card/Card.tsx` as a base container.
- [ ] T016 [P] Create the `Switch` atom in `src/components/atoms/Switch/Switch.tsx` for the theme toggle.
- [ ] T017 [P] Create the `Input` and `Textarea` atoms in `src/components/atoms/Input/` for forms.
- [ ] T018 [P] Create the `Skeleton` atom in `src/components/atoms/Skeleton/Skeleton.tsx` for loading states.

---
## Phase 3: User Story 1 - View Professional Identity (Hero) 🎯 MVP
**Goal**: Create the initial impression for visitors with a dynamic hero section and functional navigation.
**Independent Test**: The `HomePage` can be loaded to view the Navbar and Hero section, and theme toggling is functional.

### Implementation for User Story 1
- [ ] T019 [P] [US1] Create the `ThemeToggle` molecule in `src/components/molecules/ThemeToggle/ThemeToggle.tsx` using the `Switch` and `Icon` atoms.
- [ ] T020 [P] [US1] Create the `NavItem` molecule in `src/components/molecules/NavItem/NavItem.tsx` using `Link` and `Typography`.
- [ ] T021 [US1] Create the `Navbar` organism in `src/components/organisms/Navbar/Navbar.tsx` using `NavItem` and `ThemeToggle`.
- [ ] T022 [P] [US1] Create the `CTAButton` molecule in `src/components/molecules/CTAButton/CTAButton.tsx`.
- [ ] T023 [P] [US1] Create the `SocialLinks` molecule in `src/components/molecules/SocialLinks/SocialLinks.tsx`.
- [ ] T024 [US1] Implement the GSAP typing animation utility in `src/utils/animations.ts`.
- [ ] T025 [US1] Create the `Hero` organism in `src/components/organisms/Hero/Hero.tsx` using `Typography`, `CTAButton`, `SocialLinks` and the typing animation.
- [ ] T026 [US1] Create the main `HomePage` in `src/components/pages/HomePage/HomePage.tsx` and integrate the `Navbar` and `Hero` organisms.
- [ ] T027 [US1] Implement the theme state management using a hook `src/hooks/useTheme.ts` and apply it.

---
## Phase 4: User Story 2 - Understand the Developer's Background (About)
**Goal**: Display the developer's bio, image, and key stats.
**Independent Test**: The About section renders correctly on the `HomePage` when scrolled to.

### Implementation for User Story 2
- [ ] T028 [P] [US2] Create the `StatCard` molecule in `src/components/molecules/StatCard/StatCard.tsx`.
- [ ] T029 [US2] Create the `About` organism in `src/components/organisms/About/About.tsx` using `Avatar`, `Typography`, `Badge`, and `StatCard`.
- [ ] T030 [US2] Populate `src/data/about.ts` with the developer's bio and statistics.
- [ ] T031 [US2] Integrate the `About` organism into `src/components/pages/HomePage/HomePage.tsx`.

---
## Phase 5: User Story 3 - Evaluate Technical Skills (Skills)
**Goal**: Display a grid of technical skills with proficiency levels.
**Independent Test**: The Skills section renders correctly on the `HomePage` with data from the `skills.ts` file.

### Implementation for User Story 3
- [ ] T032 [P] [US3] Create the `SkillCard` molecule in `src/components/molecules/SkillCard/SkillCard.tsx`.
- [ ] T033 [US3] Create the `SkillsGrid` organism in `src/components/organisms/SkillsGrid/SkillsGrid.tsx` which maps over `SkillCard` components.
- [ ] T034 [US3] Populate `src/data/skills.ts` with the list of skills.
- [ ] T035 [US3] Integrate the `SkillsGrid` organism into `src/components/pages/HomePage/HomePage.tsx`.

---
## Phase 6: User Story 4 - Assess Practical Experience (Projects)
**Goal**: Showcase a portfolio of projects with links to demos and code.
**Independent Test**: The Projects section renders project cards correctly, and links are functional.

### Implementation for User Story 4
- [ ] T036 [P] [US4] Create the `ProjectTag` molecule in `src/components/molecules/ProjectTag/ProjectTag.tsx`.
- [ ] T037 [US4] Create the `ProjectCard` organism in `src/components/organisms/ProjectCard/ProjectCard.tsx`.
- [ ] T038 [US4] Populate `src/data/projects.ts` with at least 5 projects.
- [ ] T039 [US4] Create a `ProjectsSection` organism in `src/components/organisms/ProjectsSection/ProjectsSection.tsx` that displays a grid of `ProjectCard`s.
- [ ] T040 [US4] Integrate the `ProjectsSection` into `src/components/pages/HomePage/HomePage.tsx`.

---
## Phase 7: User Story 5 - Get in Touch (Contact)
**Goal**: Allow users to send a message via a contact form.
**Independent Test**: The contact form validates input, handles errors, and successfully sends an email via EmailJS on submission.

### Implementation for User Story 5
- [ ] T041 [P] [US5] Create the `FormField` molecule in `src/components/molecules/FormField/FormField.tsx`.
- [ ] T042 [US5] Create the `ContactForm` organism in `src/components/organisms/ContactForm/ContactForm.tsx` using `react-hook-form`.
- [ ] T043 [US5] Integrate `EmailJS` service into the `ContactForm`'s submission logic.
- [ ] T044 [US5] Integrate a `reCAPTCHA` component into the `ContactForm` as per FR-010.
- [ ] T045 [US5] Implement success and error feedback (toast/alert) for form submission.
- [ ] T046 [US5] Integrate the `ContactForm` organism into `src/components/pages/HomePage/HomePage.tsx`.

---
## Phase 8: Polish & Cross-Cutting Concerns
**Purpose**: Finalize the application with remaining components, integrations, and deployment setup.

- [ ] T047 [P] Create the `Footer` organism in `src/components/organisms/Footer/Footer.tsx`.
- [ ] T048 Create the `HomeTemplate` in `src/components/templates/HomeTemplate/HomeTemplate.tsx` to structure the overall page layout.
- [ ] T049 Refactor `HomePage.tsx` to use the `HomeTemplate` and pass all section organisms as props.
- [ ] T050 [P] Implement smooth scrolling for navigation links in `Navbar.tsx` using GSAP `ScrollToPlugin`.
- [ ] T051 Setup Playwright by creating `playwright.config.ts` and adding a basic test for page load.
- [ ] T052 Setup `gh-pages` dependency and `deploy` scripts in `package.json` for deployment to GitHub Pages.

---
## Dependencies & Execution Order
- **Phase 1 (Setup)** must be completed first.
- **Phase 2 (Atoms)** can begin after Setup.
- **Phase 3 (US1)** depends on the completion of relevant Atoms from Phase 2.
- **Phases 4-7** can be worked on in parallel after their prerequisite atoms/molecules are complete, but a sequential P1->P5 order is recommended.
- **Phase 8 (Polish)** should be done last.

## MVP Scope
The minimum viable product consists of completing **Phase 3 (User Story 1)**. This delivers the core visual identity (Navbar + Hero) and proves the foundational component structure works.
