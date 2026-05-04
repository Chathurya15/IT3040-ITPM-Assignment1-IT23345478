# 📘 ITPM Assignment 01 - Test Automation using Playwright

**Student ID:** IT23345478 | **Module Code:** IT3040 | **Module Name:** ITPM

## 📌 Project Overview

This repository contains an automated test suite developed for **ITPM Assignment 01** using **Playwright for Python**.  
The purpose of this project is to evaluate the transliteration accuracy of the **PixelsSuite Chat Translator** web application, which converts **Singlish input into Sinhala text**.

The automation covers:
- Execution of 50 negative test cases across 24 specific Singlish categories.
- Real-time UI data extraction and validation.
- Automated data logging into an Excel spreadsheet (`openpyxl`).

All tests are executed using **Python 3.12** utilizing the university-provided automation script.

---

## ⚠️ Important Note for Evaluators
**Please Read Before Running:**

1.  **Negative Test Cases:** This assignment specifically requires identifying **Negative Scenarios** (instances where the system *fails* to correctly convert chat-style Singlish into accurate Sinhala). 

2.  **The Result:** Because the expected output is the *correct* grammatical Sinhala, and the website's actual output is *incorrect*, the automation script will intentionally detect a mismatch.
    * **In the Terminal (Console):** You will see `-> FAIL` printed for the test rows. 
    * **In the Excel File:** The script will automatically record the `Status` as `FAIL`.
    
    **This is INTENTIONAL** A "FAIL" status proves that our automation successfully caught the translation bug and fulfilled the negative test case requirement.

---

## 🛠️ Step 1: Prerequisites
Before running the project, make sure the following software is installed on your system:
1.  **Python 3.11 or 3.12**: [Download Here](https://www.python.org/downloads/) 
*(Crucial: Ensure the "Add Python.exe to PATH" box is checked during installation).*
2.  **Google Chrome**: Installed and up to date.
3.  **VS Code**: [Download Here](https://code.visualstudio.com/) (Recommended editor).

💡 Verify your Python installation by running:
```bash
python --version
```

---

## 🚀 Step 2: Project Setup & Dependency Installation

Follow these steps carefully to configure the Python environment:
1.  **Download** this repository as a ZIP file 
2.  **Extract (Unzip)** and Save the ZIP file to your D: drive and extract
3.  Open **Visual Studio Code**.
4.  Go to **File → Open Folder** and select the extracted project folder.
5.  In VS Code, go to the top menu: **Terminal → New Terminal**.
6.  Paste the following commands into the terminal one by one and press **Enter**:

**Update pip:**
```bash
pip install -U pip
```

**Install Project Dependencies (Playwright & OpenPyXL):**
```bash
pip install playwright openpyxl
```

**Install Playwright Browsers:**
```bash
playwright install
```

---

## 🏃‍♂️ Step 3: Run the Tests
To execute the automated test cases and record the outputs directly to the Excel file, run the following single command in your VS Code terminal.

(Note: The --wait-ms 15000 flag is utilized to account for server response latency on the target application).


```bash
python test_automation.py --excel "test_automation/ Assignment 1 - Test cases.xlsx" -
url "https://www.pixelssuite.com/chat-translator" --wait-ms 15000 --type-delay-ms 80 -
slow-mo-ms 200 --save-every 1 --keep-open
```

### 📝 Understanding the Output:

Once the script finishes running, open the Assignment 1 - Test cases_2.xlsx file. You will see that the script has automatically populated the Actual output and Status columns for all 50 test cases based on the live website evaluation.

---

## 🧰 Technologies Used

| Technology               | Purpose                                   |
| ------------------------ | ----------------------------------------- |
| Python 3.12              | Core programming language                 |
| Playwright (Python)      | End-to-end test automation                |
| OpenPyXL                 | Excel file reading/writing automation     |
| VS Code                  | Development environment                   |
| Git / GitHub             | Version control & source code managements |


---

## 📂 Project Structure

```text
IT3040-ITPM-Assignment1-IT23345478/
├── test_automation.py                  # Main Playwright Python automation script
├── Assignment 1 - Test cases_2.xlsx    # Excel dataset containing 50 negative test cases
└── README.md                           # Project documentation and execution guide