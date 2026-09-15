# Pankov Svyatoslav

**Frontend Developer**

---

## Contact Information

- 📧 Email: pankovslava94@gmail.com
- 📱 Phone: +7 (705) 865-74-99
- 📍 Location: Almaty, Kazakhstan
- 🔗 LinkedIn: [linkedin.com/in/svyatoslavpankov](https://www.linkedin.com/in/svyatoslavpankov/)
- 🐙 GitHub: [github.com/SlavaPankov](https://github.com/SlavaPankov)

---

## About me

Frontend developer with commercial experience building applications in Vue 3 and TypeScript, including work on a large shared component UI kit within a monorepo — both as a consumer of the library and as a contributor. My work goes beyond markup: it includes deep debugging, generic type systems, custom composables, CSS theming architecture, and build optimization.

In parallel, I'm developing my skills in React and backend development with Nest.js, building a personal project — a full multiplayer real-time application powered by Socket.IO. This gave me hands-on experience designing systems that span both frontend and backend: from type-safe socket event contracts to client-side state management patterns.

My priorities: writing maintainable, type-safe code, digging into root causes of bugs rather than patching symptoms, and continuously growing my stack — from the Vue ecosystem to React and server-side development.

---

## Skills

**Programming Languages** 
JavaScript (ES6+), TypeScript

**Frontend** 
Vue 3 (Composition API), React, Vite, SCSS/Sass, Zustand, HTML5/CSS3, responsive design

**Backend** 
Nest.js, Prisma ORM, Socket.IO, PostgreSQL, EventEmitter2

**Version Control:** 
Git (including monorepo workflows)

**Architecture & Patterns** 
Vue composables, custom React hooks, discriminated unions, Strategy pattern, design token / CSS custom property architecture, layered hook architecture

**Tools & Methodologies** 
Vite, Rollup, SonarQube, ESLint, code review, build tooling debugging
---

## Code Samples

**1. Vue 3 — masked input composable (`useMask`)**

```ts
// useMask.ts (simplified fragment)
const EMPTY_SLOT = '_'
 
export const useMask = (mask: Ref<string>, modelValue: Ref<string>) => {
  const rawValue = ref(modelValue.value)
 
  const applyPositionalValidation = (input: string): string => {
    return input
      .split('')
      .map((char, i) => (isValidForSlot(char, mask.value[i]) ? char : EMPTY_SLOT))
      .join('')
  }
 
  watch(modelValue, (val) => {
    rawValue.value = applyPositionalValidation(val)
  }, { immediate: true })
 
  return { rawValue }
}
```

**2. TypeScript — discriminated union for a type-safe `onSubmit`**

A pattern that prevents type narrowing from breaking when form props are destructured:

```ts
type RoomFormSubmit =
  | { mode: 'create'; payload: CreateRoomDto }
  | { mode: 'edit'; payload: EditRoomDto; roomId: string }
 
interface RoomFormProps {
  onSubmit: (data: RoomFormSubmit) => void
}
 
// Important: do NOT destructure data.payload at the onSubmit call site,
// or TS loses the link between the mode discriminant and the payload type
```

**3. SCSS — generating button variants from a Sass map**

```scss
$button-variants: (
  primary: var(--ui-primary),
  danger: var(--ui-error),
);

@each $name, $color in $button-variants {
  .ui-button--#{$name} {
    background-color: $color;
  }
}
```

---

## Experience

### IKOD — Frontend Developer (2024 – Present)

### Project: IDMX

- Lead a full rewrite of the 125-page IDMX application from Vue 2 + Webpack to Vue 3 (Composition API) + TypeScript + Vite over 9 months, cutting the production build time from 76s to ~10s (~7x faster).
- Implement new features and maintain existing functionality for the IDMX access management system, working across the frontend stack (Vue 3, TypeScript, Vue Router, Pinia).
- Review teammates' pull requests, enforcing code quality, architectural consistency, and team conventions across the codebase.
- Drive architectural decisions for the application — component composition patterns, state-management structure, and build/tooling choices — balancing maintainability with delivery speed.
- Migrated the codebase to TypeScript 6.0, resolving `vue-tsc`/`typescript-eslint` peer conflicts, a `baseUrl` deprecation, and `noUncheckedSideEffectImports` issues.
- Fixed a production file-download bug caused by axios response interceptors corrupting blob data, and resolved Outlook Desktop rendering issues in HTML email templates (VML button fallback).

### @ikod/ui-kit — Shared Component Library

- Build and maintain the component base of `@ikod/ui-kit` — a library of 50 Vue 3 (Composition API) components consumed by 4 applications across the company.
- Architected a monorepo of 5 `@ikod`-scoped packages, configuring Rollup build pipelines per package and setting up the npm publishing workflow.
- Built the component library's documentation site with VitePress, giving consuming teams a single reference for usage and APIs.
- Own architectural decisions for the library — design-token conventions, package structure, and multi-theme CSS architecture.
- Review code across the component library, catching regressions and enforcing consistency before release.
- Covered the component base with unit tests, reaching 99.3% coverage and reducing regression risk for consuming applications.
- Designed a `useMask` composable powering masked inputs (`UiInput`, `DateTimePicker`) and refactored an SCSS button component using Sass maps and `@each` loops.
- Resolved generic TypeScript typing issues in `ui-select`/`ui-select-generic`, fixed CSS `:deep()` scoping leaks, and solved a `vite-plugin-dts`/Rollup version conflict blocking the build pipeline.

### IKOD — OutSystems Developer (2022 – 2024)

- Built and shipped software solutions on the OutSystems low-code platform for a banking client (FICO).
- Automated banking business processes, data models, and user interfaces, streamlining workflows for end users.
- Extended OutSystems' native capabilities by building custom Java extensions for requirements the platform couldn't cover out of the box.
- Worked within a cross-functional development team across the full software development lifecycle.

### Personal Project: Multiplayer Card Game
*React (frontend) + Nest.js, Prisma, Socket.IO (backend)*

**Frontend (React)**
Source code: [Github](https://github.com/SlavaPankov/spy-goat-frontend)

- Implemented an app-level singleton socket established after authentication; split `SocketContext`/`SocketProvider` for Vite Fast Refresh compatibility.
- Built a Zustand `presenceStore` with reference counting to prevent duplicate subscription events.
- Designed a discriminated union for `RoomForm`'s `onSubmit` prop, keeping the type-narrowing intact instead of breaking it on destructure.
- Built a layered React hook architecture for chat: `useChatMessages`, `useChatSocket`, `useChatAudio`, `useChatInput`, `useChatUnread`, `useChatScroll`, `useChat`.
- Implemented a `ChatContextMenu` using `createPortal` with viewport boundary adjustment.
- In progress: client-side dual-token JWT authentication (in-memory access token, HttpOnly-cookie refresh token)

**Backend (Nest.js, Prisma, Socket.IO)**
Source code: [Github](https://github.com/SlavaPankov/spy-goat-backend)

- Designed and built a Nest.js backend with Prisma ORM and Socket.IO for real-time gameplay.
- Implemented a bot system using the Strategy pattern (Random / Balanced / Lookahead).
- Built a room invitation system: direct invites and shareable token links.
- Built an online presence system via `ConnectionGateway`, `PresenceService`, and `EventEmitter2`.
- Designed `Message`/`MessageRead` models for a full chat system: soft delete, AES-256-GCM encryption, cursor-based pagination.

---

## Education

**Nizhny Novgorod State Technical University**
Bachelor's degree, Power Machinery Engineering — 2012 - 2016

**Additional training:**
- Skillbox - Web Developer, 2020
- RSSchool - JavaScript/Frontend, 2023 Q1
- RSSchool - React, 2023 Q4
- RSSchool - Node.js, 2024 Q3

---

## English Proficiency

**Level:** B2

**Language Practice:** studied English at the "Just Speak It" language school