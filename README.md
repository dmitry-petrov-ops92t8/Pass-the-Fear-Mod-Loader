# Pass the Fear Mod Loader

A lightweight, community-focused **mod loader and modding framework for Pass the Fear**.

Install mods, manage your mod collection, and extend the game with community-created content — without manually modifying the original game files.

> 🚧 **Early Development**
>
> Pass the Fear Mod Loader is currently in active development. Features, APIs, and installation methods may change between releases.

---

## ✨ Features

### For Players

* 📦 Automatic mod discovery
* 🔌 Simple mod installation
* ✅ Enable and disable individual mods
* 📋 Mod load order management
* ⚙️ Mod configuration support
* 📝 Detailed logging
* 🛡️ Keep mods separated from original game files
* 🔍 Detect incompatible or broken mods
* 🚀 Automatic mod loading when the game starts

### For Mod Developers

* 🧩 Mod API
* 📚 Developer documentation
* 🛠️ Mod development examples
* ⚙️ Configuration API
* 📝 Logging API
* 🔄 Mod version information
* 🔗 Mod dependency support
* 📦 Simple mod packaging
* 🧪 Development-friendly debugging tools

---

# 🎮 How It Works

Pass the Fear Mod Loader provides a layer between the game and community modifications.

```text
┌─────────────────────────────┐
│       Pass the Fear         │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│     Pass the Fear Mod       │
│          Loader              │
└──────────────┬──────────────┘
               │
       ┌───────┼───────┐
       ▼       ▼       ▼
    Mod A    Mod B    Mod C
       │       │       │
       └───────┼───────┘
               ▼
        Mod API / Framework
```

The goal is to allow mods to extend the game while keeping the original installation as untouched as possible.

---

# 📥 Installation

## 1. Download the Mod Loader

Download the latest release from the project's GitHub Releases page.

**Releases:**
[Download Pass the Fear Mod Loader](../../releases)

## 2. Install the Loader

Follow the installation instructions included with the release.

> Installation details may change while the project is in development. Always check the documentation for the version you are using.

## 3. Create Your Mods Folder

After installation, the loader will use a dedicated mods directory.

Example:

```text
Pass the Fear/
└── Mods/
    ├── ExampleMod/
    ├── AnotherMod/
    └── MyMod/
```

## 4. Add Your Mods

Place compatible mods inside the `Mods` directory.

Launch Pass the Fear and the Mod Loader will detect available modifications.

---

# 🧩 Installing a Mod

Installing a community mod should be as simple as:

```text
Download Mod
      ↓
Extract Mod
      ↓
Place Mod in Mods/
      ↓
Launch Pass the Fear
      ↓
Mod Loader detects it
      ↓
Mod loads
```

No need to manually overwrite the original game files whenever possible.

---

# 🛠️ Creating a Mod

Pass the Fear Mod Loader is also designed for developers who want to create their own mods.

A basic mod might look like:

```text
MyFirstMod/
├── mod.json
├── MyFirstMod.dll
└── config/
    └── settings.json
```

Example metadata:

```json
{
  "name": "My First Mod",
  "id": "my-first-mod",
  "version": "1.0.0",
  "author": "Template",
  "description": "My first Pass the Fear mod.",
  "dependencies": []
}
```

The exact API and metadata format may change during early development.

See the documentation for the current modding API.

---

# 📚 Mod API

The Mod API is intended to provide developers with a stable way to interact with the loader and supported game systems.

Planned API areas include:

* Mod lifecycle
* Configuration
* Logging
* Events
* Dependencies
* Version checking
* Mod discovery
* Runtime information

Example concept:

```csharp
public class MyMod : IMod
{
    public void OnLoad()
    {
        Logger.Info("My First Mod loaded!");
    }

    public void OnUnload()
    {
        Logger.Info("My First Mod unloaded.");
    }
}
```

The API is still evolving, so developers should expect breaking changes during early releases.

---

# 📦 Mod Structure

A standard mod package may eventually follow a structure similar to:

```text
MyMod/
│
├── mod.json
├── MyMod.dll
├── README.md
├── config/
│   └── config.json
└── assets/
    └── ...
```

This structure is intended to make mods easy to install, distribute, update, and manage.

---

# ⚙️ Mod Configuration

Mods can provide their own configuration files.

Example:

```json
{
  "enabled": true,
  "featureEnabled": true,
  "value": 100
}
```

The goal is to allow players to customize mods without editing compiled files.

---

# 🔗 Mod Dependencies

Some mods may require other mods or specific versions of the Mod Loader.

