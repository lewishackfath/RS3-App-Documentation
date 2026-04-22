# Discord Death Counter Bot

The **Discord Death Counter Bot** allows server members to track their **RuneScape 3 boss deaths** using simple slash commands directly in Discord.

Members can:

- Add to their death count
- Set an exact death count
- Clear a death count
- View their death counts for a single boss or all bosses

Death counts are stored **per Discord server**, so the same member can have different totals in different communities.

---

## How It Works

The bot uses a **global RuneScape 3 boss list** and stores each member’s death counts against their Discord account **within the current server**.

All commands are run as **Discord slash commands**.

---

# Commands

## `/death add`

Adds a number to your existing death count for a selected boss.

### Usage

```text
/death add boss:<boss> amount:<number>
```

### Example

```text
/death add boss:Telos amount:1
```

### Result

If your current **Telos** death count is `4`, it will become `5`.

### Notes

- `boss` is selected from the bot’s boss list
- `amount` must be a positive whole number

---

## `/death set`

Sets your death count for a selected boss to an exact number.

### Usage

```text
/death set boss:<boss> amount:<number>
```

### Example

```text
/death set boss:Araxxor amount:27
```

### Result

Your **Araxxor** death count will be set to `27`, regardless of the previous value.

### Notes

- `boss` is selected from the bot’s boss list
- `amount` must be zero or higher

---

## `/death clear`

Clears your death count for a selected boss.

### Usage

```text
/death clear boss:<boss>
```

### Example

```text
/death clear boss:Solak
```

### Result

Your stored death count for **Solak** will be removed.

### Notes

- This only clears the selected boss
- It does not affect your counts for any other bosses

---

## `/deaths`

Displays your death counts.

By default, this command shows **all** of your tracked boss death counts.

### Usage

```text
/deaths
```

### Example

```text
/deaths
```

### Result

Shows a list of all bosses you have tracked deaths for, along with their current totals.

---

## `/deaths boss:<boss>`

Displays your death count for a single selected boss.

### Usage

```text
/deaths boss:<boss>
```

### Example

```text
/deaths boss:Vorago
```

### Result

Shows only your **Vorago** death count.

---

## `/deaths user:@member`

Displays all tracked death counts for another server member.

### Usage

```text
/deaths user:@member
```

### Example

```text
/deaths user:@Lewis
```

### Result

Shows all tracked boss death counts for the selected member within the current server.

---

## `/deaths boss:<boss> user:@member`

Displays the death count for a specific boss for another server member.

### Usage

```text
/deaths boss:<boss> user:@member
```

### Example

```text
/deaths boss:Zamorak user:@Lewis
```

### Result

Shows the selected member’s death count for that boss.

---

# Command Summary

| Command | Purpose |
|---|---|
| `/death add` | Add to your death count for a boss |
| `/death set` | Set your death count for a boss |
| `/death clear` | Clear your death count for a boss |
| `/deaths` | View all your death counts |
| `/deaths boss:<boss>` | View your death count for one boss |
| `/deaths user:@member` | View all death counts for another member |
| `/deaths boss:<boss> user:@member` | View one boss death count for another member |

---

# Examples

## Add a death

```text
/death add boss:Nex amount:1
```

## Set a death count

```text
/death set boss:Telos amount:14
```

## Clear a death count

```text
/death clear boss:Croesus
```

## View all your counts

```text
/deaths
```

## View one boss

```text
/deaths boss:Solak
```

## View another member’s counts

```text
/deaths user:@PlayerName
```

## View another member’s count for one boss

```text
/deaths boss:Raksha user:@PlayerName
```

---

# Notes

## Per-Server Tracking

Death counts are tracked **separately for each Discord server**.  
This means your counts in one server do not affect your counts in another.

## Boss Selection

Boss names are selected from the built-in **global RuneScape 3 boss list** using Discord autocomplete.

## Data Updates

Changes take effect immediately when a command is run successfully.

---

# FAQ

## Can I track only one boss?

Yes. You can use `/deaths boss:<boss>` to view a single boss, and `/death add`, `/death set`, or `/death clear` to manage that boss only.

## Can I reset all my counts at once?

Not in the current version. Counts are cleared **per boss** using `/death clear`.

## Can I view someone else’s counts?

Yes. Use the optional `user` field with the `/deaths` command.

## Do counts carry across servers?

No. Counts are stored separately for each Discord server.

## Do I need to type the boss name exactly?

No. Bosses are selected from the command’s autocomplete list.

---

# Quick Reference

## Update Your Death Counts

- `/death add boss:<boss> amount:<number>` — add to your count
- `/death set boss:<boss> amount:<number>` — set an exact count
- `/death clear boss:<boss>` — clear a count

## View Your Death Counts

- `/deaths` — view all your death counts
- `/deaths boss:<boss>` — view one boss only

## View Another Member’s Death Counts

- `/deaths user:@member`
- `/deaths boss:<boss> user:@member`

---

# Need Help?

If the bot is installed correctly, simply type `/death` or `/deaths` in Discord and Discord will show the available command options.
