# Automation Script using OCR library
Thank you for visiting my GitHub repository! 😊
This project is focused on automating a common but time-consuming task using Python. If you're working on something similar, I hope this script helps speed things up for you.

---

## 📘 Problem Statement

The goal of this project is to **develop a Python script** that processes a directory containing PDF files (which may be digital or scanned books). The script analyzes each file and generates a **structured Excel sheet**, where each row contains catalog information for one book.

---

## 📊 Excel Output Structure

The generated Excel file includes the following columns:

| **Column Name**                  | **Description**                         |
| -------------------------------- | --------------------------------------- |
| **Book Title**                   | Full title of the book                  |
| **Author**                       | Name of the author, or **"Unknown"**    |
| **Editor**                       | Name of the editor, or **"Unknown"**    |
| **Year of Publishing**           | Year of publication, or **"Unknown"**   |
| **Publisher**                    | Name of the publisher, or **"Unknown"** |
| **Language**                     | Language of the book, or **"Unknown"**  |
| **Number of Pages** *(Optional)* | Total number of pages in the book       |
| **Format** *(Optional)*          | File format (e.g., **PDF**)             |

---
Here’s an improved and well-structured version of your description, with a clear and friendly tone, suitable for inclusion in a GitHub README or as inline documentation for your notebook/script:

---

## 📜 Step-by-Step Description of Each Code Cell

### ✅ Library Installation

This cell installs all the required Python libraries:

* **`PyPDF2`** – for reading and extracting metadata from PDF files.
* **`langdetect`** – for automatic language detection from text.
* **`pandas`** – for organizing and manipulating tabular data.
* **`openpyxl`** – for exporting data to Excel files.
* **`pytesseract`** – for performing Optical Character Recognition (OCR) on scanned PDFs.

---

### 📁 Reading PDF Files and Extracting Basic Info

This cell:

* Reads all PDF files from a specified folder.
* Extracts the **file name**, and attempts to infer **title** and **author** based on the file name structure.
* Uses `PyPDF2` to count the number of pages in each file.
* Initializes lists to store this basic metadata.

---

### 📊 Display Initial DataFrame

This cell displays the initial **pandas DataFrame**, which shows:

* File Name
* Book Title
* Author (if inferred from file name)
* Format (PDF)
* Page Count

---

### 🔍 Performing OCR and Language Detection

This cell:

* Runs OCR using `pytesseract` on the **first 5 pages** of each PDF.
* Extracts text from these pages for analysis.
* Uses `langdetect` to identify the **language** of the extracted content.
* Stores the text and language data in separate dictionaries.

---

### 🧠 Extracting Metadata from OCR Text

This cell analyzes the OCR-extracted text to identify key metadata such as:

* **Author**
* **Editor**
* **Publisher**
* **Year of Publication**

It uses **predefined keyword patterns** and regular expressions to extract this data, which is stored in corresponding lists.

---

### 📋 Creating the Final Metadata DataFrame

This cell:

* Creates a new DataFrame `df_final` using the metadata extracted from the OCR text.
* Includes columns for File Name, Author, Editor, Publisher, Year of Publication, and Language.
* Displays the resulting table for verification.

---

### 🔗 Merging and Cleaning Metadata

This cell:

* Merges the initial and final DataFrames (`df` and `df_final`) on **File Name**.
* Prioritizes author info inferred from the file name, if available.
* Cleans up inconsistent values in columns like Title and Author.
* Drops unnecessary or duplicate columns to produce a clean and final DataFrame: `df_merged`.

---

### 📌 Display Final DataFrame

This cell simply displays the **final merged and cleaned DataFrame**, containing all available metadata for each book in one place.

---

### 💾 Save to Excel

This last cell:

* Saves the final DataFrame to an Excel file named **`PDF_Metadata_Extracted.xlsx`**.
* This file will be generated in the same directory where your PDF books are located.

---
