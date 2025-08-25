# Companion Module: Calendar Assistant

This module monitors an iCal feed and provides boolean feedbacks indicating whether there is an event currently happening, or within configurable time windows before/after the event, at a specified location. The feedbacks can be used within Bitfocus Companion to trigger actions automatically based on your schedule.

---

## Configuration

1. **iCal Feed URL** – Enter the URL of your iCal feed (supports `webcal://` and `https://`).
2. **Location Text** – Enter the text to look for in the event’s location. For example, entering `F-111 Chapel` will look for events whose location contains that text (case insensitive).
3. **Time A (Before/After)** – Number of minutes before/after an event to consider the event “active” for the **Time A feedback**.
4. **Time B (Before/After)** – Number of minutes before/after an event to consider the event “active” for the **Time B feedback**.
5. **Refresh Interval** – How often to refresh the calendar feed, in minutes (1–1440 minutes).

---

## Feedbacks

- **Location Event – Time A**  
  Returns `true` when the current time is within the **Time A window** (before, during or after an event) **and** the event’s location contains the configured text.  

- **Location Event – Time B**  
  Returns `true` when the current time is within the **Time B window** (before, during or after an event) **and** the event’s location contains the configured text.  

---

## Actions

- **Refresh Calendar** – Manually refreshes the iCal feed.  
- **Check Current Matching Events** – Logs any current events that match the configured location.

---

## Variables

When a matching event is active or upcoming, the following variables are available:

- `$(calendarassistant:match_event_name)` – Name of the matching event (or "No Match").  
- `$(calendarassistant:match_event_start_date)` – Start date (YYYY-MM-DD) of the current matching event.  
- `$(calendarassistant:match_event_start_time)` – Start time (HH:MM) of the current matching event.  
- `$(calendarassistant:match_event_end_date)` – End date (YYYY-MM-DD) of the current matching event.  
- `$(calendarassistant:match_event_end_time)` – End time (HH:MM) of the current matching event.  
- `$(calendarassistant:timeA_active)` – `true`/`false` if any event is active in the **Time A window**.  
- `$(calendarassistant:timeB_active)` – `true`/`false` if any event is active in the **Time B window**.  

---

## Using Feedbacks with Triggers

To automate actions based on your calendar:

1. Go to the **Triggers** tab in Companion.  
2. Create a new trigger with **+ Add**.  
3. Select **Feedback state**.  
4. Choose **Location Event – Time A** or **Location Event – Time B**, depending on which time window you want.  
5. Add the actions you want to execute when the feedback becomes active/inactive.  

---

## Support

Developed by **DbAV (dbav.co)**  
Author: **Davis B** – [davisb@dbav.co](mailto:davisb@dbav.co)  

If you have questions or suggestions about this module, please contact the developer directly.