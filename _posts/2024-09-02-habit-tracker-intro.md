---
title: "Introducing the Year of Done's first project: A Habit Tracker"
tags:
  - yearofdone
date: 2024-09-02
---
The year of done has begun, and so it's time to start working on the first project. For this month, I want to build a self hosted habit tracker. Why a habit tracker? Because I haven't found any that suit what I want from one. My ADHD gets awful sometimes, and I'll just forget to do things if I'm not prompted. For a while, I was using a repeating task and having Thunderbird remind me on my PC, but that has a pretty tragic flaw: What if I fail? Thunderbird was connected to a CalDAV server, and and so the only options are Completed or Not. If I didn't do it, then I don't want to check it off, it opens the door to allowing myself to check stuff off without having done it elsewhere. The only other option, then, is to delete the missed tasks, which is annoying in its own right. That system is, frankly, annoying, I don't want to deal with it anymore. So I'm building my own.

## Requirements

The goal is a opinionated, no-nonsense habit tracker that understands that things happen. Streaks are Fomo, and if you mess up a long one, that's liable to be more harmful than if it wasn't tracked at all. However, watching a consistency rate rise? That will feel good.

So here are my goals:

- Add habits with varying repeat styles.
    - Daily, Weekly, X number of days/weeks, Monthly on X day, Monthly on Xth day of week.
- Each habit should have a start, reminder/due, and expiry.
    - Start date/time specifies the earliest the habit should reasonably be done. You should not be getting ready for bed at 2 PM
    - Expiry date/time specifies the point at which the habit is considered missed. You cannot take your morning meds at 2PM. Reminders for it should cease.
- The front page should hold a list of incomplete habits which have started and not expired
- Notifications should be persistent, yet snoozeable.
    - If I just close the notification without snoozing it, it should come back relatively quickly. (Treat as 2 min snooze)
    - Habits should have a "Last chance" Where if the snooze would push it past this time (5 min before expiry by default?) That snooze instead occurs here.
    - Notifications will, for now, be handled by sending calls to ntfy, as that's the notification stack I'm using. We'll see where that goes. 
- Each habit should track completion history. This can then be calculated into a consistency %, which can also be tracked on the home page, both per habit and overall.
- Primarily focused on Desktop view, but the Mobile experience should be decent as well.
## Tech stack

This is subject to change, but here's what I'm thinking so far

- SQLite DB
- Flask Backend
- React Frontend

There's a lot to do, so I'd better get started!