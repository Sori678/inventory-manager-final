# Inventory Manager CLI

A real-world inspired command-line tool designed for small businesses to manage inventory data.  
The application provides full CRUD functionality, CSV import/export, JSON persistence, and robust input validation — all inside an intuitive terminal interface.

---

## Table of Contents

- [Project Overview](#project-overview)
- [User Goals](#user-goals)
- [Site Owner Goals](#site-owner-goals)
- [Features](#features)
- [Data Model](#data-model)
- [Flowchart](#flowchart)
- [Technologies Used](#technologies-used)
- [Testing](#testing)
- [PEP8-Validation](#pep8-validation)
- [Bugs-and-Fixes](#bugs-and-fixes)
- [Deployment](#deployment)
- [How-to-Run-Locally](#how-to-run-locally)
- [Credits--Attribution](#credits--attribution)

---

# Project Overview

Inventory Manager CLI is a Python-based command-line application that enables users to efficiently track and manage product stock.

It allows users to:

- Add new products  
- Edit existing product details  
- Delete unwanted entries  
- Search products by name  
- Export inventory to CSV  
- Import inventory from CSV  
- Automatically save data to JSON  

All operations include **error handling**, **input validation**, and **clear user feedback**.

The project aligns with the Code Institute’s *Python Essentials* assessment requirements and demonstrates clean code, modular functions, defensive programming, and robust data handling.

---

# User Goals

- Easily manage product information  
- Search for products quickly  
- Import/export inventory files  
- Use a simple and intuitive interface  

# Site Owner Goals

- Provide a reliable database-like system using JSON  
- Ensure the user cannot break the application through invalid input  
- Offer helpful messages and confirmations  
- Maintain clean, maintainable, readable code  

---

# Features

### ✔ Add Product
Adds a new item with:
- Name  
- Quantity  
- Price  
With validation:
- Positive values  
- Non-empty names  
- Handles `ValueError` gracefully  

### ✔ Update Product
Allows modifying:
- Quantity  
- Price  
Empty input keeps the original value.

### ✔ Delete Product
Deletes by ID, with confirmation prompt:
```
Are you sure? (y/n)
```

### ✔ Search Products
Case-insensitive partial search.  
Example: “app” matches “Apple” and “Pineapple”.

### ✔ Export to CSV
Exports the inventory into `inventory_export.csv`.

### ✔ Import from CSV  
Reads `inventory_import.csv` and adds products.  
Invalid rows are skipped safely.

### ✔ JSON Data Persistence
Data automatically loads at startup and saves on exit.

### ✔ Defensive Programming
- Handles invalid numeric inputs  
- Catches missing files  
- Prevents negative values  
- Protects against corrupted JSON  

---

# Data Model

Product structure stored in `inventory.json`:

```json
{
    "id": 1,
    "name": "Apple",
    "quantity": 10,
    "price": 1.5
}
```

The inventory is a list of these objects.

---

# Flowchart

```
[Start]
   ↓
Load JSON → If missing: create empty list
   ↓
Show Menu
   ↓
User selects option ─────────┐
   ↓                         │
Perform operation            │
   ↓                         │
Save/Exit? ── No ────────────┘
   ↓
Save data to JSON
   ↓
[End]
```

---

# Technologies Used

- **Python 3**  
- **JSON** (data persistence)  
- **CSV module** (import/export)  
- **Replit** (cloud deployment)  
- **Git & GitHub** (version control)  
- **PEP8 Validator** (code style compliance)  

---

# Testing

### ✔ Manual Testing Table

| Feature | Action | Expected | Result |
|--------|--------|----------|--------|
| Load data | Start program | Inventory loads without crash | Pass |
| Add product | Enter name, qty, price | Product added | Pass |
| Add invalid product | Enter text instead of number | Error message | Pass |
| Update product | Modify qty/price | Updated successfully | Pass |
| Update invalid | Negative values | Error message | Pass |
| Delete product | Enter ID | Removed with confirmation | Pass |
| Delete invalid | ID not found | Error message | Pass |
| Search | Type partial name | Returns matches | Pass |
| Export CSV | Option 6 | File created | Pass |
| Import CSV | Option 7 | Products imported | Pass |
| Save and exit | Option 8 | JSON saved | Pass |

---

# PEP8 Validation

The Python code was validated using:

- **Code Institute Python Linter**  
- **PEP8 Online Validator**

Results:

✔ No major issues  
✔ Proper indentation  
✔ No unused variables  
✔ No overly long lines  
✔ Clean and readable code  

---

# Bugs and Fixes

### Fixed:
- Incorrect function ordering → reorganized  
- Indentation error in `update_product` → fixed  
- Missing CSV import validation → added `try/except`  
- Non-PEP8 formatting → full refactor  

### Remaining Bugs:
No known bugs at the time of submission.

---

# Deployment

### ✔ Live Deployment (Replit)

The project is deployed online using Replit and can be accessed here:

🔗 **https://replit.com/@biv7sor/inventory-manager-cli?v=1**

This deployment fully satisfies Learning Outcome LO9 for cloud-based command-line application deployment.

---

# How to Run Locally

### 1. Clone the repository:
```
git clone https://github.com/YOUR_USERNAME/inventory-manager-cli
```

### 2. Navigate to the project folder:
```
cd inventory-manager-cli
```

### 3. Run the application:
```
python run.py
```

---

# Credits & Attribution

- All code written entirely by **Sorin Bivol**.
- No code was copied from external GitHub repositories or tutorials.
- General knowledge and syntactic references:
  - MDN Web Docs  
  - W3Schools  
  - StackOverflow (conceptual clarification only)  
  - Python official documentation  

This project was created for the **Code Institute Full Stack Diploma – Portfolio Project 3 (Python Essentials)**.
