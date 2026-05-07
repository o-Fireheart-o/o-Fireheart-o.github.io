---
title: "2026-05-04-W1_mon VS Code Setting, Concept of venv(Virtual Environment)"
date: "2026-05-07 23:23 +0900"
categories: [Category]
tags: [tag]
layout: post
---
# Python Study : Environment Setup

## Requirements
- VS Code (Visual Studio Code) : Do not install SandBox Version (Do not install from Microsoft Store!)
- Python 3.xx.xx (Optional)
- Anaconda 3 (Python Package)
## Setup
### Create folder
```powershell
mkdir <folder_name>
```
### Go to New folder
```powershell
cd <folder_name>
# if you want to go high level folder
cd ..
```
### Create virture environment
```PowerShell
# first venv is create command
# second venv is venv name 
python -m venv .venv
```
### Activate
```powershell
.venv\Scripts\activate
```

```bash
source .venv/bin/activate # mac/linux
```
### Check python Version
```powershell
python --version
```
### Deactivate
```powershell
deactivate
```
---
## Note
- Keep venv folder outside of OneDrive
- venv folder should not be pushed to GitHub
- if you want to remove some folders or files use these commands
```powershell
rm <file_name>
```

```powershell
remove-item -recurse -force <folder_name>
```

```bash
rm -rf <folder_name> # mac/linux
```

- if you want to move some folders or files use these commands
```powershell
mv <file(folder)_name> <target_path>\
```
```bash
mv <file(folder)_name> <target_path>/ # mac/linux
```