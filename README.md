# 🛡️ Auth Server

> A simple, asynchronous authentication server built with Rust, Warp, and JWT.

![Rust](https://img.shields.io/badge/rust-%23000000.svg?style=for-the-badge&logo=rust&logoColor=white)
![Warp](https://img.shields.io/badge/warp-%23000000.svg?style=for-the-badge&logo=rust&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

## 📖 Overview

**Auth Server** is a lightweight yet powerful authentication microservice designed to handle user authentication and role-based access control (RBAC). Built with performance and safety in mind using Rust's asynchronous ecosystem, it provides secure token generation and validation.

## ✨ Features

-   **🚀 High Performance**: Built on top of `warp` and `tokio` for blazing fast async request handling.
-   **🔐 Secure Authentication**: Implements JSON Web Tokens (JWT) for stateless and secure authentication.
-   **👤 Role-Based Access Control**: Granular permission management with `User` and `Admin` roles.
-   **🛡️ Type-Safe**: Leverages Rust's strong type system to prevent common runtime errors.

## 🛠️ Tech Stack

-   **Language**: [Rust](https://www.rust-lang.org/)
-   **Web Framework**: [Warp](https://github.com/seanmonstar/warp)
-   **Async Runtime**: [Tokio](https://tokio.rs/)
-   **Serialization**: [Serde](https://serde.rs/)
-   **Auth**: [jsonwebtoken](https://github.com/Keats/jsonwebtoken)

## 🚀 Getting Started

### Prerequisites

Ensure you have Rust and Cargo installed on your machine.

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Installation & Run

1.  **Clone the repository** (if applicable) or navigate to the project directory.
2.  **Run the server**:

```bash
cargo run
```

The server will start on `127.0.0.1:8000`.

## 📡 API Endpoints

### 1. Login
Authenticate a user and receive a JWT token.

-   **URL**: `/login`
-   **Method**: `POST`
-   **Body**:
    ```json
    {
      "email": "user@user1and.com",
      "pw": "1234"
    }
    ```
-   **Response**:
    ```json
    {
      "token": "eyJhbGciOiJIUzUxMiJ9..."
    }
    ```

### 2. User Profile
Access a protected route for standard users.

-   **URL**: `/user`
-   **Method**: `GET`
-   **Headers**: `Authorization: Bearer <token>`

### 3. Admin Dashboard
Access a protected route restricted to administrators.

-   **URL**: `/admin`
-   **Method**: `GET`
-   **Headers**: `Authorization: Bearer <token>`

