# Automated REST API Testing & Validation Suite

[![Newman Tests](https://img.shields.io/badge/Newman-Passing-brightgreen.svg)](https://learning.postman.com/docs/collections/using-newman-cli/command-line-integration-with-newman/)
[![Postman Collection](https://img.shields.io/badge/Postman-v2.1-orange.svg)](https://www.postman.com/)
[![Assertions](https://img.shields.io/badge/Assertions-100%25%20Passed-blue.svg)](https://github.com/utkarshpatwa393-sys/postman-student-expert)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Production-grade automated REST API test collection and validation suite built with **Postman** and executed via **Newman CLI**. Features complete CRUD lifecycle coverage, query/path parameter handling, automated schema assertions, and dynamic collection variable management.

---

## 📌 Architecture & Features

This test suite executes automated regression and integration tests against a live RESTful Library API:

- **Full CRUD Operations**: Comprehensive testing across `GET`, `POST`, `PATCH`, and `DELETE` HTTP methods.
- **Dynamic Variable Chaining**: Automatically extracts and sets collection variables (`id`, `favoriteActor`) from runtime responses to link subsequent API requests.
- **Authentication**: Validates API Key authorization headers (`api-key`, `student-expert`) at both the collection and request levels.
- **Status Code & Schema Assertions**: Tests for `200 OK`, `201 Created`, and `204 No Content`, verifying JSON payload structure, property data types, and filtering logic.
- **CI/CD Ready**: Fully compatible with headless CI runners using **Newman CLI**.

---

## 🔍 Test Coverage & Endpoints

| # | Request Name | HTTP Method | Endpoint / Route | Assertion & Verification Logic | Status |
|---|:---|:---:|:---|:---|:---:|
| 1 | **get books** | `GET` | `/books` | Status `200 OK`, response array validation, response time check | ✅ PASS |
| 2 | **get fiction books** | `GET` | `/books?genre=fiction&checkedOut=false` | Status `200 OK`, query parameter validation, filtered results assertion | ✅ PASS |
| 3 | **get book by id** | `GET` | `/books/:id` | Status `200 OK`, dynamic path variable resolution, JSON schema assertion | ✅ PASS |
| 4 | **add a book** | `POST` | `/books` | Status `201 Created`, JSON payload verification, dynamic `id` persistence | ✅ PASS |
| 5 | **checkout a book** | `PATCH` | `/books/:id` | Status `200 OK`, partial entity update validation, state change assertion | ✅ PASS |
| 6 | **delete a book** | `DELETE` | `/books/:id` | Status `200/204`, entity deletion assertion, resource cleanup | ✅ PASS |
| 7 | **skillcheck** | `POST` | `/postman-echo/post?movieName=Inception` | Status `200 OK`, query param, auth header, JSON body & dynamic variable test | ✅ PASS |

---

## 🚀 Quick Start / How to Run

### Prerequisites
- Node.js (v16+) installed
- Newman CLI installed globally or executed via `npx`

### 1. Clone the Repository
```bash
git clone https://github.com/utkarshpatwa393-sys/postman-student-expert.git
cd postman-student-expert
```

### 2. Run the Automated Tests via Newman
```bash
npx newman run collection.json
```

### 3. Generate HTML Test Reports (Optional)
```bash
npx newman run collection.json -r htmlextra
```

---

## 📊 Live Execution Results

```text
┌─────────────────────────┬─────────────────────┬─────────────────────┐
│                         │            executed │              failed │
├─────────────────────────┼─────────────────────┼─────────────────────┤
│              iterations │                   1 │                   0 │
├─────────────────────────┼─────────────────────┼─────────────────────┤
│                requests │                   7 │                   0 │
├─────────────────────────┼─────────────────────┼─────────────────────┤
│            test-scripts │                   7 │                   0 │
├─────────────────────────┼─────────────────────┼─────────────────────┤
│              assertions │                   8 │                   0 │
├─────────────────────────┴─────────────────────┴─────────────────────┤
│ total run duration: 10.3s                                           │
│ average response time: 1446ms                                       │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 👤 Author

**Utkarsh Patwa**  
- B.Tech Computer Science & Engineering (AI & ML), Hi-Tech Institute of Engineering and Technology, Ghaziabad  
- **GitHub**: [@utkarshpatwa393-sys](https://github.com/utkarshpatwa393-sys)  
- **LinkedIn**: [Utkarsh Patwa](https://www.linkedin.com/in/utkarsh-patwa-7b6b84381/)
- **AWS Builder Center**: [@utkarshx96](https://builder.aws.com/@utkarshx96)

---
*Maintained under the MIT License.*
