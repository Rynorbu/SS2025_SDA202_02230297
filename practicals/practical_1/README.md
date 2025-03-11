## Automated Assignment Submission Portal

### Introduction

This report shows the Interaction Overview Diagram (IoD) and Use Case Diagram (UCD) for an Automated Assignment Submission Portal. The portal is designed to make grading easier for SWE (Software Engineering) courses. The system will automatically grade assignments, check for plagiarism, and improve auditing and integration with the Learning Management System (LMS).

## Methodology  


**1 .Interaction Diagram (IoD)**

This diagram focuses on the flow of interactions between the Student and Professor during the assignment submission and grading process.

Key Interactions:

- Professor:

    - Sets the assignment criteria and requirements.

    - Executes the submitted code for evaluation.

    - Grades the assignments based on the provided criteria.

- Student:

    - Completes the assignment as per the given requirements.

    - Writes the necessary code for the assignment.

    - Submits the code to GitHub for evaluation.

Decision Points:

- If the submission is made on time, the professor clones the repository and proceeds with grading.
- If the submission is late, the system automatically rejects the submission.
- Once all submissions are graded or updated, the process ends.


<b>2. Interaction Overview Diagram (IoD)</b>

Combines parts from the Use Case Diagram (UCD) and Interaction Diagram (IoD) to give a clear, overall picture of how the system works.
- Key components included: 
  - **Submission System:** Allows students to submit assignments.
  - **Deadline Check:** Validates if submission is on time or late.
  - **Cloning & Validation:** Professor clonesthe submitted assignment and verifies the assignments.
  - **Code Execution:** Runs submitted code for evaluation.
  - **Manual Review:** Professor manually checks code if needed.
  - **Plagiarism Check:** Checks if the submitted work is original and not copied from others.
  - **Grading System:** Assigns grades to the submissions and updates them accordingly.

<b>3. Use Case Diagram</b>

This diagram provides a clear overview of the system's functionality and the interactions between actors and use cases.
- Included use cases such as:  
  - **Student**: Upload Source Code, View Grade and resubmit the assignmet for more marks.  
  - **Professor**: Review submission, view plagarism report Define Grading Criteria, Set Due Date and Time.  
  - **LMS/System**: Runs the code, stores grades, generate automatic grading, check deadine.
  - **plagarism**: Comapre submission, Check against external service.
  - **Regular body**: Audit grades
- Relationships:  
  - `<extend>`: Re-submission is an extension of normal submission.
  - `<include>`: Plagiarism report depends on comparison.

## System Overview

<details>

### Interaction overview Diagram


### Actor

- **Professor:** Reponsible for setting assignment criteria, excecuting codes, and grading assignment.
- **Student:** Responsible for doing the assignment given by the professor, writing code the assigment and submiting the code to GitHub.


![Interaction Diagram](assets/Interaction%20overview%20diagram(IOD).png)  
*Figure 1: Interaction Diagram*

### Explanation of Key Steps

### Professor Sets Assignment Details

- The process starts with the professor providing assignment details to students. This includes the deadline, instructions, and grading criteria.

### Student Submits Assignment
- Based on the assignment details the student writes the code and after completing the assignment the student pushes his code to his GitHub repository.

- The system checks if the submission was made before the deadline.

    - If the submission is on time, the system accepts it, and the professor evaluates the code.
    - If the submission is late, the system rejects it, and no further evaluation happens.
 
- If the submission is on time, the professor clones or forks the student’s repository. The professor runs the code to check its functionality and manually inspects the code in VS Code for quality and requirements.

- The professor checks if the code meets the assignment requirements and runs without errors.

    - If the code is valid, the professor assigns a grade.

    - If the code is invalid, the assignment is rejected, and the student is notified to fix and resubmit the code.   

- Based on the predefined criteria, the professor evaluates the code and assigns a grade. This grade is then recorded in the grading system.
</details>

<details>

### 2. Interaction Overview Diagram

![Interaction overview Diagram](assets/Interaction%20overview%20diagram.png)  
*Figure 2: Interaction Overview Diagram*


### Interactions

- The professor decides how assignments will be graded and sets the due date. 

- The student uploads their code before the deadline.

- If the student submits the assignment after the deadline, it is rejected. If it is on time, the process continues.

- Professor clones the assignment – The professor makes a copy of the submitted code to check it.

- The system reviews the submission:
    - If the assignment is not valid, it is rejected.
    - If the assignment is valid, it moves to the next step.

- The professor can review the code in two ways:

    - Manually checking the code.
    - Running the code to see if it works correctly.

- The system checks if the student copied the code from somewhere else.

- Based on how well the code works and whether it follows the grading rules, the professor gives a grade.

- The final grade is recorded, and the process is complete.

</details>

<details>

### Use Case Diagram

The Use Case Diagram provided a high-level overview of the system's functionality. 

![Interaction overview Diagram](assets/Use%20case%20diagram.png)  
*Figure 3: Use Case Diagram*

### Actors

- Student – Submits assignments and checks grades.
- Professor – Reviews submissions, sets grading criteria, and views plagiarism reports.
- LMS (Learning Management System) – Handles authentication, grading, and submissions.
- Plagiarism Checker – Compares assignments for similarity.
- Regulatory Body – Audits grades.

### Workflow of the Use Case Diagram

1. Student Submits an Assignment

- A student submits an assignment. The system runs the code (if it’s a programming assignment) → Includes.
- The system stores the grades after processing → Includes.
- If needed, the student can re-submit the assignment, which is an extension of the original submission.

2. Student Views Grades

- The student logs in (authentication is required).
- They view grades, which includes authentication to ensure secure access.

3. Professor Reviews Assignments

- The professor logs in and reviews student submissions.
- Includes authentication to ensure only authorized users access submissions.

4. Professor Checks for Plagiarism

- The professor views the plagiarism report.
- The system compares the submission with other students.
- If needed, the system checks against an external service like Turnitin → Extends.

5. Professor Sets Grading Rules and Deadlines

- The professor sets grading criteria and due dates.
- The system checks the deadline for each assignment → Extends.

6. Automatic Grading System 

- The system grades the assignment automatically.
- It stores the grades after grading → Includes.
- It rejects late submissions if they are past the deadline → Includes.

7. Regulatory Body Audits Grades

- A regulatory body (like an admin or an external authority) audits grades.

</details>