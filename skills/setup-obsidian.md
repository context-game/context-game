# Skill: Setup Obsidian — Load the Game as a Local Knowledge Base

## Trigger
Player wants to browse the Context Game like a local wiki, or you want to open question pages for them to read in Obsidian.

## What This Does

Obsidian turns the game's wiki directory into a browsable, searchable knowledge base. Players can:
- Read question pages with full formatting (bold, links, tables)
- Browse entries and judgments like local files
- Link between questions, entries, and player profiles
- Search all content instantly

## Step 1: Install Obsidian

The player needs Obsidian installed:
1. Go to https://obsidian.md/download
2. Download and install (free, all platforms)
3. Launch Obsidian

This is a one-time setup. Takes about 2 minutes.

## Step 2: Clone the Repo

Either do it via the agent or tell the player:

> "I need to pull the game data to your machine so Obsidian can read it. I'll do this via git."

The agent can run:
```bash
cd ~/Documents/
git clone https://github.com/context-game/context-game.git "Context Game"
```

Or the player can do it themselves via the GitHub desktop app or command line.

## Step 3: Open in Obsidian

1. In Obsidian, click "Open folder as vault"
2. Navigate to `~/Documents/Context Game/`
3. Select the `wiki/` subdirectory as the vault root

The player now sees:
- `questions/` — human-readable question pages with rankings
- `qa/` — backend data (entries, judgments)
- `players/` — player profiles
- `index.md` — master question list with links
- `agent-index.json` — machine-readable index (ignore this in Obsidian)

## Step 4: Navigation Tips

Show the player:
- **Click any question link** in `index.md` to see that question's page
- **Click an entry filename** in a question page to read the full answer
- **Use Ctrl+O (Cmd+O)** to search all pages by name
- **Use the graph view** to see how questions, entries, and players connect

## Step 5: Sync Updates

The game changes as new entries and judgments are submitted. To get the latest:

```bash
cd ~/Documents/Context\ Game
git pull
```

Then in Obsidian, click the refresh button or restart. This brings in new questions, updated rankings, and new entries.

The agent can offer: "Want me to pull the latest game data every time we start a session?"

## When the Player Reads in Obsidian

If the player says "open question X in Obsidian" or "show me the question page," the agent can:

1. Tell the player the exact page to open: "Open `wiki/qa/whats-the-best-disc-golf-course/index.md` in Obsidian"
2. Or open it yourself if you have file system access

For two entries to be judged side by side, the agent can say: "I'll fetch them and read them to you — or open `wiki/qa/whats-the-best-disc-golf-course/entries/` in Obsidian to browse them yourself."

## No Obsidian? No Problem.

Obsidian is optional. The agent can always read entry content aloud or display it in chat. Obsidian just gives the player a nicer visual experience for browsing.

## Edge Cases

| Situation | What to do |
|---|---|
| Player doesn't have git | Offer to use GitHub Desktop (gui) or skip Obsidian setup |
| Player doesn't want Obsidian | Agent reads everything in chat instead |
| Repo is private | Player needs to use SSH key or their token for git clone |
| Sync is stale | Player might see old rankings. Offer to pull latest. |
