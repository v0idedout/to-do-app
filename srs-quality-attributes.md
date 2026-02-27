# Quality Attributes

> This file defines how well the app must perform. These are the standards
> the coding agent must follow when building the application. Every
> requirement is measurable — a tester can verify each one as pass or fail.

## App Context

- **App Name:** SkyBox
- **App Description:** Skybox is a todo list app run with the interface of inserting work and a calendar to track them. it tracks deadlines for assignments, but fluctuates when the user is avalible to do work according to their schedule.
- **Persona:** the target users are students, mainly in high school, who struggle with getting tasks done due to the mental struggle, setting up for overlapping deadlines, or their current systems not being specific enough to them.
- **Tech Stack:** Vanilla JavaScript, HTML, CSS — no frameworks, no package managers
- **Data Storage:** localStorage (browser-based, per-device)
- **Hosting:** Vercel (static site deployment)
- **Max Concurrent Users:** 30 (classroom setting)

---

## Usability

- A new user shall be able to complete the app's primary action within
  3 steps of opening the app, without needing a tutorial or instructions.
- All navigation shall be visible on screen — no hidden menus or gestures
  required to access core features.
- The app shall display clear confirmation feedback (a visible message or
  visual change) within 1 second of any user action (button click, form
  submission, data save).
- All text shall be at least 16px for body content and maintain sufficient
  line spacing (1.4 or higher) for readability.

## Reliability

- The app shall save all user data to localStorage immediately after every
  user action that changes data (no delayed auto-save). When the user
  returns to the app, their data shall be exactly as they left it.
- The app shall work consistently across the latest versions of Chrome,
  Firefox, and Edge without layout or functionality differences.
- If localStorage is unavailable or full, the app shall display a clear
  message to the user explaining the issue instead of silently failing
  or crashing.

## Scalability

- The app shall load and become interactive within 3 seconds on a standard
  school Wi-Fi connection.
- The app shall display correctly and remain fully functional on screens
  as small as 375px wide (iPhone SE) and as large as 1920px (desktop
  monitor).
- All images and assets shall be optimized so the total page weight does
  not exceed 3MB on any single view.

## Accessibility

- All text shall meet a minimum color contrast ratio of 4.5:1 against its
  background, per WCAG 2.1 AA standards.
- All interactive elements (buttons, links, form inputs) shall be reachable
  and operable using keyboard-only navigation (Tab to move, Enter to
  activate, Escape to close).
- Every interactive element shall have a visible focus indicator so keyboard
  users can see where they are on the page.
- All non-decorative images shall include descriptive alt text.
- All form inputs shall have associated labels (using the HTML <label>
  element or aria-label attribute).
- The app shall use semantic HTML elements (header, nav, main, section,
  button) instead of generic divs for all structural and interactive
  components.

## Security

- The app shall include a login screen where users enter their name and
  an access code to proceed. The default access code is `V01D3R`. This
  code can be changed by the student in the source code.
- The access code shall be stored as a single variable at the top of the
  main JavaScript file (or in a dedicated config section) so it is easy
  to find and change.
- The app shall validate all form inputs before processing them: reject
  empty submissions and limit text inputs to reasonable character lengths
  (e.g., 200 characters for names, 1000 for longer text fields).
- The app shall not store any data beyond what is needed for the app to
  function. No tracking, no analytics, no third-party scripts.

---

## Chaos Monkey Plan

> What happens when things go wrong? Instead of hoping nothing breaks,
> these requirements define how the app responds gracefully to the two
> most realistic failures it will face.

### Failure 1: localStorage Is Full or Unavailable

If localStorage is unavailable (private browsing mode, storage quota
exceeded, or browser restrictions), the app shall:

1. Detect the issue on startup by attempting a test write/read cycle.
2. Display a prominent banner at the top of the screen reading:
   "Your browser cannot save data right now. Your work will not be saved
   if you close this tab. Try using a regular browser window."
3. Allow the user to continue using the app for the current session
   without crashing — features that require saving shall show a warning
   icon next to them.

### Failure 2: User Loses Internet Connection

If the network connection drops while the user is using the app, the
app shall:

1. Continue functioning normally for all features that do not require
   a network connection (since the app is client-side with localStorage,
   most features should work offline).
2. If any feature requires a network request (e.g., loading external
   content), display a message: "You appear to be offline. Some features
   may be limited until your connection returns."
3. Not lose any data — since all data is stored locally, the user's
   work shall remain intact regardless of network status.