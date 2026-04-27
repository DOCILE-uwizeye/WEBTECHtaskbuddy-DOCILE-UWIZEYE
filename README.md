# WEBTECHtaskbuddy-DOCILE-UWIZEYE
# Task Buddy — Project Documentation

**Task Buddy** is a full-stack Personal Task Manager application built with a **Vue.js** frontend and a **Spring Boot** backend, connected to a **MongoDB Atlas** cloud database.

---

## 1. Login Page

![Login Page]<img width="446" height="520" alt="Screenshot 2026-04-27 035830" src="https://github.com/user-attachments/assets/062c8403-263d-49f0-87d9-9e7230a3b806" />


The Login page is the entry point of the application. It presents a clean card-style form with two fields: **Username** and **Password**, and a prominent **Login** button. A link at the bottom reads *"Need an account? Register"*, allowing new users to navigate to the registration page. The design uses the app's navy-blue branding and is centered on a light gray background.

---

## 2. Registration Page

![Registration Page]<img width="366" height="500" alt="Screenshot 2026-04-27 035958" src="https://github.com/user-attachments/assets/a29ba823-7071-4e54-b095-e5400d697291" />


The Register page mirrors the login layout but swaps the action button to **Register**. A secondary outlined button labeled *"Have an account? Login"* lets existing users navigate back. This page handles new user account creation, sending credentials to the backend for storage.

---

## 3. Dashboard — Task Management

![Dashboard]<img width="1127" height="536" alt="Screenshot 2026-04-27 042259" src="https://github.com/user-attachments/assets/4a30bb67-a64c-460e-bdc2-a46980515da6" />


After logging in, the user lands on the **Dashboard**. It contains:

- A **top navigation bar** displaying the app name, a welcome message with the logged-in username (`docile`), and buttons for **Profile** and **Logout**.
- An **Add Task form** with fields for Task Title, Description, Category (dropdown), Priority (dropdown), Status (dropdown), and Due Date.
- A **filter toolbar** with quick-filter buttons: All, To Do, In Progress, Done, Personal, Work, School.
- A **task card** showing an existing task (`work` / `school work`) with its category badge, priority badge, status badge, due date, a `Shared` label, and a **Delete** button.

---

## 4. Profile Page

![Profile Page]<img width="561" height="652" alt="Screenshot 2026-04-27 042647" src="https://github.com/user-attachments/assets/5aeede4a-cfce-406d-8241-481fff21a8aa" />


The **Profile page** lets users view and edit their personal information. It shows:

- A **Username** field (read-only display of `docile`).
- A **Bio** textarea where users can write about themselves.
- A **Save Profile** button to persist changes.
- A **My Task Stats** section (partially visible) that will show statistics about the user's tasks.

Navigation buttons at the top allow returning to the **Dashboard** or logging out.

---

## 5. 404 — Page Not Found

![404 Page]<img width="495" height="331" alt="Screenshot 2026-04-27 042858" src="https://github.com/user-attachments/assets/4f837e8e-e3fb-4cc5-a6dd-5bd6a1e9a944" />


A custom **404 error page** is implemented to handle unknown or invalid routes. It displays a large `404` heading, a *"Page not found"* message, and a **Go to Dashboard** button so users can easily recover and navigate back to the main page.

---

## 6. OpenAPI / Swagger Documentation

![Swagger UI]<img width="1366" height="650" alt="Screenshot 2026-04-27 043042" src="https://github.com/user-attachments/assets/33439bdb-d2af-49ad-a3c3-ccae8d773ad6" />


The Spring Boot backend exposes a **Swagger UI** (via SpringDoc OpenAPI 3.0) at `/v3/api-docs`, running on `http://localhost:9090`. The documented **Tasks API** includes the following endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/tasks/{id}` | Get task by ID |
| `PUT` | `/api/tasks/{id}` | Update a task |
| `DELETE` | `/api/tasks/{id}` | Delete a task |
| `GET` | `/api/tasks` | Get all tasks |
| `POST` | `/api/tasks` | Create a new task |

---

## 7. MongoDB Atlas — IP Access List

![MongoDB IP Access List]<img width="1353" height="619" alt="Screenshot 2026-04-27 044111" src="https://github.com/user-attachments/assets/094500bf-d74f-46f8-b4cd-15e9092fa09a" />


The MongoDB Atlas cluster is secured via an **IP Access List**. Two entries are configured:

- `41.186.136.61/32` — Added during the Auto Setup process (Active).
- `0.0.0.0/0` — "Allow all" rule, enabling connections from any IP address (Active).



---

## 8. MongoDB Atlas — Data Explorer (Tasks Collection)

![MongoDB Data Explorer]<img width="1298" height="600" alt="Screenshot 2026-04-27 044258" src="https://github.com/user-attachments/assets/b7311787-e98a-494f-968a-9a8ea02ef2de" />


The **Data Explorer** in MongoDB Atlas shows the `taskbuddy` database with a `tasks` collection containing **2 documents**. The first document visible has the following structure:

This confirms that tasks created in the frontend are successfully persisted to the cloud database.

---

## 9. MongoDB Atlas — Database Users

![MongoDB Database Users]<img width="1364" height="613" alt="Screenshot 2026-04-27 044423" src="https://github.com/user-attachments/assets/18ed057e-791f-4c15-9b44-963568dcfb4a" />


A dedicated **database user** named `uwizeyedocile_db_user` has been created for the application. It uses **SCRAM** authentication and has the **atlasAdmin** role on all resources. This user is what the Spring Boot backend uses in its connection string to authenticate with the Atlas cluster.

---

## 10. MongoDB Atlas — Data Explorer (Tasks Collection) *(repeated view)*

![MongoDB Data Explorer 2]<img width="1353" height="619" alt="Screenshot 2026-04-27 044111" src="https://github.com/user-attachments/assets/d57d04dd-b41d-4506-9ac0-6f7973fca371" />



A second view of the Data Explorer, confirming the same `tasks` collection data and the `taskbuddy` database structure under `Cluster0`.

---

## 11. MongoDB Atlas — Database Users *(repeated view)*

![MongoDB Database Users 2]<img width="1364" height="613" alt="Screenshot 2026-04-27 044423" src="https://github.com/user-attachments/assets/d7d25c63-66aa-40a0-b26d-53bcd13b32c9" />



A repeated confirmation of the database user setup showing `uwizeyedocile_db_user` with `atlasAdmin@admin` role and access to all resources.

---

## 12. VS Code — Backend Running (Spring Boot)

![VS Code Backend]<img width="1285" height="684" alt="Screenshot 2026-04-27 044646" src="https://github.com/user-attachments/assets/1dce2069-c089-4cfd-ba7d-d139ae6a64a8" />



The VS Code environment shows the **project structure** on the left with a Vue.js frontend (`src/components/TaskCard.vue`, `TaskForm.vue`, `TaskList.vue`, `App.vue`, `main.js`) and a Spring Boot `demo` backend. 

The backend starts successfully on **port 9090**, with logs confirming:
- Connection to MongoDB Atlas (`ac-hut0kih-shard-00-01`).
- Initialization of the Spring `DispatcherServlet`.
- SpringDoc OpenAPI resource initialized (344ms).

---



