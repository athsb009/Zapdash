# ZapDash: Workflow Automation Platform

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [Testing](#testing)
- [Deployment](#deployment)
- [License](#license)

## Project Overview
ZapDash is a workflow automation platform that enables users to create custom workflows between applications. Users can define dynamic triggers and actions to automate tasks, increasing efficiency and productivity. ZapDash integrates with multiple third-party services, making task automation seamless and intuitive.

## Features
- **User Authentication**: OAuth 2.0 and JWT-based authentication for secure access.
- **Real-time Processing**: Kafka is used to handle task execution efficiently.
- **Dynamic Workflows**: Flexible trigger and action system to create custom workflows.
- **Scalability**: Built with scalable architecture using Docker and PostgreSQL.
- **Third-party Integration**: Supports connecting various apps and services.
- **Logging & Monitoring**: Track and debug workflows with execution logs.
- **Error Handling & Retries**: Automatically retries failed workflows.

## Tech Stack
- **Frontend**: React.js, Next.js, Tailwind CSS
- **Backend**: Node.js, Express.js, TypeScript
- **Database**: PostgreSQL, Prisma ORM
- **Task Processing**: Kafka
- **Containerization & Orchestration**: Docker
- **Validation**: Zod (for schema validation)
- **Authentication**: NextAuth

## Project Structure

### Directory Descriptions:
- **frontend/**: Contains the frontend code built using React.js and Next.js.
- **hooks/**: Handles triggers for sending Solana tokens and Gmail notifications.
- **primary-backend/**: The main backend server, managing API requests, authentication, and workflow logic.
- **processor/**: Processes workflows, validates actions, and interacts with third-party APIs.
- **worker/**: Manages background tasks using Kafka for asynchronous processing.

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/athsb009/zapdash.git
    ```
2. **Navigate to the project directory**:
    ```bash
    cd zapdash
    ```
3. **Install dependencies for both frontend and backend**:
    ```bash
    cd frontend && npm install
    cd ../primary-backend && npm install
    ```
4. **Set up environment variables**:
   Create a `.env` file in both the `frontend` and `primary-backend` directories (see [Environment Variables](#environment-variables)).
5. **Run Docker containers for backend services (Kafka, PostgreSQL, etc.)**:
    ```bash
    docker-compose up
    ```
6. **Start the development servers**:
    - Frontend:
    ```bash
    cd frontend && npm run dev
    ```
    - Backend:
    ```bash
    cd primary-backend && npm run dev
    ```

## Quick Start
Once the development servers are running:
1. Open `http://localhost:3000` in your browser.
2. Sign up or log in.
3. Create custom workflows by selecting triggers and actions from the dashboard.
4. Connect third-party apps to automate tasks effortlessly.


## Environment Variables
Create a `.env` file in both `frontend` and `primary-backend` with the following keys:
```
# Backend (primary-backend/.env)
DB_URL=postgres://user:password@localhost:5432/zapdash
JWT_SECRET=your-secret-key
KAFKA_BROKER=localhost:9092

# Frontend (frontend/.env)
NEXTAUTH_URL=http://localhost:3000
NEXT_PUBLIC_API_BASE_URL=http://localhost:4000
```

## Contributing
We welcome contributions! To contribute:
1. Fork the repository.
2. Create a new branch:
    ```bash
    git checkout -b feature-name
    ```
3. Make your changes and commit:
    ```bash
    git commit -m "Add new feature"
    ```
4. Push to your branch:
    ```bash
    git push origin feature-name
    ```
5. Submit a pull request, and we will review it.

## Testing
Run unit and integration tests:
```bash
cd primary-backend
npm test
```

## Deployment
To deploy ZapDash using Docker:
```bash
docker-compose -f docker-compose.prod.yml up --build -d
```

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---
🚀 *Happy automating with ZapDash!*
