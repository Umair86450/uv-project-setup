# UV Project Assignment: Simple & Packaged Applications

## 📄 Description
This repository demonstrates how to create and run **UV simple** and **UV packaged** Python applications.  
Both apps print **Name** and **PIAIC Registration Number** from a `main()` function.

- **Name:** Hafiz Muhammad Umair  
- **PIAIC Registration Number:** PIAIC204291

---

## Table of Contents
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Step-by-Step Procedure](#step-by-step-procedure)
  - [1. Folder Creation](#1-folder-creation)
  - [2. Simple Application Setup](#2-simple-application-setup)
  - [3. Packaged Application Setup](#3-packaged-application-setup)
- [Use Cases](#-use-cases)
- [Screenshots](#-screenshots)
- [Git Setup](#-git-setup)
- [Notes](#notes)

---

## Prerequisites
- Python 3.8+
- [`uv`](https://docs.astral.sh/uv/) installed and on your PATH

---

## Project Structure
```text
uv-assignment/
├─ simple-app/
│  ├─ pyproject.toml
│  └─ main.py
└─ packaged-app/
   ├─ pyproject.toml
   └─ src/
      └─ packaged_app/
         └─ main.py
🛠️ Step-by-Step Procedure
1. Folder Creation
Create a parent folder for the assignment: uv-assignment

Inside it, create two subfolders:

simple-app

packaged-app

2. Simple Application Setup
Initialize and enter the project

bash
Copy code
uv init simple-app
cd simple-app
Sync the environment

bash
Copy code
uv sync
Create main.py

python
Copy code
# main.py
def main():
    print("Name: Hafiz Muhammad Umair")
    print("PIAIC Registration Number: PIAIC204291")

if __name__ == "__main__":
    main()
Run the app

bash
Copy code
uv run main.py
Expected output

yaml
Copy code
Name: Hafiz Muhammad Umair
PIAIC Registration Number: PIAIC204291
3. Packaged Application Setup
Initialize and enter the project

bash
Copy code
uv init --package packaged-app
cd packaged-app
Sync the environment

bash
Copy code
uv sync
Create the package layout

bash
Copy code
mkdir -p src/packaged_app
Add src/packaged_app/main.py

python
Copy code
# src/packaged_app/main.py
def main():
    print("Name: Hafiz Muhammad Umair")
    print("PIAIC Registration Number: PIAIC204291")
Add a console script entry point in pyproject.toml

toml
Copy code
[project]
name = "packaged-app"
version = "0.1.0"
requires-python = ">=3.8"

[project.scripts]
entry = "packaged_app.main:main"
Run via the entry point

bash
Copy code
uv run entry
Alternative module run

bash
Copy code
uv run -m packaged_app.main
Expected output

yaml
Copy code
Name: Hafiz Muhammad Umair
PIAIC Registration Number: PIAIC204291
⚡ Use Cases
Simple UV App: quick script execution with minimal setup, useful for small tasks or testing functions.
Packaged UV App: organized src layout, modular development, CLI script execution, and easier scaling.

🖼️ Screenshots
Add terminal screenshots that show both apps running successfully.

Recommended paths:

Copy code
uv-assignment/
└─ screenshots/
   ├─ simple_app.png
   └─ packaged_app.png
Reference them in the README:

markdown
Copy code
![Simple App Output](screenshots/simple_app.png)
![Packaged App Output](screenshots/packaged_app.png)
✅ Git Setup
Configure Git username and email (once per machine):

bash
Copy code
git config --global user.name "Umair86450"
git config --global user.email "2001muhammadumair@gmail.com"
Initialize the repository and commit:

bash
Copy code
git init
git add .
git commit -m "Initial commit: UV simple and packaged apps"
Create the main branch, add a remote, and push:

bash
Copy code
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
Notes
Keep the package directory name packaged_app in sync with the entry point packaged_app.main:main.

Run uv sync after changing dependencies or cloning the repo on a new machine.

If uv run entry fails, confirm that the [project.scripts] section exists and paths are correct.
