# Django Backend Junior Assessment: Coworking Space API

## 📌 Overview
The goal of this task is to build a simplified **Booking Engine** for a coworking space. This test evaluates your ability to design database relationships, handle complex business logic, and implement custom validations in Django Rest Framework (DRF).

---

## 🛠 Business Requirements

You need to create an API that manages **Desks** and **Bookings**.

### 1. Data Models
* **Desk**: Should have a unique `desk_number` (e.g., "A101") and a `price_per_hour`.
* **Booking**: Should link a `User`, a `Desk`, a `start_time`, and an `end_time`.

### 2. Functional Endpoints
* `GET /api/desks/`: List all desks.
* `POST /api/bookings/`: Create a new booking for the authenticated user.
* `GET /api/my-bookings/`: Show only the bookings belonging to the logged-in user.

### 3. Core Logic & Constraints (The Challenge)
Your code must strictly enforce the following rules:
1.  **No Overlaps**: A desk cannot be booked if it overlaps with an existing booking for the *same desk* at that time.
2.  **Minimum Stay**: Each booking must be at least **1 hour** long.
3.  **Cool-down Period**: A user cannot create a new booking that starts within **30 minutes** of their own previous booking ending (to prevent monopolizing desks).
4.  **Auto-Calculation**: The API response must include a `total_price` field, calculated as: `(duration_in_hours) * (desk.price_per_hour)`.

---

## 📋 Technical Requirements
* **Framework**: Django & Django Rest Framework (DRF).
* **Database**: SQLite.
* **Authentication**: Simple Token Authentication or Session Authentication is fine.
* **Validation**: Logic should be implemented within the **Serializer** or **Model** layer.
* **Code Quality**: Use meaningful variable names and include English comments for complex logic.

---

## 🚀 Submission Instructions
1.  **Fork** this repository.
2.  Complete the task within **1 to 2 hours**.
3.  Commit your code with clear, descriptive messages.
4.  Update the bottom of this `README.md` with:
    * Instructions on how to run the project.
    * An example of the JSON payload for a `POST` request.
5.  Send the link to your repository or submit a Pull Request.

---
*Good luck! We are looking for clean, logical, and maintainable code.*
