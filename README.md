# Project 1: Automated Network Inventory Ingestion
**Author:** Eric Rivera  
**Role:** IT Professional / NetDevOps Learner  

## 📌 Project Overview
As part of my transition from IT Support to NetDevOps, this project demonstrates the transition of legacy, unstructured network data (CSV) into a centralized "Source of Truth" using **NetBox**. Instead of manual entry, I developed a Python-based automation script to handle data validation and relational mapping.

## 🛠️ Technology Stack
* **Source of Truth:** NetBox (Dockerized)
* **Environment:** Ubuntu 24.04 VM (VirtualBox)
* **Networking:** Tailscale (Secure Remote Access)
* **Language:** Python 3.12
* **Libraries:** `pynetbox` (API wrapper), `python-dotenv` (Security)
* **IDE:** VS Code (Remote-SSH)

## 🚀 Features
* **Idempotent Logic:** The script checks if Sites or Device Roles exist before creation to prevent duplicate data.
* **Automatic Slug Generation:** Converts human-readable names into API-compliant slugs.
* **Security First:** Utilizes `.env` files and `.gitignore` to prevent API token and infrastructure IP leaks.
* **Error Handling:** Provides real-time feedback via terminal for failed API requests (e.g., 400 Bad Request troubleshooting).

## 📖 Lessons Learned
* **API Constraints:** Navigated NetBox 4.0 requirement changes, such as mandatory Hex color codes for roles.
* **Network Troubleshooting:** Resolved "Connection Refused" issues by aligning Docker port mappings (8000 vs 8080) with script requests.
* **Secure Workflow:** Implemented SSH Key-based authentication for a password-less, secure development environment.

## 🚦 How to Run
1. Clone this repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Configure your `.env` file with your NetBox URL and API Token.
4. Run the script: `python3 import_inventory.py`.