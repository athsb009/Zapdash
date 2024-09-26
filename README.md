# ZapDash: Workflow Automation Platform

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
ZapDash is a workflow automation platform that enables users to create custom workflows between applications. Users can define dynamic triggers and actions to automate tasks, increasing efficiency and productivity. ZapDash integrates with multiple third-party services, making task automation seamless and intuitive.

## Features
- **User Authentication**: OAuth 2.0 and JWT-based authentication for secure access.
- **Real-time Processing**: Kafka is used to handle task execution efficiently.
- **Dynamic Workflows**: Flexible trigger and action system to create custom workflows.
- **Scalability**: Built with scalable architecture using Docker and PostgreSQL.
- **Third-party Integration**: Supports connecting various apps and services.

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
- **frontend/**: This folder contains the frontend code, built using React.js and Next.js. It handles the user interface and client-side logic for creating and managing workflows.
- **hooks/**: This folder stores custom React hooks, which might be shared across different components in the frontend or between frontend and backend logic for utilities, API calls, or authentication.
- **primary-backend/**: The main backend server, built using Node.js, Express.js, and TypeScript. It manages API requests, user authentication, and workflow logic. It connects to the PostgreSQL database and coordinates workflow execution.
- **processor/**: This component is likely responsible for processing workflows or middleware logic. It could include operations like validating workflows, interacting with third-party APIs, or managing triggers and actions.
- **worker/**: This folder contains the background processing logic, possibly involving Kafka for message queueing and asynchronous task processing. It handles tasks like sending notifications, scheduling jobs, or processing workflows that run in the background.

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
   Create a `.env` file in both the `frontend` and `primary-backend` directories and add the necessary keys (e.g., `DB_URL`, `JWT_SECRET`, etc.).

5. **Run Docker containers for backend services (Kafka, PostgreSQL, etc.)**:
    ```bash
    docker-compose up
    ```

6. **Start the development servers**:
    - For frontend:
    ```bash
    cd frontend && npm run dev
    ```
    - For backend:
    ```bash
    cd primary-backend && npm run dev
    ```

## Usage
Once the development servers are running:
1. Access the app at `http://localhost:3000` (frontend).
2. Sign up or log in.
3. Create custom workflows by selecting triggers and actions from the dashboard.
4. Connect third-party apps to automate tasks effortlessly.

## API Endpoints
### Workflow Endpoints
- `GET /api/v1/workflows`: Fetch all workflows
- `POST /api/v1/workflows`: Create a new workflow
- `GET /api/v1/workflows/{id}`: Fetch workflow by ID
- `PUT /api/v1/workflows/{id}`: Update workflow by ID
- `DELETE /api/v1/workflows/{id}`: Delete workflow by ID

### Authentication Endpoints
- `POST /api/v1/auth/register`: Register a new user
- `POST /api/v1/auth/login`: Login an existing user

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

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

