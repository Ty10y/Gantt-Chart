# Gantt Chart Editor

A lightweight, interactive Gantt chart that runs entirely in a single HTML file. No install, no server, no build step. Open `index.html` in any modern browser, or use the hosted version at <https://ty10y.github.io/Gantt-Chart/>, and start planning.

**Current version: v3**

---

## Getting Started

1. Download or clone this repository.
2. Open `index.html` in your browser.
3. The chart loads with sample tasks that start today. Replace them with your own.

Your work is not saved automatically. Use **Export JSON** to save a chart and **Import JSON** to open it again.

---

## Managing Tasks

### The task table

| Column | What it does |
|---|---|
| **Task Name** | Type to rename. You can also click a name on the chart to edit it there. |
| **Start / End** | Date pickers in Dates view, day numbers in Weeks view. Changing one edits that edge of the task. |
| **Duration** | Length in calendar days. Typing a duration moves the end date and keeps the start. |
| **Progress** | 0–100 %. Shown as the filled portion of the bar. |
| **Actions** | Reorder (▲ / ▼), color and options (●), convert to milestone (◆), and delete (✕). |

- Click **+ Add Task** to add a row.
- Drag the grip handle (⋮⋮) to reorder tasks, in the table or on the chart.
- **Right-click a row** for a quick **Delete Task** option. While you are typing in a field, right-click still gives the browser's normal copy/paste menu.
- If an end date is earlier than its start date, the fields turn red and the bar is drawn with a red dashed outline until it is fixed.
- Click the list icon to hide or show the table without losing any data.

### Milestones

Milestones are single-date events such as a design review, a FAT, or a ship date. They appear as diamonds on the chart.

- Click **◆** in the Actions column, or choose **Convert to Milestone** from the bar menu.
- A milestone's end date follows its start date, and it has no duration.
- The diamond is hollow while pending and filled once progress is set to 100 %.
- Drag a diamond left or right to move it.

---

## Working With the Chart

- **Move a task.** Drag the bar left or right. Both dates shift together, so the duration stays the same.
- **Resize a task.** Drag the left or right edge of the bar to change the start or end date.
- **Open the bar menu.** Click or right-click a bar or diamond to:
  - **Link Bar / Unlink Bar.** Connects the task to the one above it with a connector line and indents its name.
  - **Convert to Milestone / Convert to Task.**
  - **Color.** Choose from 12 preset colors, or **Reset to Default Color**.
- **Resize the name column.** Drag the divider between the task names and the timeline.
- **Today** is highlighted in yellow. Weekends are shaded gray.
- Task names stay pinned on the left while you scroll the timeline horizontally.

### Colors

Every task and milestone can have its own color, picked from 12 screen-friendly presets. The color dot in the Actions column shows each task's current color, and clicking it opens the same menu. Colors appear on screen, in exports, and in saved JSON files. Default colors are blue for tasks, gray for linked tasks, and near-black for milestones.

---

## Dates View and Weeks View

Use the **Dates | Weeks** switch next to **+ Add Task** to change how the timeline is labeled.

### Dates view
The timeline shows months and calendar dates. Saturdays and Sundays are shaded.

### Weeks view
The timeline shows **Week 1, Week 2, Week 3…** across the top and **day numbers** counting up from Day 1 underneath, with no reset at the end of a month. This is useful for relative schedules such as "8 weeks after PO," before real dates are known.

- The first time you open Weeks view, the earliest task start becomes **Day 1**. Day 1 then stays fixed. Dragging tasks around never renumbers the days.
- Tasks moved before Day 1 show as Day 0, −1, −2 under Week 0, Week −1, and so on.
- Days 6 and 7 of every week are shaded as weekends.
- The table's Start and End columns switch to day numbers, so you can type "15" instead of picking a date.
- **+ Add Task** starts the new task the day after the last task ends, with a 5-day duration, so you can build a sequence quickly.
- The **↺ button** (Weeks view only) renumbers the days so the earliest task becomes Day 1 again. Tasks keep their calendar dates.
- Hover over a day number to see its real calendar date.

Tasks always keep their real dates behind the scenes. Switching back to Dates view shows exactly the dates you would expect, and switching back to Weeks view keeps the same Day 1.

---

## Shift Schedule

Use the **calendar button with the ▶ icon** (available in both views) to move the whole project at once, for example when a start is delayed from October 1 to October 20.

- **Project start** (labeled **Day 1** in Weeks view): pick the new start date.
- **Or shift by _ days**: enter how far to move. Negative numbers move the schedule earlier.

The two fields stay in sync, and a preview line confirms the change before anything happens (for example, "Moves all 5 tasks 19 days later"). Click **Shift** or press **Enter** to apply. Press **Escape** or **Cancel** to close without changes.

Every task, milestone, and Day 1 moves together. Durations, gaps, links, colors, and day numbers are preserved.

---

## Saving and Loading

- **Export JSON** (floppy-disk icon) downloads the chart as a `.json` file. The file includes the title, all tasks, colors, milestones, the current view, and Day 1.
- **Import JSON** (download icon) opens a previously exported file. Files from older versions still load.
- If a file can't be imported, an error message explains why, for example invalid JSON, no task list, or a date that isn't in YYYY-MM-DD format.

---

## Exporting the Chart

Click the **Export Chart** button (printer icon) and choose one of:

| Option | Result |
|---|---|
| **Fit to One Page (PDF)** | The whole chart scaled to fit on one landscape page. |
| **Full Size, Multiple Pages (PDF)** | The chart at full readable size, split across as many pages as needed. Every page repeats the task names and date header. |
| **Download as Image (PNG)** | One full-resolution image with no page limits. |

Exports match the active view: dates in Dates view, weeks and day numbers in Weeks view. Pages are US Letter landscape, which also fits on A4.

> **Note:** PDF export uses the [jsPDF](https://github.com/parallax/jsPDF) library, which loads from the internet the first time you export. PNG export and everything else work offline.

---

## Chart Title

Click the title at the top of the page to rename the chart. The title is also used as the file name for exports.

---

## Version History

**v3**
- Weeks view with Week / Day numbering and a fixed Day 1
- Shift Schedule button to move the whole project in either view
- Duration column
- Milestones (diamonds)
- 12-color palette for tasks and milestones, with a color dot in the table
- Right-click menus on bars, milestones, and table rows
- Invalid date ranges are flagged in red
- Clear error messages when importing a bad file
- Fixed day labels and bar positions shifting after a daylight-saving time change
- Fixed task names containing quotes breaking the table
- Fixed linked task names overflowing onto the chart
