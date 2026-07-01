Ascend — Personal Growth Hub
A complete personal improvement and productivity web app that runs entirely in the browser. No backend, no API keys, no build steps — just open the file and start building better habits.

Features
Daily Summary
A unified dashboard for any given date. See your routine logs, habit completion ring, brain dump entries, task progress by category, and long-term goal milestones — all in one scrollable view. Navigate between days with arrow buttons or the date picker.

Hourly Routine with Time Blocks
Time Blocks — Club consecutive hours under a single label. Set "Sleep" from 10 PM to 7 AM (overnight spans supported), "Office Work" from 9 AM to 12 PM, etc. Each block gets a color, and blocked hours are visually grouped in the timeline with a colored left border and header.
Per-Hour Notes — Tap any hour (blocked or free) to add a specific note about what you did. Notes layer on top of block labels.
Live Preview — When creating or editing a block, a 24-hour grid highlights the selected hours and flags conflicts with existing blocks.
Date Navigation — Review or log past days with the date picker.
Habit Tracker
Weekly grid view (Mon–Sun) for each habit.
Toggle completion for any past day.
Reminder System — Enable a reminder per habit with a custom time. Reminders fire as in-app toasts and browser notifications (permission requested automatically).
Add custom habits with an icon picker (24 icons available).
Brain Dump
A zero-friction idea capture input. Type and press Enter — that's it. Entries are timestamped and displayed newest-first. Delete what you no longer need.

To-Do List
Three categories: Work, Personal, Financial — each color-coded.
Three priority levels: High (red), Medium (gold), Low (green).
Filter by category with live counts.
Completed tasks collapse into a toggleable section.
Tasks are priority-sorted automatically.
Vision Board
A masonry grid of text and image cards representing your goals and aspirations.

Text cards — Choose from 8 accent colors.
Image cards — Paste any image URL or generate a random one from Picsum.
Hover to reveal the delete button. Add cards via a clean modal.
Long Term Goal Planner
Create goals with a title, description, and target deadline.
Each goal shows a progress bar and days-remaining counter.
Expand a goal to reveal its milestone checklist.
Add, check off, or remove milestones inline.
Overdue goals are flagged in red.
Tech Stack
Layer	Choice
Styling	Tailwind CSS (CDN)
Fonts	Space Grotesk (headings) + DM Sans (body) via Google Fonts
Icons	Font Awesome 6
Storage	localStorage — all data persists across sessions
Notifications	Browser Notification API
Build	None — single HTML file
Getting Started
Save the index.html file anywhere.
Open it in a modern browser.
That's it.
No server, no npm install, no configuration.

For local development with live reload:

# Using Pythonpython3 -m http.server 8000# Using Node.js (npx)npx serve .# Using PHPphp -S localhost:8000
Then open http://localhost:8000 in your browser.

Data & Privacy
Everything stays on your device. No data is sent to any server.
All state is serialized to localStorage under the key ascend_state.
To back up your data, open DevTools → Application → Local Storage → copy the ascend_state value.
To reset, delete the ascend_state key or run localStorage.removeItem('ascend_state') in the console and refresh.
Browser notifications require user permission — the app requests it once when you enable the first habit reminder.
Default Data
The app ships with starter data so it doesn't feel empty on first load:

2 time blocks: Sleep (10 PM–7 AM), Office Work (9 AM–12 PM)
5 habits: Morning Meditation, Exercise, Read 30 Minutes, Journal, Drink 8 Glasses Water
6 vision cards: A mix of text goals and images
2 long-term goals: Learn Spanish (4 milestones) and Run a Marathon (4 milestones)
Delete or customize anything to make it yours.

Browser Support
Works in all modern browsers:

Chrome / Edge 90+
Firefox 90+
Safari 15+
Mobile Chrome / Safari (responsive layout with bottom tab bar)
Customization
Color Palette
The entire theme uses CSS custom properties via Tailwind config. Edit the tailwind.config object in the <script> tag to change colors:

js

colors: {
  bg: '#0C0C0C',        // Page background
  card: '#161616',       // Card background
  elevated: '#1E1E1E',   // Modal/input background
  border: '#2A2826',     // Borders
  fg: '#F0EBE3',         // Primary text
  muted: '#7A756C',      // Secondary text
  accent: '#D4A04A',     // Primary accent (gold)
  // ...
}
Time Block Colors
The BC array at the top of the script defines the 8 colors available for time blocks.

Habit Icons
The HI array lists the 24 Font Awesome icons shown in the habit icon picker.

File Structure
text

ascend/
└── index.html    ← Everything lives here
Single-file architecture. No dependencies to manage, no bundler output, no node_modules.

Known Limitations
No cloud sync — data is device-local only. Manual export/import if you switch devices.
No recurring tasks — to-dos are one-time entries.
Notification timing — reminders check every 15 seconds, so they may fire up to 15 seconds late. Browser throttling may further delay notifications when the tab is in the background.
Storage limit — localStorage typically allows 5–10 MB. Brain dump images are stored as URLs, not base64, so this is unlikely to be an issue.
License
This project is provided as-is for personal use. Feel free to modify, extend, and redistribute