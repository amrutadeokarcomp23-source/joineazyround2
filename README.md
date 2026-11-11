# Joineazy

Joineazy is a responsive student and professor workspace for courses, assignment briefs, group coordination, and submission tracking. It builds on the supplied Round 1 React + Vite + Tailwind project and uses a localStorage mock API so the demo works without a server.

Live video: https://submitly-assignment-dashboard.vercel.app/
Demo video: https://drive.google.com/file/d/1cW4ImA9eo37O2F8FTeE9-5O67oSSz7_h/view?usp=drive_link


## Run locally

Requires Node.js 18 or newer.

```bash
npm install
npm run dev
```

Vite prints the local URL (normally `http://localhost:5173`). To make a production bundle:

```bash
npm run build
npm run preview
```

## Demo accounts

Choose the matching role on the sign-in screen. All seeded accounts use password `demo123`.

| Role | Email | Password |
|---|---|---|
| Student | `amruta@joineazy.edu` | `demo123` |
| Professor | `meera@joineazy.edu` | `demo123` |

Other seeded students: `rohan@joineazy.edu`, `sneha@joineazy.edu`, `aditya@joineazy.edu`, `pooja@joineazy.edu`. Another professor account is `rahul@joineazy.edu`.

Suggested demo: sign in as Amruta, open Data Structures & Algorithms, inspect the individual and group assignment details, then acknowledge the group assignment as its leader. Sign out, sign in as Meera, open the same course, and use **Track submissions** to see the roster and acknowledgement timestamp.

## What’s included

- Student and professor registration with required-field, email, password-length, duplicate-account, and role validation.
- Role-specific sign-in and protected workspace views. A simulated JWT-style token is saved in localStorage and cleared at sign-out.
- Course cards and course assignment pages with search, type/status filters, deadlines, overdue indicators, and responsive layouts.
- Professor assignment create, edit, delete, resource link, date/time, individual/group type, and submission roster drill-down.
- Student assignment detail with resource links and an individual confirmation step. Acknowledgements are stored with timestamps.
- Course groups with create/join, member list, leader identity, and leader-only group acknowledgement visible to every member.
- Seeded individual and group assignments, loading-ready states through the existing project components, empty-search state, toast feedback, and keyboard-dismissable dialogs.
- Persistent demo data in the browser. To reset seeded data, remove `joineazy.round2.data` and `joineazy.round2.session` from localStorage for the local site, then refresh.

## Design choices

The visual direction pairs a warm paper-like canvas with deep ink navigation, vivid violet and teal course accents, and a lime highlight for key actions. Course cards use soft color blooms and clear course codes; assignment rows foreground due dates and acknowledgement state. Dense professor tracking stays in a separate assignment detail view, while student actions are short and mobile-friendly.

The data model keeps users, courses, assignments, groups, individual acknowledgements, and group acknowledgements as separate collections. The group leader’s acknowledgement is attached to the group, so each member sees the same status and the professor can drill down by student. All data is browser-local; there is no production authentication, remote API, or cross-device sync.

## Component structure

```text
src/
├── main.jsx                 # React entry
├── App.jsx                  # Application entry component
├── Round2App.jsx            # Round 2 flows, local data, pages, and interactions
├── index.css                # Tailwind layers and visual system
├── context/AppContext.jsx   # Retained Round 1 context provider
├── components/              # Retained reusable Round 1 UI components
├── pages/                   # Retained Round 1 pages
├── data/seed.js             # Retained Round 1 sample data
└── utils/                   # Retained Round 1 storage and helper utilities
```

## Delivery notes

The project is ready for a GitHub repository and Vercel/Netlify build (`npm run build`, output folder `dist`). Publishing requires the user’s own GitHub and hosting accounts, so no repository, deployment, or video link is claimed here. No screenshots are included in this project folder yet.
