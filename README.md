# Loot Ledger

A personal ledger for mod links. One place for everything from Nexus, Steam Workshop, GitHub, forums and wikis, organized by game.

**https://8bitboar.github.io/loot-ledger/**

## What it does

- **Games** with their own pictures, each with a **Library** that holds every mod for that game once
- **Collections** built from the Library, so one mod can sit in several collections and edits show up everywhere
- **Notes** on each mod, plus an optional note for a mod in one particular collection
- **Collection icons** from [game-icons.net](https://game-icons.net), in a color of your choice
- **Links** with a title, author, tags and notes
- **Per-game tags** with custom colors; each game's tags are separate
- **Requirements** between mods in the same game, with a "Needed by" list on each required mod
- **Mine** badge and **My uploads** page for mods you authored
- **Filtering** by tag, author, Mine, or search, inside a collection or across a whole game
- **Bookmark button** that adds the page you're on, and fills in the author on Nexus mod pages

## How it's built

This repo holds only the page. Data lives in a separate private repo (`loot-ledger-data`): games, Library mods and collections in `collections.json`, and game pictures in `images/`. The page reads and writes that repo through the GitHub API using a fine-grained token that only has access to it. The token stays in the browser it's entered in.

Every change is a commit to the data repo, so the full history is there to restore from.
