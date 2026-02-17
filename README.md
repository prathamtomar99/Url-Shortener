# 🔗 URL Shortener

A full-stack URL shortening service built with **Spring Boot** and **React**. This application allows users to convert long URLs into manageable, short links.

**Live Demo:** [https://pratham-short.netlify.app/](https://pratham-short.netlify.app/)

---

## Tech Stack

**Backend**
* **Framework:** Spring Boot (v3.4.0)
* **Language:** Java 17
* **Build Tool:** Maven
* **Database Access:** Spring Data JPA, JDBC
* **Utilities:** Lombok

**Frontend**
* **Framework:** React.js
* **Hosting:** Netlify

---

## Features

* **URL Shortening:** Generate concise aliases for long URLs.
* **Redirection:** Fast redirection from short links to original destinations.
* **Clean UI:** Simple and responsive React frontend.
* **REST API:** Robust backend endpoints for URL management.

---

## Getting Started

Follow these instructions to set up the project locally.

### 1. Backend Setup (Spring Boot)

Navigate to the backend directory and run the application.

```bash
cd url-shortener-sb

# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
