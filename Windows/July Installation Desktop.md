---
title: July Installation Desktop
parent:
  - "[[Windows]]"
aliases: 
tags:
  - abandoned
---
### July Installation Desktop
Notes on the configuration of my desktop after resetting it in July 2024.
### Steps on Startup
1. Get chocolatey
2. Get Opera with Chocolatey
3. Run debloater: https://christitus.com/windows-tool/
4. Install everything else.
### Chocolatey Managed Apps  
- `choco install -y powertoys obsidian notepadplusplus.install vscode.install spotify discord openjdk procexp procmon autoruns ccleaner 7zip.install wget python312 nano microsoft-windows-terminal steam minecraft-launcher lghub`
- `choco install opera --params '"/NoAutostart /NoDesktopShortcut"'`
- `choco install git.install --params'"/NoAutoCrlf /WindowsTerminalProfile /DefaultBranchName:main /Editor:Notepad++"'`
### Unmanaged Apps
- AMD Adrenaline Software