# Fitlife Studio Management System

An end-to-end Python management system for **FitLife Studio**, designed to handle member enrollment, eligibility evaluation, automated membership renewals, revenue aggregation, and file logging.

---

## Key Features

* **Interactive Welcome Kiosk:** Formatted CLI displays built using f-string specifiers and dynamic user inputs.
* **Core Data Architecture:** Utilizes nested dictionaries for member profiles, immutable tuples for pricing tiers, sets for unique branch deduplication, and dictionaries for weekly timetables.
* **Business & Control Logic:** Applies boolean logic to calculate booking eligibilities, iterative loops to track revenue, and string date comparisons for membership expirations.
* **Modular Architecture & File I/O:** Encapsulates core logic into reusable functions (`enrol_member`, `renew_membership`, `calculate_fees`) and writes formatted system reports to disk using Python context managers.

---

## Technical Specifications

| Component | Implementation Details |
| :--- | :--- |
| **Language & Version** | Python 3.x |
| **Libraries** | Standard Library (`datetime`, `math`, `random`) |
| **File Operations** | `open()` context manager (`with` statement) for persistent reports |
| **Data Models** | Primitive collections (`list`, `dict`, `set`, `tuple`) |

---

## Project Milestones

### Milestone 1: Front-Desk Welcome Kiosk
Constructed a CLI kiosk interface handling studio information displays, membership plan pricing, promo banners, and walk-in user input capture.

### Milestone 2: Data Structures Layer
Structured core member records using list-of-dictionaries:
```python
members = [
    {
        "id": "FL-001",
        "name": "Tan Jia Hui",
        "plan": "Basic",
        "branch": "Tampines One",
        "joined": "2025-10-15",
        "expires": "2026-04-15",
        "status": "EXPIRED"
    }, ...
]
```
Utilized immutable tuples for plan rates and sets for branch tracking.

### Milestone 3: Control Flow & Business Logic
* Evaluated class booking eligibility using boolean combinations (`plan != 'Basic'` AND `status == 'active'`).
* Executed date-string comparison logic to filter expired members and calculate 6-month extensions.
* Aggregated total monthly revenues using conditional loop counters.

### Milestone 4: Modular Library & File Logging
* Modularized operations into functional signatures (`calculate_fees`, `check_eligibility`, `print_member_card`).
* Handled ISO date parsing and timedelta operations via Python's `datetime` module.
* Implemented text file logging (`members_report.txt`) to maintain permanent audit records.

---

## Sample Generated Report (`members_report.txt`)

```text
============= FITLIFE CLASS REPORT =============
Generated: 2026-08-18 12:48
Total members: 6

FL-001 | Tan Jia Hui | Basic | EXPIRED
FL-002 | Rajesh Kumaran | Premium | active
FL-003 | Nur Hidayah Binte Rahman | Plus | EXPIRED
FL-004 | Marcus Wong | Basic | active
FL-005 | Priya Subramaniam | Premium | active
FL-006 | David Chen | Plus | active

FEES
 Grand total : S$808.00
 Basic       : S$176.00
 Plus        : S$256.00
 Premium     : S$376.00

ELIGIBLE FOR CLASS BOOKING
 Rajesh Kumaran
 Priya Subramaniam
 David Chen

----- end of report -----
```

---

## Link to Python code in Google Colab

Front-Desk Welcome Kiosk: 
https://github.com/LiewWaiSan/Fitlife-Studio-Management-System/blob/main/Fitlife_M1_Liew_Wai_SanGH.ipynb 

Data Structures Layer:
https://github.com/LiewWaiSan/Fitlife-Studio-Management-System/blob/main/Fitlife_M2_LiewWaiSanGH.ipynb

Control Flow & Business Logic:
https://github.com/LiewWaiSan/Fitlife-Studio-Management-System/blob/main/Fitlife_M3_LiewWaiSan.ipynb

Modular Library for code reusability and easier debugging & File Logging:
https://github.com/LiewWaiSan/Fitlife-Studio-Management-System/blob/main/FitLife_M4_LiewWaiSan.ipynb
