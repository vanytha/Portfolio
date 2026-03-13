# Case Study: Resolving Time Zone Issues in CXS Platform

## Background
A time zone–related issue was identified in the CXS platform where certain date fields appeared **one day earlier for client administrators** compared to what was stored in the system. This discrepancy affected several features across the platform, particularly areas that display **hire dates, birthdays, and service anniversaries**.

Since these dates drive **recognition events, reports, and service milestones**, ensuring their accuracy was critical. The issue required careful investigation and regression testing across multiple modules.

---

## Problem Statement
Dates saved based on user input were not always displayed correctly due to time zone differences between the system and user environment.

This caused some dates to appear one day earlier, especially in reporting and administrative views.

---

## Affected Areas
The following sections of the application were identified as potentially impacted by the time zone issue and required regression testing.

---

## 1. Edit Profile – Moments that Matter
Within the **Moments that Matter** tab in the Edit Profile section, the following fields needed validation:

- Service anniversary (Hire date)
- Birthday selection
- Adding a personal moment with date in the Moments that Matter section

<img width="840" height="331" alt="image" src="https://github.com/user-attachments/assets/8a0cfb39-d3d2-492d-8289-c70f3074869f" />

These fields store important personal milestones and must retain the exact date entered by the user.

---

## 2. Homepage
On the homepage, the **anniversary dates displayed for users celebrating service milestones** must appear correctly.
<img width="840" height="373" alt="image" src="https://github.com/user-attachments/assets/fc49cbb3-8c98-4faf-9d4f-3ac28fb85ff7" />

Incorrect date calculations due to time zone shifts could cause recognition messages to trigger on the wrong day.

---

## 3. My Wall
When clicking on a user profile and viewing **My Wall**, the following dates should be displayed correctly:

- Hire date
- Birthday
  
<img width="840" height="243" alt="image" src="https://github.com/user-attachments/assets/bea61827-a3d4-414a-8968-48357132029e" />

These values must reflect the exact date saved in the user profile.

---

## 4. Upcoming Anniversaries (Manager Tools)
Within **Manager Tools → Upcoming Anniversaries**, the dates shown in the report must be accurate for all dropdown selections.

### Dropdown Options
- All Service Anniversaries
- Birthdays
- Milestone Anniversaries
<img width="940" height="208" alt="image" src="https://github.com/user-attachments/assets/8687d060-4931-41c7-9d6e-e14ddf8d6b8a" />

The following date fields must display correctly:

- Service Award Date (All Service Anniversaries)
  <img width="942" height="379" alt="image" src="https://github.com/user-attachments/assets/8004804b-1e4f-4b81-a353-db05b8f27b14" />

- Birth Date (Birthdays)
  <img width="943" height="337" alt="image" src="https://github.com/user-attachments/assets/23dcd59c-b6c0-48ce-94ef-e9653b78d029" />

- Service Award Date (Milestone Anniversaries)
<img width="944" height="399" alt="image" src="https://github.com/user-attachments/assets/01b1c6be-0cd7-4692-a0ee-c5cfc9107805" />

Additionally, the dates must remain accurate when exported to **XLS files**.

---

## 5. Manage Accounts
In the **Manage Accounts** section, date fields must remain consistent across all options in the **Actions dropdown**.
<img width="944" height="276" alt="image" src="https://github.com/user-attachments/assets/9dc01855-7b3b-45ac-89d3-67f18885ae3f" />

### Areas affected
- Edit Profile → Service date
  <img width="859" height="379" alt="image" src="https://github.com/user-attachments/assets/ae78456a-dcbd-4b79-9dd8-562c2876229f" />

- Online Statement → Service anniversary date
 <img width="940" height="315" alt="image" src="https://github.com/user-attachments/assets/a6f89f33-2230-4bdb-b6ef-fcb9983306a3" />

- Permissions → Service anniversary date
  <img width="944" height="303" alt="image" src="https://github.com/user-attachments/assets/dee016b3-23b8-4fb2-b0e0-5b8a64d7d35d" />

- Points Management → Service anniversary date
<img width="940" height="395" alt="image" src="https://github.com/user-attachments/assets/e15ec8e7-9cd1-4b23-8768-141d9909dd80" />

These dates must accurately reflect the stored values regardless of user location or time zone.

---

## 6. Reports – Awards and Rewards

### a. Upcoming Anniversary and Birthday
Dates must display correctly in the report:
<img width="875" height="428" alt="image" src="https://github.com/user-attachments/assets/cdb39db8-0a64-4eb6-a63f-906b32a8c112" />

These values must also remain consistent when exported to:

- XLS
- CSV

### b. Selection History
The **anniversary date** should be displayed correctly in selection history records.
<img width="866" height="367" alt="image" src="https://github.com/user-attachments/assets/aa036177-4c2d-4769-a6ff-32ae29ec0bad" />
<img width="862" height="169" alt="image" src="https://github.com/user-attachments/assets/16b2ba51-0caa-4cb5-a5fc-cd0454ddfa27" />


### c. Expired Awards
The **anniversary date** associated with expired awards should also display accurately.
<img width="853" height="470" alt="image" src="https://github.com/user-attachments/assets/7df370a1-2a5f-40f8-81d5-82a3b61120c6" />

---

## 7. Order History
The dates shown in the **Order History report** should match the dates stored in **Backstage → Nominations Management**.
 <img width="944" height="300" alt="image" src="https://github.com/user-attachments/assets/b7ce395d-de7b-47a9-9ae4-00ffeb231faf" />

However, the client administrator observed that some dates appeared **one day earlier**, indicating a potential **time zone conversion issue**.
 <img width="944" height="260" alt="image" src="https://github.com/user-attachments/assets/85183d4a-57ef-4fe9-a304-4849b33f2060" />

---

## Root Cause
The discrepancy appears to be caused by **time zone conversion differences between stored system dates and client display time zones**, leading to incorrect date rendering in certain UI components and reports.

---

## Recommended Action
Regression testing should be conducted across all affected modules to ensure:

- Dates are saved exactly as entered by users
- Displayed dates remain consistent across all views
- Exported reports (XLS/CSV) reflect the correct values
- Time zone handling is standardized across the platform

---

## Outcome
By validating these scenarios through regression testing, the platform can ensure:

- Accurate date handling across all modules
- Reliable recognition events
- Correct reporting outputs
- Improved trust in system-generated data
