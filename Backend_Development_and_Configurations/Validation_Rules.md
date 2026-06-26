# Validation Rules

## Project Title

**AI-Powered Customer Support & Service Automation using Salesforce Service Cloud, Flow, Prompt Builder, and Agentforce**

---

# Overview

Validation Rules are used in Salesforce to ensure that only accurate and complete data is saved in the system. They help maintain data integrity by preventing users from entering invalid or incomplete information into records.

In this project, validation rules were implemented on customer support objects to improve data quality, reduce errors, and ensure consistency across the application.

---

# Objectives

The validation rules were designed to:

* Ensure mandatory fields are completed.
* Prevent incorrect or incomplete data entry.
* Improve data consistency across objects.
* Support accurate reporting and AI-generated responses.
* Reduce manual data correction efforts.

---

# Implemented Validation Rules

## 1. Case Subject is Required

**Object:** Case

**Purpose:**
Ensures that every support case has a subject before it is saved.

**Validation:**

* The **Subject** field cannot be left blank.

**Expected Result:**
Users must provide a subject describing the customer's issue.

---

## 2. Priority Must Be Selected

**Object:** Case

**Purpose:**
Ensures that each support case is assigned a priority level.

**Validation:**

* The **Priority** field is mandatory.

**Expected Result:**
Every case is categorized as Low, Medium, or High priority.

---

## 3. Customer Email Validation

**Object:** Contact

**Purpose:**
Ensures that customer email addresses follow a valid email format.

**Validation:**

* Invalid email formats are not accepted.

**Expected Result:**
Only correctly formatted email addresses are stored.

---

## 4. Warranty Claim Date Validation

**Object:** Warranty Claim

**Purpose:**
Prevents users from entering a future date for warranty claims.

**Validation:**

* Claim Date cannot be greater than the current date.

**Expected Result:**
Warranty claims are recorded with valid dates only.

---

## 5. Product Warranty Period Validation

**Object:** Product

**Purpose:**
Ensures that the warranty period is a positive value.

**Validation:**

* Warranty Period must be greater than zero.

**Expected Result:**
Invalid warranty durations cannot be saved.

---

## 6. Case Status Validation

**Object:** Case

**Purpose:**
Ensures that every support case has a valid status before saving.

**Validation:**

* Status field cannot be blank.

**Expected Result:**
Each case progresses through a defined support lifecycle.

---

# Benefits

The implemented validation rules provide the following advantages:

* Improved data accuracy.
* Reduced duplicate or incomplete records.
* Better customer support documentation.
* Reliable AI-generated summaries.
* Consistent reporting and analytics.
* Enhanced user experience.

---

# Sample Validation Rules

| Validation Rule       | Object         | Purpose                                     |
| --------------------- | -------------- | ------------------------------------------- |
| Subject Required      | Case           | Prevent empty case subjects                 |
| Priority Required     | Case           | Ensure case priority is assigned            |
| Valid Email Format    | Contact        | Accept only valid email addresses           |
| Claim Date Validation | Warranty Claim | Prevent future claim dates                  |
| Warranty Period Check | Product        | Ensure warranty period is greater than zero |
| Status Required       | Case           | Ensure every case has a valid status        |

---

# Testing

Each validation rule was tested by attempting to save records with invalid or incomplete information.

**Expected Results:**

* Invalid records were rejected.
* Appropriate error messages were displayed.
* Valid records were saved successfully.

---

# Conclusion

Validation Rules play an essential role in maintaining the quality and reliability of customer support data. By enforcing mandatory fields, validating input values, and preventing incorrect entries, the Salesforce application ensures accurate information is available for reporting, automation, and AI-powered customer support features.
