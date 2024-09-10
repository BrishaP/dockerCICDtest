## Project Overview
(in progress)
This project is a **Next.js application** containerized using **Docker** to create a consistent development environment across different machines (Windows and Mac). The application serves as a **proof of concept** for a fully automated development and deployment process, ensuring code quality and smooth collaboration across teams.

## Key Features

- **Containerized Development**: The app runs inside a Docker container, eliminating environment discrepancies (e.g., "works on my machine" issues).
- **Automated Workflow**: Pre-commit hooks enforce coding standards, run tests, and check for vulnerabilities.
- **Production-Ready Setup**: Separate Dockerfile for production, optimized for deployment.

## Technologies Used

- **Next.js**: Framework for building server-side rendering and static web applications.
- **Docker**: Containerization to ensure consistency between development and production environments.
- **ESLint**: Linting tool to maintain code quality.
- **Prettier**: Code formatting for consistent style.
- **Jest & React Testing Library**: Unit testing to ensure components function as expected.
- **Husky**: Pre-commit hooks to automate tasks such as linting, formatting, and testing.
- **npm audit**: Checks for vulnerabilities in dependencies before committing code.

## How It Works

### 1. Development Environment with Docker

- **Run the app in a container**: The app is set up to run inside a Docker container with live reload enabled. This ensures that changes made locally are reflected immediately in the app.
- **Docker Commands**:
  - Build the image:
    ```bash
    docker build -t nextjs-app .
    ```
  - Run the container:
    ```bash
    docker run -p 3000:3000 -v $(pwd):/app nextjs-app
    ```

### 2. Automated Development Workflow

- **Pre-commit Hooks**:
  - On each commit, the following tasks are automatically run to enforce standards:
    - **Linting**: ESLint ensures code follows defined rules.
    - **Formatting**: Prettier enforces consistent code formatting.
    - **Unit Tests**: Jest runs unit tests to prevent breaking changes.
    - **Security Checks**: `npm audit` checks for vulnerabilities in dependencies.

  This guarantees that only high-quality, tested, and secure code gets committed.

### 3. Production Dockerfile

- The app is optimized for production with a separate Dockerfile [`Dockerfile.prod`] that minimizes the image size and only installs production dependencies.

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone <repo-url>
