# 🔎 Lost & Found Portal

A web application where users report lost or found items and an admin moderates the platform.
Built with **Spring Boot** as an enterprise systems development project, following a layered
architecture (controller → service → repository).

![Java](https://img.shields.io/badge/Java%2017-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

## ✨ Features

- **Accounts:** registration and login with **Spring Security**, BCrypt-hashed passwords and two roles (`USER`, `ADMIN`)
- **Item reports:** create, edit and delete lost/found items with type, status and an image upload
- **My items:** each user manages their own reports and marks an item as resolved
- **Item details** page for every report
- **Admin dashboard:** promote or demote users, delete users and remove any item
- **Validation** on all forms (Bean Validation)
- **Access control by route:** `/admin/**` is admin-only, and the app area requires a logged-in user

## 🏗️ Architecture

```
lostfound/src/main/java/com/nikoliadis/swe6002/lostfound/
├── controller/   Auth, Home, LostItem, MyItems, ItemDetails, Admin
├── service/      LostItemService, UserService (interfaces + implementations)
├── repository/   Spring Data JPA repositories
├── model/        JPA entities (User, LostItem) + form objects and enums
├── security/     SecurityConfig, CustomUserDetailsService
└── config/       DataInitializer (seeds an admin account), WebConfig (serves uploads)
```

## 🛠️ Run locally

Requirements: **Java 17+** and **MySQL** (for example via XAMPP).

1. Create a database named `lostfound_db`. Tables are created automatically by JPA.
2. Check the credentials in `lostfound/src/main/resources/application.properties` (default: `root` with an empty password).
3. Start the app:
   ```bash
   cd lostfound
   ./mvnw spring-boot:run        # Windows: mvnw.cmd spring-boot:run
   ```
4. Open <http://localhost:8080>. A default admin account is created on first start: **admin / admin123**.

---

Built by **[Nikolaos Nikoliadis](https://github.com/Nikoliadis)** · Enterprise Systems Development module (SWE6002).
