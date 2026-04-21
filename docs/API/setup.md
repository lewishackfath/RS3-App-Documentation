---
icon: lucide/settings
---

# Setup

## Config
The config file is primarily used to connect to the Database as well as some other low level settings for Rank Ordering.
``` php
<?php
// public_html/config/config.php

return [

  /* =========================================================
   * DATABASE
   * ======================================================= */
  'db' => [
    'host'    => 'localhost',
    'name'    => '',
    'user'    => '',
    'pass'    => '',
    'charset' => 'utf8mb4',
    'options' => [
      PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
      PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
      PDO::ATTR_EMULATE_PREPARES   => false,
    ],
  ],

  /* =========================================================
   * APPLICATION
   * ======================================================= */
  'app' => [
    'environment' => 'production', // production | staging | dev
    'timezone'    => 'UTC',
    'debug'       => false,

    // Used for hashing activity / snapshot dedupe
    'hash_algo'   => 'sha256',
  ],

  /* =========================================================
   * POLLING / CRON BEHAVIOUR
   * ======================================================= */
  'polling' => [
    'default_interval_seconds' => 300,   // fallback if no poll_state exists
    'retry_backoff_seconds'    => 900,   // used after 429s
    'max_consecutive_429'      => 5,
  ],

  /* =========================================================
   * RANKING / GAME LOGIC (STATIC)
   * ======================================================= */
  'ranks' => [
    // Ordered lowest → highest
    'order' => [
      'Recruit',
      'Corporal',
      'Sergeant',
      'Lieutenant',
      'Captain',
      'General',
      'Coordinator',
      'Overseer',
      'Deputy Owner',
      'Owner',
    ],
  ],

  /* =========================================================
   * DISCORD (GLOBAL)
   * ======================================================= */
  'discord' => [
    'bot_token'    => '',
    'x_bot_token'  => '',

    // Safety / rate limits (global, not per clan)
    'max_message_length' => 1900,
  ],

];
```
## Add New Clan to Database
```SQL
INSERT INTO `clans` (
	`id`,
	`name`,
	`timezone`,
	`reset_weekday`,
	`reset_time`,
	`max_rank_by_capping`,
	`discord_guild_id`,
	`discord_log_channel_id`,
	`discord_ping_channel_id`,
	`discord_announcement_channel_id`,
	`discord_ping_role_ids_json`,
	`is_enabled`,
	`created_at`,
	`updated_at`,
	`inactive_at`
) 
VALUES (
	'', -- Clan ID (Auto Increment)
	'Clan Name', -- Clan Name exactly as it appears in Runescape eg. 24K, RS3 Vikings etc.
	'UTC', -- Timezone that the clan wishes to use (UTC is Gametime)
	'3', -- Day of the Week for Cap Reset (0 - 7, Sunday - Saturday) Eg. 3 = Wednesday
	'16:20:00', -- Cap Reset Time in the Clans Local Timezone Eg. 16:20:00 is 4:20pm.
	'Captain', -- Maximum Rank achieveable via Capping. Set this to whatever Rank players can be promoted too from Capping Alone if capping promotion isn't used set to Recruit
	'["Role ID 1","Role ID 2","Role ID 3"]', -- Discord Guild ID - This is the Server ID of your Clans Discord Server
	'0', -- Discord Log Channel - This is where Caps and Visit logs are sent too
	'0', -- Discord Ping Channel - This is where Rank Up Pings are Sent Eg. 24K Lodo has capped and needs to be promoted to God of the Universe.
	'0', -- Discord Announcement Channel - This is for Player Facing announcements it shows configurable announcements for things like drops, level ups, quest completions etc.
	'TBA', -- An Array of Roles that are tagged/pinged when a rank up is required, these roles also give access to bot commands in the discord server.
	'1', -- Is Active Set to 1 unless clan no longer is used.
	current_timestamp(3), -- Current Timestamp for Creation
	current_timestamp(3), -- Current Timestamp for Last Update
	NULL -- Innactive At Current Timestamp NULL for New Clann
)
```

