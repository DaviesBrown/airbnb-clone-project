# Airbnb Clone Project
### Overview Of The Project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

### Project Goals
> **User Management**, **Property Management**, **Booking System**, **Payment Processing**, **Review System**

### Tech Stack
> Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, Docker, CI/CD Pipelines


## Team Roles
- **Backend Developer**: Responsible for implementing API endpoints, database schemas, and business logic.
- **Database Administrator**: Manages database design, indexing, and optimizations.
- **DevOps Engineer**: Handles deployment, monitoring, and scaling of the backend services.
- **QA Engineer**: Ensures the backend functionalities are thoroughly tested and meet quality standards.


## Technology Stack
- **Django**: A high-level Python web framework used for building the RESTful API.
- **Django REST Framework**: Provides tools for creating and managing RESTful APIs.
- **PostgreSQL**: A powerful relational database used for data storage.
- **GraphQL**: Allows for flexible and efficient querying of data.
- **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.
- **Redis**: Used for caching and session management.
- **Docker**: Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## Database Design
### Entities

### 1. **User**
Represents both guests and hosts.

**Important Fields:**
- `id`: Unique identifier for each user.
- `name`: Full name of the user.
- `email`: Used for login and communication.
- `password_hash`: Encrypted password for authentication.
- `role`: Host or Guest (could also be both).

**Relationships:**
- A **User** can create **multiple Properties** (if they're a host).
- A **User** can make **multiple Bookings** (if they're a guest).
- A **User** can write **multiple Reviews**.
- A **User** can have **multiple Payments**.

---

### 2. **Property**
Represents a listed rental space.

**Important Fields:**
- `id`: Unique identifier.
- `title`: Property name or short description.
- `description`: Detailed overview of the property.
- `location`: Address or coordinates.
- `host_id`: Foreign key referencing the User who owns the property.

**Relationships:**
- A **Property** belongs to one **User** (host).
- A **Property** can have multiple **Bookings**.
- A **Property** can have multiple **Reviews**.

---

### 3. **Booking**
Represents a reservation made by a guest.

**Important Fields:**
- `id`: Unique identifier.
- `user_id`: Foreign key referencing the User who booked.
- `property_id`: Foreign key referencing the Property booked.
- `start_date`: Start date of the reservation.
- `end_date`: End date of the reservation.

**Relationships:**
- A **Booking** belongs to one **User** (guest).
- A **Booking** belongs to one **Property**.
- A **Booking** can have one associated **Payment**.

---

### 4. **Review**
Represents feedback left by a guest for a property.

**Important Fields:**
- `id`: Unique identifier.
- `user_id`: User who left the review.
- `property_id`: Property being reviewed.
- `rating`: Numerical score (e.g., 1-5).
- `comment`: Written feedback.

**Relationships:**
- A **Review** belongs to one **User**.
- A **Review** belongs to one **Property**.

---

### 5. **Payment**
Handles transaction records for bookings.

**Important Fields:**
- `id`: Unique identifier.
- `booking_id`: Reference to the related Booking.
- `amount`: Total payment amount.
- `payment_method`: Credit card, PayPal, etc.
- `payment_status`: Paid, Failed, Pending.

**Relationships:**
- A **Payment** is linked to one **Booking**.
- A **Payment** indirectly relates to one **User** through the Booking.

## Feature Breakdown
Here’s a list of the **main features** from the Airbnb Clone Project, along with short descriptions of how each contributes to the overall platform:

### 1. **User Management**
Handles user registration, login, authentication, and profile settings.  
This feature ensures that users can securely access the platform, manage their accounts, and distinguish between roles such as guest and host.


### 2. **Property Management**
Allows hosts to create, update, and delete property listings.  
It enables the platform to showcase available accommodations, providing essential details like location, pricing, photos, and amenities to attract potential guests.


### 3. **Booking System**
Enables guests to reserve available properties and view their booking history.  
This is the core functionality of the application, ensuring users can select dates, check availability, and complete the reservation process seamlessly.


### 4. **Payment Processing**
Facilitates secure transactions between guests and hosts.  
By integrating a payment gateway, this feature handles payment collection, status tracking, and receipts, ensuring a smooth and trustworthy financial experience for both parties.


### 5. **Review System**
Lets guests leave ratings and feedback on properties after their stay.  
This adds transparency and trust to the platform, helping future guests make informed decisions and encouraging hosts to maintain high-quality service.

