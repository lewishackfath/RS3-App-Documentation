---
icon: lucide/arrow-down-up
---

# Clan Scraper/API
The Clan Scraper/API is used to collect RuneMetrics Data on the members of configured clans.

## Collected Data
- XP Snapshots
- Activity Logs
- Clan Ranking & Rank Up Notifications
- Citadel Cap/Visit Log

## Features

### Citadel Cap/Visit Logging
The scrapper will collect clan member citadel visits and cap logs, they are posted to the "discord log channel" that is configured in the database as well as announced in the "discord announcement channel".

### Clan Ranking and Rank Up Notifications
The Clan Members Rank is collected and stored in the Main Member Database. This is used in conjunction with the capping data to and the configured "Max Rank by Capping" field to determine if a player is eligible to be ranked up post cap.

### Activity Log
The Members activity logs are collected and stored for use with the Clan Tracker site. The Activity log is also used in conjuction with the announcement system for announcing level ups, boss drops, quest completions etc.

### XP Snapshots
This data is collected and stored with a timestamp for use in the Clan Tracker site.