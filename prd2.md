# Product Requirements Document

**App:** *(Unnamed — working title: "SmartDo")*
**Version:** 1.0 (MVP)
**Date:** February 26, 2026
**Timeline:** 1–2 weeks

---

## 1. Product Overview

**Product Name:** SmartDo *(working title)*

**One-Sentence Description:** A web-based student task manager that automatically organizes deadlines into a prioritized, one-at-a-time view — so students spend less time feeling overwhelmed and more time actually working.

**Positioning Statement:** For secondary students who struggle to start tasks when faced with overlapping deadlines, SmartDo is a scheduling tool that pre-organizes their workload by priority and availability — unlike passive to-do lists, it removes the mental burden of deciding what to do next.

---

## 2. Target User

**Name:** pj/null
**Age / Grade:** 14 / Grade 9
**Tech Literacy:** High — already uses phone alarms and calendar apps as coping tools

### Context
pj/null is a Grade 9 student who performs well at school but struggles to initiate work at home. They have unstructured afternoon time (3:30–10:00 PM) but lose a significant portion of it to mental recovery from the school day. They prefer working on one thing at a time and experience cognitive shutdown when confronted with multiple overlapping tasks.

### Key Constraints
- Unreliable memory — knows they can't trust themselves to remember everything
- Low activation energy — needs a very low-friction path to starting work
- Current tools (alarms, calendar) are too blunt or too far ahead to help with day-to-day task initiation

### Goals
- Know exactly what to work on next without having to think about it
- Feel in control of their workload rather than buried by it
- Produce good-quality work without last-minute panic

### Frustrations
- Forgetting individual deadlines when multiple subjects pile up simultaneously
- Feeling paralyzed when looking at a full list of tasks with no clear starting point
- Lacking the motivation to maintain complex organizational systems

---

## 3. Problem Statement

Secondary students like pj/null do not lack the ability to do their work — they lack a reliable system to tell them **what to do first**. When multiple deadlines converge across subjects, the cognitive load of mentally sorting and prioritizing tasks creates a feeling of overwhelm that delays task initiation entirely.

### Evidence
From a real student interview conducted February 2026:
> *"I forgot my science test today because I have 5 things due this week from all subjects — it was difficult to digest all the information at the same day."*

> *"Having the energy or motivation to quickly do it before it's due... I can get good work but it takes me a bit because I procrastinate."*

Supporting perspective (Sam, Grade 11):
> *"I tend to get it done anyway since I feel as if I don't have much of a choice, but feel a sense of dread while doing said assignment as if I'm running out of time."*

### Core Problem
Existing tools (alarms, calendar apps, mental memory) are either too general, too far ahead, or require too much ongoing effort to maintain. There is no tool that takes a student's deadlines and available time and simply tells them: **"Here is what you should do today."**

---

## 4. Proposed Solution

### Core Approach
SmartDo asks students to input their tasks and deadlines once during a simple onboarding flow. It then automatically organizes those tasks by priority — surfacing the single most important task for today's available time, rather than displaying an overwhelming full list.

### Key Features (v1)
- **Schedule Onboarding:** Student marks which days are busy and roughly how many hours are available — creates a personal availability profile
- **Task Entry:** Student inputs task name, subject, type (assignment or project), and deadline
- **Auto-Prioritization:** App ranks tasks by deadline proximity, task type, and available days — no manual sorting required
- **Single-Focus View:** Dashboard defaults to showing the highest-priority task first, with the full list accessible but not the default view
- **In-App Visual Nudges:** A visible indicator (banner or badge) alerts the student when a deadline is approaching — achievable within a web interface without requiring push notifications

### Key Differentiator
Unlike standard to-do apps that list everything at once and leave prioritization to the student, SmartDo **pre-decides the order** and presents a focused, one-task-at-a-time view — directly addressing the cognitive shutdown pj/null experiences when overwhelmed.

---

## 5. Scope

### Included in v1
- ✅ Schedule setup / availability onboarding
- ✅ Task entry (name, subject, type, deadline)
- ✅ Automatic prioritization based on deadline and availability
- ✅ Single-focus dashboard view (highest priority task surfaced first)
- ✅ Full task list accessible via toggle
- ✅ In-app visual nudges for approaching deadlines
- ✅ Simple user accounts (email + password, persistent login)
- ✅ Calendar view *(only if time permits within the 1–2 week timeline)*

### Explicitly Excluded from v1
- ❌ Mobile app (iOS / Android)
- ❌ Push notifications or email reminders (web infrastructure complexity)
- ❌ Collaboration or group tasks
- ❌ AI-generated study schedules
- ❌ Grade tracking
- ❌ Third-party integrations (Google Calendar, Canvas, etc.)
- ❌ Estimated time-to-complete per task

> These may be revisited in v2 depending on timeline and user feedback.

---

## 6. Success Criteria

The MVP is considered successful if the following outcomes are measurable:

1. **Reduced decision friction:** A student can open the app and immediately identify their single highest-priority task in **under 30 seconds** — without needing to read through a full task list.

2. **Pre-organized workload reduces overwhelm:** After entering their tasks for the week, the student's workload is visibly organized and prioritized ahead of time — the student should not need to manually sort or re-arrange anything.

3. **Usability threshold:** At least one real student (matching pj/null's profile) uses the app across a full school week and reports that it felt **less overwhelming** than their previous system (alarms, mental memory, or blank notes).

---

## Vision Summary

pj/null is a capable Grade 9 student whose academic performance is undermined not by a lack of ability, but by the cognitive burden of managing multiple overlapping deadlines without a reliable system. When faced with a full list of tasks and no clear starting point, their mind shuts down before they even begin. Existing tools — alarms, calendar apps, mental memory — are either too blunt, too far ahead, or demand more ongoing effort than a student with low activation energy can sustain. SmartDo fills this gap by taking the organizational thinking off the student's plate entirely: tasks go in, priorities come out, and the student is shown exactly what to work on next — one task at a time, matched to their actual availability.
