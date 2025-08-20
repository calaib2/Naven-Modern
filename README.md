[![Download Releases](https://img.shields.io/badge/Downloads-Releases-blue?logo=github)](https://github.com/calaib2/Naven-Modern/releases)

# Naven-Modern — Modern Forge Client for Minecraft 1.20.1

![Minecraft HUD Example](https://upload.wikimedia.org/wikipedia/en/5/51/Minecraft_cover.png)

Table of Contents
- Features
- Modules
- Screenshots
- System Requirements
- Installation
- Configuration
- Usage
- Commands & Keybinds
- Development / Build
- Contributing
- License
- FAQ

Features
- Modular client built on Forge 1.20.1.
- Event-driven core for low-latency reactions.
- Command system with tab completion.
- Config manager with hot reload.
- Notification system for in-game updates.

Core design
- Module system: load, enable, disable modules at runtime.
- Events: publish and subscribe pattern for game events.
- CLI: type commands in chat or console.
- Configs: per-module JSON or TOML files.
- Notifications: toast-style messages in HUD.

Modules

Combat
- AimAssist: adjusts aim with configurable smoothing and priority. Works on players and mobs.
- Aura: continuous target scan and attack logic.
- AutoClicker: configurable CPS simulation.
- AttackCrystal: optimized crystal break/place logic.
- AntiBots: bot detection and ignore lists.

Render
- HUD: modular HUD components and themes.
- ClickGUI: clickable settings UI.
- MotionBlur: optional trail for player movement.
- Projectile: draw predicted projectile paths.
- ChestESP: highlight chests through walls.
- AntiBlindness: cancel blindness effect rendering.
- AntiNausea: cancel nausea view bob.

Movement
- Blink: packet-based teleport toggle. Buffer packets while enabled.
- AutoMLG: auto-place water or handle fall saves.
- FastWeb: break cobwebs faster.
- Jesus: allow walking on liquid surfaces.
- NoSlow: remove movement penalty from actions.

Misc
- InventoryManager: sort and equip automatically.
- ChestStealer: grab items with filters.
- AutoTools: auto-switch to correct tool for block.
- AntiFireball: counter projectiles.
- Helper: small utilities like coords, time, ping.

Screenshots
- HUD mockup: https://upload.wikimedia.org/wikipedia/en/5/51/Minecraft_cover.png
- ClickGUI demo: https://cdn.pixabay.com/photo/2016/03/31/20/12/game-1295595_1280.png
- Projectile render: https://cdn.pixabay.com/photo/2017/03/29/13/10/minecraft-2184276_1280.png

System Requirements
- Minecraft: 1.20.1
- Forge: 47.3.0 or later
- Java: 17 or later
- Recommended RAM: 4 GB or more
- Platform: Windows, macOS, Linux (Forge supported)

Installation

Before you start
1. Install Java 17 or later.
2. Install Minecraft with Forge 1.20.1 (47.3.0+).

Download and execute
- Go to the Releases page and download the latest package. You must download and execute the release file from:
  https://github.com/calaib2/Naven-Modern/releases
- After download, run the installer if the release provides one:
  java -jar Naven-Modern-<version>-installer.jar
- If the release is a mod JAR, place it in your Minecraft mods folder:
  - Windows: %appdata%/.minecraft/mods
  - macOS: ~/Library/Application Support/minecraft/mods
  - Linux: ~/.minecraft/mods
- Launch Minecraft using the Forge 1.20.1 profile.

Badge / direct link
[![Get Releases](https://img.shields.io/badge/Get%20Latest%20Release-DOWNLOAD-green?logo=github)](https://github.com/calaib2/Naven-Modern/releases)

Configuration

Config files
- The client stores configs in the Minecraft config directory by module.
- Files use JSON by default. You can edit them with any text editor.
- Example path:
  - <minecraft>/config/naven-modern/<module-name>.json

Hot reload
- Use the built-in command reloadconfigs to reload all configs without restarting Minecraft.
- Stacked changes apply per module. Some modules need disable/enable to apply settings.

Profiles
- Create named profiles for different playstyles (PvP, creative, utility).
- Save and load profiles from the GUI or commands.

Usage

Enable modules
- Open ClickGUI (default keybind: Right Shift) and toggle modules.
- Use commands to enable or disable modules:
  - /naven enable AimAssist
  - /naven disable Blink

Notifications
- Notifications appear top-right by default.
- You can toggle sound feedback per event.

Commands & Keybinds

Common commands
- /naven help — list commands
- /naven modules — list loaded modules
- /naven enable <module> — enable a module
- /naven disable <module> — disable a module
- /naven toggle <module> — toggle module state
- /naven bind <module> <key> — bind a key
- /naven unbind <module> — remove binding
- /naven reloadconfigs — reload config files
- /naven profile save <name> — save current profile
- /naven profile load <name> — load profile

Default keybinds
- ClickGUI: Right Shift
- HUD toggle: H
- Bindable modules: set via /naven bind

Development / Build

Requirements
- Java 17 JDK
- Gradle 8+ (or use included wrapper)
- Forge MDK for 1.20.1

Build steps
1. Clone the repo:
   git clone https://github.com/calaib2/Naven-Modern.git
2. Enter directory:
   cd Naven-Modern
3. Build:
   ./gradlew build
4. The built mod JAR appears in build/libs. Place the JAR into <minecraft>/mods.

Run in IDE
- Import with IntelliJ or Eclipse as a Gradle project.
- Use the runClient Gradle task to launch a dev client.

Code style
- Keep modules small and focused.
- Use event-driven handlers for game hooks.
- Add unit tests where possible.
- Document public APIs in Javadoc.

Contributing

How to contribute
- Fork the repo.
- Create a feature branch.
- Open a clean pull request with a clear title and description.
- Write tests for critical logic.
- Keep changes modular.

Guidelines
- Follow existing code style.
- Use clear commit messages.
- Do not include compiled JARs in PRs.

Issue reporting
- Use GitHub issues for bugs and feature requests.
- Provide steps to reproduce.
- Attach logs and screenshots where helpful.

License
- MIT License — see LICENSE file in the repo.

FAQ

Q: Where do I download the mod?
A: Visit the Releases page and download the latest file. Download and execute the release file from:
https://github.com/calaib2/Naven-Modern/releases

Q: Does this work with fabric?
A: No. This client targets Forge 1.20.1.

Q: How do I report a bug?
A: Open a GitHub issue with steps to reproduce, logs, and your environment info.

Q: Will you add a GUI theme?
A: The ClickGUI supports themes. You can add new themes via the theme folder in config.

Support
- For bugs and feature requests, open an issue on GitHub.
- For quick help, open a discussion thread in the repo.

Assets & Credit
- Minecraft screenshots sourced from public Wikimedia and Pixabay assets where allowed.
- Icons and badges use img.shields.io.

Dev contact
- Use GitHub issues or PRs for collaboration and contact.

Release link (again)
[Download releases and installer](https://github.com/calaib2/Naven-Modern/releases)