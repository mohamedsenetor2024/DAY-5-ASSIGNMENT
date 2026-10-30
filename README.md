A) User Manual Procedure — GitHub Repository 

Creating a GitHub Repository and Making a First Commit
Prerequisites
Before starting, make sure you have:
A computer connected to the internet.
A GitHub account.
Git installed on your computer.
Basic knowledge of opening a terminal or Git Bash.
A project folder containing at least one file.
Procedure
Step 1: Open GitHub
Action: Open GitHub in a web browser and sign in to your account.
Expected result: Your GitHub account homepage appears.
Step 2: Create a new repository
Action: Select New repository from your GitHub account.
Expected result: The Create a new repository page appears.
Step 3: Enter the repository name
Action: Enter my-first-project in the repository name field.
Expected result: The repository name is displayed in the form.
Step 4: Set the repository visibility
Action: Select Public as the repository visibility.
Expected result: The Public option is selected.
Step 5: Create the repository
Action: Select Create repository.
Expected result: GitHub opens the new repository page.
Step 6: Open Git Bash
Action: Open Git Bash on your computer.
Expected result: A Git Bash terminal window appears.
Step 7: Navigate to the project folder
Action: Use the cd command to move into your project folder.
Expected result: The terminal prompt shows that you are inside the project folder.
Step 8: Initialize Git
Action: Run git init.
Expected result: Git creates a local repository in the project folder.
Step 9: Add the project files
Action: Run git add ..
Expected result: The project files are staged for the first commit.
Step 10: Create the first commit
Action: Run git commit -m "Initial commit".
Expected result: Git creates the first commit containing the staged files.
Step 11: Connect the local repository to GitHub
Action: Run git remote add origin https://github.com/YOUR-USERNAME/my-first-project.git.
Expected result: The local repository is connected to the GitHub repository.
Step 12: Rename the branch
Action: Run git branch -M main.
Expected result: The current branch is named main.
Step 13: Push the commit
Action: Run git push -u origin main.
Expected result: The first commit is uploaded to GitHub and the project files appear in the online repository.
Screenshot Description
The screenshot should show the GitHub repository page after the successful push. It should display the repository name, the main branch, the uploaded project files, and the Initial commit message.
Troubleshooting
Common error: remote origin already exists
This error means the local project is already connected to a remote repository.
Run:
git remote -v
to check the existing remote URL. If it is incorrect, replace it with:
git remote set-url origin https://github.com/YOUR-USERNAME/my-first-project.git
Then run:
git push -u origin main









B) API Reference Entry 

Create a New Task
Endpoint
HTTP Method: POST
Endpoint Path: /api/v1/projects/{projectId}/tasks
Description
Creates a new task inside a specified project. The authenticated user must have permission to create tasks in the project.
The task requires a title, assignee, due date, and priority. A description can optionally be included.
Path Parameters
Parameter
Type
Required
Description
projectId
string
Yes
Unique identifier of the project where the task will be created.

Request Body Parameters
Parameter
Type
Required
Description
title
string
Yes
Short name of the task.
description
string
No
Additional information about the task.
assigneeId
string
Yes
Unique ID of the user assigned to the task.
dueDate
string
Yes
Date when the task is due, using ISO 8601 date format (YYYY-MM-DD).
priority
string
Yes
Task priority. Allowed values are low, medium, or high.

Request Headers
Header
Required
Description
Authorization
Yes
Authentication token in the format Bearer <token>.
Content-Type
Yes
Must be application/json because the request body is JSON.

Example Request
POST /api/v1/projects/proj_1001/tasks
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI...
Content-Type: application/json
Request Body
{
  "title": "Complete project documentation",
  "description": "Write and review the technical documentation for the project.",
  "assigneeId": "usr_2045",
  "dueDate": "2026-09-15",
  "priority": "high"
}
Response Codes
HTTP Status
Meaning
201 Created
The task was successfully created.
400 Bad Request
The request contains invalid or missing data, such as an unsupported priority value or missing required field.
401 Unauthorized
The authentication token is missing, invalid, or expired.
403 Forbidden
The authenticated user does not have permission to create tasks in the specified project.
404 Not Found
The specified project or assignee does not exist.
409 Conflict
The request conflicts with the current project state or creates a duplicate task where duplicates are not permitted.
422 Unprocessable Entity
The request format is valid, but one or more values fail business validation.
500 Internal Server Error
An unexpected error occurred on the server.

Successful Response
Status: 201 Created
{
  "id": "task_7842",
  "projectId": "proj_1001",
  "title": "Complete project documentation",
  "description": "Write and review the technical documentation for the project.",
  "assigneeId": "usr_2045",
  "dueDate": "2026-09-15",
  "priority": "high",
  "status": "todo",
  "createdAt": "2026-08-23T11:42:18Z",
  "updatedAt": "2026-08-23T11:42:18Z"
}
Response Field Description
Field
Type
Description
id
string
Unique identifier assigned to the new task.
projectId
string
Identifier of the project containing the task.
title
string
Title of the created task.
description
string
Description provided when the task was created.
assigneeId
string
ID of the user assigned to the task.
dueDate
string
Task deadline in YYYY-MM-DD format.
priority
string
Task priority: low, medium, or high.
status
string
Initial task status. A newly created task starts as todo.
createdAt
string
Timestamp when the task was created.
updatedAt
string
Timestamp when the task was last updated.




Executive Summary
This four-week evaluation compared MySQL, PostgreSQL, and MongoDB as potential database systems for a new university student records management system. The evaluation focused on the system’s ability to manage structured student information, enrolment records, and grades; support up to 200 staff users accessing the system at the same time; maintain strong data integrity; and remain manageable by a small IT team with limited database expertise.
Based on these requirements, PostgreSQL is recommended as the preferred database. It provides strong support for reliable transactions and data integrity, making it well suited to sensitive student records. It also offers a mature and well-established platform that can be maintained without requiring a large specialist database team.
The two most important factors driving the decision were data integrity and ease of maintenance. Although all three options can support database applications, PostgreSQL provides the best overall balance between protecting the accuracy of student records and keeping ongoing administration manageable for the university.
The recommended choice will provide a dependable foundation for the student records system while supporting the university’s operational and data-management needs.

