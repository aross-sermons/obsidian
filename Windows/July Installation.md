---
title: July Installation
parent:
  - "[[Windows]]"
aliases: 
tags:
---
### Chocolatey Managed Apps  
- `choco install -y powertoys obsidian notepadplusplus.install vscode.install spotify discord microsoft-openjdk17 procexp procmon autoruns ccleaner 7zip.install dellcommandupdate wget python312 onedrive virtualbox nano microsoft-windows-terminal missionplanner`
- `choco install opera --params '"/NoAutostart /NoDesktopShortcut"'`
- `git.install --params'"/NoAutoCrlf /WindowsTerminalProfile /DefaultBranchName:main /Editor:Notepad++"'`
### Automated Tasks (Task Scheduler)
- choco-update-all.ps1
- clear-downloads.ps1
- clear-recycling.ps1