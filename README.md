# Gantt Chart Editor

A lightweight, interactive Gantt chart that runs entirely in a single HTML file — no install, no server, no dependencies. Open `index.html` in any modern browser and start planning.

---

## How to Use

### Getting started
1. Download or clone this repository.
2. Open `index.html` in your browser.
3. The chart loads with sample tasks. Replace them with your own.

### Managing tasks
- Click **+ Add Task** to append a new row.
- Edit a task name directly in the table or by clicking the label on the chart.
- Pick start and end dates using the date pickers in each row.
- Enter a **Progress** value (0–100) to track completion.
- Click **✕** to delete a task.
- Use the **▲ / ▼** buttons or drag the grip handle to reorder tasks.

### Working with the chart
- **Move a bar** — click and drag it left or right to shift both dates.
- **Resize a bar** — drag the left or right edge to adjust the start or end date independently.
- **Open bar menu** — click a bar without dragging to get link / unlink options.
- **Link a bar** — links the task visually to the one above it with a connector line and indents its label.

### Saving and loading
- Click the **Export** button (floppy-disk icon) to download the chart as a `.json` file.
- Click the **Import** button (download icon) to load a previously exported `.json` file.

### Printing
- Click the **Print** button to open the browser print dialog.
- The chart automatically scales to fit A4 landscape and hides all controls, leaving only the timeline.

---

## Features

### Task management
- Add, rename, delete, and reorder tasks
- Drag-and-drop reordering in both the task table and the chart
- Progress tracking per task (0–100 %) with a visual fill on each bar

### Interactive chart
- Drag bars horizontally to move tasks to new dates
- Resize bars from either edge to extend or shorten a task
- Click a bar to open a context menu for linking / unlinking
- Linked tasks display a connector line to the task above and receive an indented label

### Timeline display
- Month and day headers that auto-fit to your date range
- Today's date highlighted with a distinct column
- Weekend columns shaded for easy visual separation
- Sticky task labels so names stay visible while scrolling horizontally

### Chart title
- Click the title at the top to rename the chart inline

### Toggle view
- Hide or show the task table without losing data

### Import / Export
- Export the full chart (title + all tasks) to a `.json` file
- Re-import any previously exported `.json` to restore the chart

### Print
- One-click print in landscape mode
- Auto-scales content to fit A4 width
- Prints only the timeline — controls are hidden
