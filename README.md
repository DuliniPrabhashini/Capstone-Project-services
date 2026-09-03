# Capstone Project Services

This repository contains the three main business microservices of the Capstone Project.

The services are maintained as separate Git repositories and included here as **Git submodules**. This makes it easier to clone and deploy all three services together, especially on a cloud VM.

## Services

| Service            | Port | Database   |
| ------------------ | ---: | ---------- |
| Student Service    | 8000 | PostgreSQL |
| Program Service    | 8001 | MongoDB    |
| Enrollment Service | 8002 | MySQL      |

## Project Structure

```text
Capstone-Project-services/
│
├── student-service/
├── program-service/
├── enrollment-service/
│
├── .gitmodules
├── ecosystem.config.js
└── pom.xml
```

### Student Service

Handles student related operations such as creating, updating, viewing and deleting student records.

```text
Port: 8000
Database: PostgreSQL
API: /api/v1/students
```

### Program Service

Manages academic program information.

```text
Port: 8001
Database: MongoDB
API: /api/v1/programs
```

### Enrollment Service

Handles student enrollment information and communicates with the Student Service when required.

```text
Port: 8002
Database: MySQL
API: /api/v1/enrollments
```

## Clone

Because the project uses Git submodules, clone it using:

```bash
git clone --recurse-submodules https://github.com/DuliniPrabhashini/Capstone-Project-services.git
```

If the repository has already been cloned:

```bash
git submodule update --init --recursive
```

## Service Dependencies

The services use the platform components provided by the Platform repository:

```text
Config Server      : 9000
Service Registry   : 9001
API Gateway        : 7000
```

Recommended startup order:

```text
Config Server
      ↓
Service Registry
      ↓
API Gateway
      ↓
Business Services
```

## Cloud Deployment

The repository can be cloned directly to a cloud VM using the recursive clone command.

