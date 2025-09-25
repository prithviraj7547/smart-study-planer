Smart Study Planner — Modern, Local-First Study Organizer

A lightweight, browser-based study planner built with HTML, CSS, and JavaScript.
Designed to help students organize study schedules, manage tasks, set reminders, and track progress. All data is saved locally so you can use it offline and keep control of your information.

Author: PRITHVIRAJ CHAUHAN
College: Mangalmay Institute of Engineering and Technology
Department: CSE

Key Features

Landing dashboard with quick stats: total tasks, today's tasks, upcoming reminders, and progress percent

Create and manage study plans and tasks:

Task title, subject, priority, due date/time, estimated duration, notes

Repeating tasks (daily, weekly, custom)

Visual timeline and calendar view:

Day, week, and month views

Drag to reschedule (optional UX enhancement)

Timers and study sessions:

Pomodoro-style timer with configurable work and break lengths

Start/pause/reset controls and session history

Reminders and notifications:

In-app reminders and optional browser notifications

Snooze and mark-as-done from the notification UI

Goal tracking and progress:

Mark tasks complete, view completion rate per subject

Weekly/monthly progress charts

Local persistence:

Save all data in Local Storage

Export and import planner data as JSON

Reports:

Downloadable summary report (.txt or .json) of completed tasks and study time

Responsive, mobile-first UI with accessible controls

How to Use

Open index.html in your browser.

Enter your name and optionally set your semester or course.

Create subjects or categories (for example: Maths, DSA, Physics).

Add study tasks with due dates and priorities.

Use the calendar or timeline to view and organize tasks.

Start a study session with the timer and mark tasks complete when done.

Export your planner data or download a report when needed.

Project Structure

index.html — Single page app entry

style.css — Responsive, modern styles

script.js — App logic, Local Storage handling, timers, reminders, UI interactions

assets/ — icons, images, fonts

README.md — Project documentation

data/sample-data.json — Example dataset for quick start (optional)

Implementation Notes
Data model (example)

Store planner data as nested JSON in Local Storage under the key smartStudyPlanner_v1.

{
  "user": { "name": "Prithviraj Chauhan", "course": "BTech CSE", "college": "Mangalmay Institute of Engineering and Technology" },
  "subjects": [
    { "id": "maths", "title": "Mathematics" }
  ],
  "tasks": [
    {
      "id": "t1",
      "title": "Linear Algebra revision",
      "subjectId": "maths",
      "priority": "High",
      "due": "2025-09-28T18:00:00",
      "durationMin": 60,
      "repeat": "weekly",
      "notes": "Practice past year questions",
      "completed": false
    }
  ],
  "sessions": [
    { "taskId": "t1", "start": "2025-09-25T15:00:00", "end": "2025-09-25T16:00:00" }
  ]
}

Core modules in script.js

Storage module: saveState() and loadState() wrappers around Local Storage

Task manager: create, read, update, delete tasks and subjects

Calendar/timeline renderer: day/week/month templates

Timer module: Pomodoro logic and session recording

Reminder/notification service: in-app alerts and Notification API integration

Export/import: downloadJSON() and loadFromFile() utilities

Customization

Add subjects and task templates in script.js under defaultState.

Swap styles in style.css to match your branding or dark mode preferences.

Replace Local Storage with IndexedDB if you need larger storage or more complex queries.

Integrate a backend or sync service later (Google Drive, OneDrive, or Firebase) if you want cross-device sync.

Accessibility and UX tips

Ensure interactive elements use semantic HTML (button, form, label) and keyboard focus states.

Provide ARIA labels for calendar controls and timer buttons.

Use high contrast text and scalable fonts for readability on mobile.

Troubleshooting

Planner not saving:

Check browser Local Storage quota and browser privacy settings.

Open DevTools console to see any errors.

Browser notifications not showing:

Confirm you granted notification permission for the site.

Notifications only work on secure contexts (http on localhost or https).

Calendar rendering issues:

Verify task due fields are valid ISO datetime strings.

Example Quick Start

Clone the folder or save the files locally.

Open index.html in Chrome, Edge, or Firefox.

Add a subject, create a task with a due date, then start the Pomodoro timer.

Mark the task complete and download your report from Results -> Export.

Future Enhancements

Integrate study material links and attachments per task

Add spaced repetition algorithm for flashcard-style review

Sync across devices with a simple backend

Collaborative study groups and shared planners

Analytics dashboard with heatmaps for study time

License

MIT License
