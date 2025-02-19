# TableMerger-AI Case Study

## Overview

**TableMerger-AI** is an intelligent system developed to seamlessly merge data from two different tables, such as employee records and department assignments. Its primary goal is to integrate tabular data provided in CSV or JSON formats while ensuring data accuracy through rigorous validation and error handling. The system validates the input, performs a precise merge using a common key (employee_id), and provides a detailed, step-by-step explanation of the process in a user-friendly manner that even non-technical users can understand.

## Features

- **Data Validation:**  
  TableMerger-AI first checks the input to ensure that:
  - The data is provided in the correct format (CSV or JSON within markdown code blocks).
  - The language is English.
  - All required fields are present in each table. For example, the employee records table must include `employee_id`, `name`, `age`, and `position`, while the department assignments table must include `employee_id`, `department`, and `location`.
  - All fields have the appropriate data types, and key constraints (such as unique employee IDs) are enforced.
  
- **Table Merging:**  
  The system merges the two tables by using `employee_id` as the join key. It combines records that exist in both tables and assigns default values like "Unassigned" for missing department details when necessary. The merge is designed to handle discrepancies and inconsistencies gracefully.

- **Step-by-Step Explanations:**  
  After merging, TableMerger-AI provides a detailed explanation of how each record was processed. This includes a breakdown of the merge logic, error handling (such as missing or unmatched keys), and a preview of the final merged table.

- **Feedback and Iterative Improvement:**  
  The system engages users by asking for feedback after processing. It prompts questions like, "Would you like any additional filtering or sorting?" and "Did this merge meet your expectations? Rate this process (1-5 ⭐)." This allows users to suggest improvements, ensuring that TableMerger-AI continues to evolve based on real-world usage.

## System Prompt

The following system prompt governs TableMerger-AI’s behavior, detailing the rules for data validation, merging logic, error handling, and response formatting:

```markdown
**[system]**
You are TableMerge-AI, an intelligent assistant designed to merge two tabular datasets (employee records and department assignments) provided in CSV or JSON format. Your tasks include:
- Validating the data to ensure that both tables contain all required fields with correct data types.
- Verifying that the employee records table has unique `employee_id` values.
- Ensuring that every `employee_id` in the department table exists in the employee records table, or else flagging them as warnings.
- Merging the tables using `employee_id` as the join key. If an employee record does not have a corresponding department, assign default values ("Unassigned") to the missing fields.
- Providing a detailed, step-by-step explanation of the merge process, including a summary of data warnings and a preview of the final merged table.
- Asking for user feedback after processing, and if any rating is given below 4, request suggestions for improvement.
- Adhering to clear and friendly communication, ensuring that non-technical users can easily understand the steps involved.
```

## Metadata

- **Project Name:** TableMerger-AI  
- **Version:** 1.0.0  
- **Author:** Usman Ashfaq 
- **Keywords:** Data Integration, Table Merge, CSV, JSON, Employee Records, Department Assignments, Data Validation, Error Handling

## Variations and Test Flows

### Flow 1: Basic Greeting and Template Request
- **User Action:** The user starts with a simple "hi" message.
- **Assistant Response:** The system greets the user in a friendly, default manner and asks if they need a template for data input.
- **User Action:** The user accepts the offer and requests a template.
- **Assistant Response:** The system provides clear CSV and JSON template examples.
- **User Action:** The user submits two CSV files containing employee records and department assignments.
- **Assistant Response:** TableMerger-AI validates the data, merges the tables, and returns a detailed summary report, including any data warnings.
- **Feedback:** The user reviews the merged result and gives positive feedback.

### Flow 2: Time-based Greeting and No Template Request
- **User Action:** The user greets with a time-specific message, for example, "Good afternoon, I'm ready to work on my tables."
- **Assistant Response:** The system responds with a time-appropriate greeting such as:  
  **"☀️ Good afternoon, table architect! Ready to combine your data effortlessly?"**
- **User Action:** The user provides CSV data directly, without asking for a template.
- **Assistant Response:** The system processes the data, performs the merge, and returns a comprehensive summary report.
- **Feedback:** The user rates the process highly (e.g., a 5-star rating), and the system acknowledges the positive feedback.

### Flow 3: JSON Data with Errors and Corrections
- **User Action:** The user submits JSON data containing the tables, but with a missing required field in one of the datasets.
- **Assistant Response:** The system detects the error, returns an explicit error message indicating the missing field, and provides an example of a correct data format.
- **User Action:** The user corrects the JSON data and resubmits it, but this time includes an invalid data type for one field.
- **Assistant Response:** The system returns another error message detailing the data type issue and lists the allowed data types.
- **User Action:** The user finally submits fully corrected JSON data.
- **Assistant Response:** TableMerger-AI processes the data, performs the merge, and returns a detailed report along with a step-by-step breakdown.
- **Feedback:** The user rates the analysis as 3, prompting the system to ask for suggestions on how to improve the process.

### Flow 4: JSON Data with 8 Records and Data Type Errors
- **User Action:** The user provides JSON data with 8 records but uses incorrect data types for some required fields.
- **Assistant Response:** The system greets the user by name and returns a precise error message regarding the invalid data types.
- **User Action:** The user submits corrected JSON data with the proper data types.
- **Assistant Response:** The system processes the corrected data, performs the merge, and returns a detailed summary report.
- **Feedback:** The user gives a 3-star rating, leading the system to ask, "How can I improve the data merging process for you?"

## Conclusion

TableMerger-AI is a robust, flexible, and user-centric tool that automates the merging of tabular data from multiple sources. By enforcing strict validation rules and providing detailed, step-by-step explanations of the merging process, it ensures both accuracy and clarity in its outputs. The various test flows demonstrate how the system handles different data inputs, error scenarios, and user feedback to continuously improve its performance. This case study illustrates that TableMerger-AI not only simplifies the complex task of data integration but also makes it accessible to non-technical users, ultimately aiding in efficient data management and decision-making.
