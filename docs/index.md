---
icon: lucide/hand
---

# Welcome
The Lodo bot is broken up into several different modules which are deployed individually but share common data.

## Clan Scraper/API
The Scraper/API pulls data from the RuneScape 3 Servers using a number of different API Endpoints and collates it into a large database.

## Clan Tracker
The Clan Tracker is a website, that allows members of your clan to login and view the data that is being collected by the Clan Scraper/API.
It basically creates a human readable interface for the API Data collected.

## Clan Bingo
Clan Bingo is a website that hooks into the Clan Tracker database to allow members of any configured/tracked clan to play in a friendly/competitive game of Bingo using item drops.
This app tracks drops from bosses using the runemetrics drop log and as such some items are not able to be detected automatically and must be manually marked off. The system hooks into the GE item database so only items on the GE can be selected.

## Clan Ranking
The Clan ranking website allows for automatic discord role changes based on Ranks in the RuneScape clan. This uses discord Nickname matching to identify RSN's but can also be hard configured in the application configuration.

## Clan Events
This allows for the automated scheduling and creation of Clan events within discord including automated creation of voice channels, discord events and allows role selection through reaction tags.