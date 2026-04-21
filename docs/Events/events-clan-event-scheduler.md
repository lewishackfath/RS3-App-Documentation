---
icon: lucide/calendar-range
---

# Clan Event Scheduler
The event scheduler allows to to create clan event listings which are displayed on the website, in a weekly summary discord post and in the daily event posts.

## Events Homepage
The events website homepage will display the scheduled events for the current week and the ability to view past and future scheduled events. A logged in user will also be able to edit, cancel and delete events.

## Admin Interface
The admin interface consists of several sections

### Login/Authentication
Logging in to the admin interface is done by clicking the login button in the uper right of the screen. Authentication is via discord server role permissions for the configured guild.

### Discord Publishing
The discord publishing page allows you to run the update sync, or post the daily event listings if the Cron job fails to complete or is missed. you can also run this for a future week/day if needed. You can also sync missing items.

For the most part this page will not be needed as the cron will handle the majority of the functions that are availiable on this page.