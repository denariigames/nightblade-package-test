# NightBlade MMO Addons

**Addon Manager** is a custom Unity Editor window designed for [**NightBlade MMO**](https://github.com/Fallen-Entertainment/NightBlade_MMO) that provides a clean, professional interface for discovering, installing, and managing addons.

It functions as a private, curated "addon marketplace" directly inside the Unity Editor, making it easy to browse and install community or official addons without leaving your project.

## Features

<img width="260" height="475" alt="image" src="https://github.com/user-attachments/assets/94e477b5-09a7-4e3d-9af1-e3d2e8b07777" />

- **Dynamic Addon Discovery**
  - Addons are loaded from a central [manifest.json](https://github.com/denariigames/nightblade-addons/blob/master/manifest.json)
  - Shows outdated addons where an update is available
  - Clean, Unity Package Manager-inspired layout

- **Smart Filtering**
  - Category
  - Publisher (Core or Community)
  - Status (All, Installed, Update Available, Not Installed)
  - Recency (Anytime, This week, This month)

- **Clean Project Structure**
  - addons saved to NightBlade_addons folder, organized by category

## Contributing Addons

To contribute your addon:

- Bundle your assets as a .unitypackage with a guid file (*do not include the Assets folder!*)
  - The guid file should have a filename unique to the project. You can use a resource like [GuidGenerator](https://guidgenerator.com/) to create one.
  - Creating the file in Unity as a text file should work. Otherwise, `touch your-guid-id` at the command line so there is no extension (Windows equivalent: `echo.> your-guid-id`).
- Add a NightBlade compatible package.json with required fields (see below)
- Host on a public github repository
- Submit a [pull request](https://github.com/denariigames/nightblade-addons/pulls) to the manifest.json

### NightBlade Compatible package.json

Each addon repository must have a NightBlade compatible package.json with these required fields:

- name (displayed in Addon Manager and used for addon folder name)
- guid (must be unique to the project and match guid filename in the unitypackage)
- author (format: string or object {"name": "yourname", "url": "yoururl"})
- version
- updateDate (format: "YYYY-MM-DD")
- packageUrl (link to the unitypackage, you can use either a release package or raw/refs/head)

Optional, but recommended:

- category (must match one of the approved categories below)
- description (supports \n for line breaks)
- screenshot (filename of screenshot file in repo at same root as package.json, e.g. screenshot.png)

A valid example package.json is [available here](https://github.com/denariigames/nightblade-addons/blob/master/example-package.json).

### Approved Categories

Only these categories appear in the filter dropdown:

- Characters
- Monsters
- NPCs
- Combat
- Economy
- Items
- Gameplay
- UI
- MMO
- Tools

Any other category value will be treated as "Uncategorized" and hidden from filters.
