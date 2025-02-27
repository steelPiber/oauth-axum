# oauth-axum
Development of Oauth (Google) membership registration using Rust (axum) web framework, Postgres database, and React (tsx)
# OAuth Application Development Project

## Project Overview
* **Purpose**: Development of an authentication system supporting multiple OAuth providers
* **Tech Stack**: Rust (Axum), PostgreSQL, React (TypeScript)
* **Containerization**: Docker for maintaining consistent development/deployment environments

## System Architecture

### Backend (Rust/Axum)
* **RESTful API**: Provides endpoints for user authentication and management
* **Authentication Methods**:
  * Local authentication with email/password
  * GitHub OAuth integration
  * Google OAuth integration
* **Token Management**: JWT-based authentication token issuance and validation
* **Security**: Password hashing, security information management via environment variables

### Frontend (React/TypeScript)
* **Main Pages**:
  * Login/Registration page
  * User dashboard
* **State Management**: Authentication state management using Context API
* **Routing**: Protected routes implementation via React Router
* **OAuth Integration**: Social login buttons (GitHub, Google)

### Database (PostgreSQL)
* **User Table**: Stores local and OAuth user information
* **Data Model**: UUID-based user identification, OAuth provider information storage
* **Migration**: Schema management through SQL migrations

## Key Features

### Authentication Features
1. **Local Authentication**: Email/password registration and login
2. **Social Login**:
   * Login/registration with GitHub account
   * Login/registration with Google account
3. **Session Management**: JWT token-based user sessions

### Security Features
1. **Password Security**: Application of secure hashing algorithms
2. **Environment Variables**: Sensitive information managed via .env files
3. **Token Validation**: Server-side JWT validation

## Development Environment Setup

### Environment Variable Management
* **Backend Environment Variables**: Database connection, JWT secret, OAuth keys, etc.
* **Frontend Environment Variables**: API URL, OAuth activation flags, etc.

### Docker Containerization
* **Three Containers**: Backend, Frontend, Database
* **Network Configuration**: Container network setup
* **Volume Management**: Database persistence maintenance

## Implementation Approach

### OAuth Authentication Flow
1. User clicks on a social login button
2. Redirection to the respective OAuth provider login page
3. Authorization code issuance after user authentication
4. Access token exchange with authorization code in the backend
5. User information retrieval using access token
6. Existing user verification or new user creation
7. JWT token issuance and redirection to client

### Code Structure
* **Modularized Backend**: Separation of modules by functionality (authentication, users, error handling, etc.)
* **Component-based Frontend**: Reusable UI components

## Project Setup and Execution

1. **Clone Repository and Create Directory Structure**
2. **Set Up .env Files**:
   * Register OAuth client ID/secret
   * Configure database connection information
   * Set JWT secret
3. **Run Docker**:
   ```bash
   docker-compose up -d
   ```
4. **Access Application**:
   * Frontend: http://localhost:8080
   * Backend API: http://localhost:3000

## Future Development

1. **Additional OAuth Provider Integration**: Add domestic services like Kakao, Naver, etc.
2. **Implement Refresh Tokens** to enhance security
3. **Add User Profile Management** functionality
4. **Implement Permission Management System**
5. **HTTPS Configuration** for enhanced security
