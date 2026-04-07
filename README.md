<div align="center">
  <h1>𝔄𝔰𝔭𝔥𝔶𝔵𝔦𝔞 · 𝐜𝐬𝟐 𝐢𝐧𝐭𝐞𝐫𝐧𝐚𝐥</h1>
  <p>A high-performance, modular internal framework for Counter-Strike 2</p>

  <img src="https://img.shields.io/badge/Language-C%2B%2B20-blue?style=flat-square&logo=c%2B%2B" alt="C++20">
  <img src="https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square&logo=windows" alt="Windows">
  <img src="https://img.shields.io/badge/Status-Active-green?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/License-MIT-orange?style=flat-square" alt="License">
</div>

<br />

◈ **Overview**  
Asphyxia is a sophisticated internal library designed for CS2, focusing on low-latency execution and robust feature implementation. It leverages modern C++20 patterns and a customized rendering pipeline to provide a seamless user experience.

◈ **Features**  
- **Combat:** Advanced AimBot (V2), RageBot, Anti-Aim, and Backtrack systems.
- **Visuals:** Grenade predictors, Bullet tracers, Hit-markers, and Spectator lists.
- **Inventory:** Integrated SkinChanger and Inventory Manager utilizing internal game events.
- **Movement:** Movement recorder and optimization utilities.
- **Core:** Dynamic schema dumping, logic-based input handling, and localized configuration storage.

◈ **Tech Stack**  
| Component | Technology |
| :--- | :--- |
| **Logic** | C++20 |
| **UI** | ImGui + FreeType |
| **Hooking** | MinHook & SafetyHook |
| **Rendering** | DirectX 11 |
| **Build** | Premake5 |

◈ **Getting Started**  
1. **Prerequisites:**
   - Visual Studio 2022 (v143 toolset)
   - Windows SDK 10.0+
   - [Premake5](https://premake.github.io/download/)
2. **Setup:**
   - Clone the repository.
   - Run `premake5 vs2022` in the root directory to generate the solution.
3. **Build:**
   - Open `asphyxia.sln` and build in **Release | x64**.

◈ **Usage**  
1. Launch Counter-Strike 2.
2. Inject the resulting `cstrike.dll` using your preferred manual-map injector.
3. Use the `INSERT` key to toggle the GUI (default).
4. Press the configured **Panic Key** to immediately unload the library.

◈ **Configuration**  
Settings and logs are stored automatically in your Documents folder:  
`Documents\UNDERAGER_logs\`

⚠ **Known Requirements**  
The project waits for specific modules before initializing to prevent race conditions:
- `navsystem.dll` and `materialsystem2.dll` must be loaded by the game.
- Ensure `freetype.lib` is present in `dependencies/freetype/binary` before compiling.

◈ **Project Structure**  
```text
┆
├── cstrike/            # Core source code
│   ├── core/           # Framework & HWID/Hooking logic
│   ├── features/       # Feature implementations
│   ├── sdk/            # Game classes & Interfaces
│   └── utilities/      # Memory, Math, and Logging
├── dependencies/       # Third-party libraries (ImGui, etc.)
├── resources/          # Binary assets (Fonts, Icons)
└── premake5.lua        # Build configuration