For example:

```text
MyGameplayMod
      │
      ├── Pass the Fear Mod Loader
      │
      └── Common API
```

Dependency information can be declared in the mod metadata.

This allows the loader to detect missing requirements before starting the game.

---

# 📝 Logging & Troubleshooting

The Mod Loader provides logging to help identify problems.

Typical log information may include:

```text
[INFO] Mod Loader starting...
[INFO] Searching for mods...
[INFO] Found 3 mods.
[INFO] Loading ExampleMod...
[INFO] ExampleMod loaded successfully.
[WARN] AnotherMod requires a newer API version.
[ERROR] Failed to load BrokenMod.
```

If a mod fails to load, logs can help determine whether the problem is related to:

* the mod itself;
* an incompatible version;
* a missing dependency;
* an incorrect installation;
* the Mod Loader;
* the game.

---

# 🛡️ Safety

The Mod Loader is intended to keep community modifications separated from the original game installation as much as practical.

However, **mods are third-party software**.

Only install mods from sources you trust.

Before installing a large collection of mods, consider making a backup of your game saves.

Never assume that a third-party mod is safe simply because it is distributed through a community website.

---

# 🧑‍💻 Development
```

Build the project using the appropriate .NET tooling for the current release.

```bash
dotnet build
```

Run tests:

```bash
dotnet test
```

> Development commands may change as the project architecture evolves.

---

# 🗺️ Roadmap

## v0.1 — Foundation

* [ ] Basic mod detection
* [ ] Mod folder
* [ ] Mod metadata
* [ ] Basic mod loading
* [ ] Logging
* [ ] Error handling

## v0.2 — Mod Management

* [ ] Enable / disable mods
* [ ] Mod load order
* [ ] Configuration files
* [ ] Better error messages
* [ ] Mod compatibility checks

## v0.3 — Mod API

* [ ] Public Mod API
* [ ] Lifecycle events
* [ ] Configuration API
* [ ] Logging API
* [ ] Developer documentation
* [ ] Example mods

## v0.4 — Dependencies

* [ ] Mod dependencies
* [ ] Version requirements
* [ ] Dependency validation
* [ ] Conflict detection

## v0.5 — Mod Manager

* [ ] Graphical mod manager
* [ ] Mod browser
* [ ] Mod profiles
* [ ] One-click enable / disable
* [ ] Mod information panel

## v1.0 — Community Modding Platform

* [ ] Stable API
* [ ] Stable mod format
* [ ] Complete documentation
* [ ] Mod development toolkit
* [ ] Community mod ecosystem
* [ ] Automated compatibility checks

---

# 🤝 Contributing

Contributions are welcome!

You can help by:

* reporting bugs;
* suggesting features;
* improving documentation;
* creating example mods;
* improving the Mod API;
* testing new releases;
* submitting pull requests.

Before submitting a large change, consider opening an issue to discuss the idea first.

---

# 🐛 Bug Reports

When reporting a problem, please include:

* Mod Loader version
* Pass the Fear version
* operating system
* installed mods
* steps to reproduce the issue
* relevant log files
* screenshots when useful

A good bug report makes troubleshooting much faster.

---

# 💡 Feature Requests

Have an idea for the modding framework?

Open an issue and describe:

1. What you want to add.
2. Why it would be useful.
3. How you expect it to work.
4. Whether the feature is intended for players or mod developers.

---

# 📜 License

This project is licensed under the terms specified in the repository's `LICENSE` file.

Pass the Fear and its associated intellectual property belong to their respective owners.

This project is an independent community-created tool and is not affiliated with or endorsed by the original developers unless explicitly stated.

---

# ⭐ Support the Project

If you find **Pass the Fear Mod Loader** useful:

* ⭐ Star the repository
* 🐛 Report bugs
* 💡 Suggest features
* 🧩 Create mods
* 📖 Improve the documentation
* 📢 Share the project with other Pass the Fear players

The more people use the loader, the more useful the modding ecosystem can become.

---

# 🚀 Build the Pass the Fear Modding Community

Pass the Fear Mod Loader is more than a loader.

The long-term goal is to create a foundation for a **community-driven modding ecosystem** around Pass the Fear.

```text
                 PASS THE FEAR
                       │
                       ▼
              MOD LOADER / API
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       Gameplay       QoL          UI
        Mods          Mods        Mods
          │            │            │
          └────────────┼────────────┘
                       ▼
                COMMUNITY
                       │
                       ▼
              MORE MODS & TOOLS
```

**Install. Create. Share. Mod Pass the Fear.**
