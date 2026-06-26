# Fields & Relationships

## Project Title

**AI-Powered Customer Support & Service Automation using Salesforce Service Cloud, Flow, Prompt Builder, and Agentforce**

---

# Overview

Fields and relationships form the foundation of the Salesforce data model. They define how information is stored, organized, and connected across different objects. In this project, both standard and custom objects were configured to manage customer support operations efficiently.

---

# Standard Objects

The following standard Salesforce objects are used in the project.

## Account

Stores customer account information.

| Field Name      | Data Type | Description                          |
| --------------- | --------- | ------------------------------------ |
| Account Name    | Text      | Name of the customer or organization |
| Phone           | Phone     | Contact number                       |
| Email           | Email     | Customer email address               |
| Billing Address | Address   | Customer address                     |

---

## Contact

Stores individual customer details.

| Field Name | Data Type       | Description                 |
| ---------- | --------------- | --------------------------- |
| First Name | Text            | Customer first name         |
| Last Name  | Text            | Customer last name          |
| Email      | Email           | Contact email               |
| Phone      | Phone           | Contact number              |
| Account    | Lookup(Account) | Associated customer account |

---

## Case

Stores customer support requests.

| Field Name  | Data Type       | Description                       |
| ----------- | --------------- | --------------------------------- |
| Case Number | Auto Number     | Unique case identifier            |
| Subject     | Text            | Issue title                       |
| Description | Long Text       | Problem description               |
| Status      | Picklist        | Current case status               |
| Priority    | Picklist        | Priority level                    |
| Account     | Lookup(Account) | Related customer                  |
| Contact     | Lookup(Contact) | Customer contact                  |
| Product     | Lookup(Product) | Product associated with the issue |
| AI Summary  | Long Text       | AI-generated case summary         |

---

## Product

Stores product information.

| Field Name      | Data Type | Description                |
| --------------- | --------- | -------------------------- |
| Product Name    | Text      | Product name               |
| Product Code    | Text      | Product identifier         |
| Category        | Picklist  | Product category           |
| Warranty Period | Number    | Warranty duration (months) |

---

# Custom Objects

## Customer Order

Stores order information.

| Field Name   | Data Type       | Description          |
| ------------ | --------------- | -------------------- |
| Order Number | Auto Number     | Unique order ID      |
| Order Date   | Date            | Date of purchase     |
| Order Status | Picklist        | Current order status |
| Customer     | Lookup(Account) | Associated customer  |

---

## Warranty Claim

Stores warranty claim details.

| Field Name      | Data Type       | Description                  |
| --------------- | --------------- | ---------------------------- |
| Claim Number    | Auto Number     | Unique claim ID              |
| Claim Date      | Date            | Date of claim                |
| Warranty Status | Picklist        | Approval status              |
| Customer        | Lookup(Account) | Customer requesting warranty |
| Product         | Lookup(Product) | Product under warranty       |

---

# Object Relationships

The project uses Lookup relationships to connect related records.

| Parent Object | Child Object   | Relationship Type |
| ------------- | -------------- | ----------------- |
| Account       | Contact        | Lookup            |
| Account       | Case           | Lookup            |
| Contact       | Case           | Lookup            |
| Product       | Case           | Lookup            |
| Account       | Customer Order | Lookup            |
| Account       | Warranty Claim | Lookup            |
| Product       | Warranty Claim | Lookup            |

---

# Data Model Overview

The relationship between objects is shown below.

```text
Account
│
├── Contact
│
├── Customer Order
│
├── Case
│     ├── Product
│     └── AI Summary
│
└── Warranty Claim
      └── Product
```

---

# Benefits of the Data Model

The configured fields and relationships provide the following benefits:

* Centralized storage of customer information.
* Efficient tracking of products and orders.
* Better organization of customer support cases.
* Simplified warranty claim management.
* Improved reporting and analytics.
* Accurate AI-generated summaries using related record information.

---

# Conclusion

The fields and relationships were carefully designed to support the AI-Powered Customer Support & Service Automation system. By combining standard Salesforce objects with custom objects and Lookup relationships, the application provides a structured, scalable, and efficient data model that supports automation, AI integration, and effective customer service management.
