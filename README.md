# Assignment 1 – Transliteration Accuracy Testing
**IT3040 – IT Project Management | BSc (Hons) in Information Technology – Year 3**  
**Student ID:** IT23533714  
**Option:** Option 1 – Chat Sinhala Transliteration Testing (for students familiar with Sinhala)

---

## Overview

This project automates the testing of the **Chat Sinhala transliteration** feature available at:  
👉 [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

The script uses **Playwright** to automatically send Singlish (chat-style romanized Sinhala) inputs to the web application and record the actual Sinhala output, then compares it against the expected output and marks each test case as PASS or FAIL.

A total of **50 negative test cases** were identified across all 24 Singlish input types defined in the assignment.

---

## Project Structure

```
test_automation/
│
├── test_automation.py                        # Main Playwright automation script
├── Assignment 1 - Test cases - IT23533714.xlsx  # Test cases with results
└── README.md                                 # This file
```

---

## Prerequisites

- **Python 3.11 or 3.12** – [Download here](https://www.python.org/downloads/)
- **Google Chrome** (recommended) – [Download here](https://www.google.com/chrome/)

---

## Installation

### 1. Clone or download this repository

```bash
git clone <your-repo-url>
cd test_automation
```

Or download the ZIP and extract it to your `D:` drive, then open Command Prompt and run:

```cmd
cd /d D:\test_automation
```

### 2. Install Python dependencies

```bash
pip install -U pip
pip install playwright openpyxl
```

### 3. Install Playwright browsers

```bash
playwright install
```

---

## Running the Tests

From inside the `test_automation` folder, run the following command:

```bash
python test_automation.py --excel "Assignment 1 - Test cases - IT23533714.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command-line Arguments

| Argument | Description | Default |
|---|---|---|
| `--excel` | Path to the Excel test cases file | Auto-detected |
| `--url` | URL of the web application to test | `https://www.pixelssuite.com/chat-translator` |
| `--wait-ms` | Time (ms) to wait for translation output | `5000` |
| `--type-delay-ms` | Delay (ms) between keystrokes when typing | `30` |
| `--slow-mo-ms` | Slow motion delay (ms) for browser actions | `0` |
| `--save-every` | Save Excel after every N test cases | `0` (save at end) |
| `--keep-open` | Keep browser open after tests complete | `false` |
| `--headless` | Run browser in headless mode (no UI) | `false` |

---

## Test Results

After running the script, open the Excel file and check the **Actual output** and **Status** columns, which are filled in automatically.

- **PASS** – Actual output matches the expected Sinhala output exactly
- **FAIL** – Actual output differs from the expected output
- **UI Error** – The script encountered an issue interacting with the page

All 50 test cases in this submission are expected to result in **FAIL**, as they were specifically chosen to expose transliteration errors in the application.

---

## Singlish Input Types Covered

All 24 input types from Appendix 1 of the assignment are covered with at least 2 test cases each:

1. Question forms
2. Command forms
3. Greetings
4. Requests
5. Responses
6. Repeated Words
7. Inputs with Punctuation Marks
8. Romanization / Spelling Variants
9. Isolated English Word Insertions in Singlish
10. Multi-Word English Phrases in Singlish
11. English Digital Terms in Singlish
12. Platform/App Names in Singlish
13. English Abbreviations/Acronyms in Singlish
14. English Clipped Forms in Singlish
15. Place Names Embedded in Singlish
16. Person Names Embedded in Singlish
17. Inputs with Numbers and Numeric Suffixes
18. Inputs with Currency
19. Inputs with Time Formats
20. Inputs with Dates
21. Inputs with Unit of Measurements
22. Inputs with Slang and Casual Phrasing
23. Online Identifiers in Singlish
24. Inputs Containing Emojis

---

## Dependencies

| Package | Purpose |
|---|---|
| `playwright` | Browser automation for UI testing |
| `openpyxl` | Reading and writing Excel (.xlsx) files |
