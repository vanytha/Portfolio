# Case Study: Resolving Time Zone Issues Affecting Date Accuracy in CXS Platform

## Background
A time zone–related issue was identified in the CXS platform where certain date fields appeared **one day earlier for client administrators** compared to what was stored in the system. This discrepancy affected several features across the platform, particularly areas that display **hire dates, birthdays, and service anniversaries**.

Since these dates drive **recognition events, reports, and service milestones**, ensuring their accuracy was critical. The issue required careful investigation and regression testing across multiple modules.

---

## Problem Statement
Dates saved based on **user input** were not always displayed correctly due to **time zone differences between the system and user environment**.

This caused some dates to appear **one day earlier**, especially in reporting and administrative views.

---

## Affected Areas
The following sections of the application were identified as potentially impacted by the time zone issue and required regression testing.

---

## 1. Edit Profile – Moments that Matter
Within the **Moments that Matter** tab in the Edit Profile section, the following fields needed validation:

- Service anniversary (Hire date)
- Birthday selection
- Adding a personal moment with date in the Moments that Matter section

These fields store important personal milestones and must retain the exact date entered by the user.

---

## 2. Homepage
On the homepage, the **anniversary dates displayed for users celebrating service milestones** must appear correctly.

Incorrect date calculations due to time zone shifts could cause recognition messages to trigger on the wrong day.

---

## 3. My Wall
When clicking on a user profile and viewing **My Wall**, the following dates should be displayed correctly:

- Hire date
- Birthday

These values must reflect the exact date saved in the user profile.

---

## 4. Upcoming Anniversaries (Manager Tools)
Within **Manager Tools → Upcoming Anniversaries**, the dates shown in the report must be accurate for all dropdown selections.

### Dropdown Options
- All Service Anniversaries
- Birthdays
- Milestone Anniversaries

The following date fields must display correctly:

- Service Award Date (All Service Anniversaries)
- Birth Date (Birthdays)
- Service Award Date (Milestone Anniversaries)

Additionally, the dates must remain accurate when exported to **XLS files**.

---

## 5. Manage Accounts
In the **Manage Accounts** section, date fields must remain consistent across all options in the **Actions dropdown**.

### Areas affected
- Edit Profile → Service date
- Online Statement → Service anniversary date
- Permissions → Service anniversary date
- Points Management → Service anniversary date

These dates must accurately reflect the stored values regardless of user location or time zone.

---

## 6. Reports – Awards and Rewards

### a. Upcoming Anniversary and Birthday Reports
Dates must display correctly in the following report types:

- Service Award Anniversary
- Birthday Report

These values must also remain consistent when exported to:

- XLS
- CSV

### b. Selection History
The **anniversary date** should be displayed correctly in selection history records.

### c. Expired Awards
The **anniversary date** associated with expired awards should also display accurately.

---

## 7. Order History
The dates shown in the **Order History report** should match the dates stored in **Backstage → Nominations Management**.

However, the client administrator observed that some dates appeared **one day earlier**, indicating a potential **time zone conversion issue**.

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
