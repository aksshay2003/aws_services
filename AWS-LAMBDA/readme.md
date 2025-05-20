# AWS Lambda

## Overview

This lab guides you through creating a serverless AWS Lambda function using Python, testing it, and integrating it with DynamoDB to retrieve data from a table. The Lambda function runs without managing servers and scales automatically.

---

## Part 1: AWS Lambda Setup

- **Login** to your AWS Console.
- Search and open **Lambda** service.
- **Create Function**:
  - Author from scratch.
  - Function Name: `Lambda-Rollno`
  - Runtime: Python (choose appropriate version, e.g., Python 3.x)
  - Architecture: x64
  - Execution Role: Use an existing role (`Lab Role`).
  - Additional configurations: Defaults.
- Add the following print statements in the function code:
  ```python
  print("Hello Welcome to Lambda Environment")
  print("My Roll No is _____")
  ```
