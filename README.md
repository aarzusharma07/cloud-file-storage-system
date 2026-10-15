# Cloud File Storage and Sharing System

A learning and portfolio project focused on understanding secure file uploads, cloud object storage, authenticated access, and controlled file sharing.

> **Project origin:** This repository is an adaptation of [SecureShare by srikesav09](https://github.com/srikesav09/SecureShare). The upstream project provided the starting codebase. This README identifies the source clearly; any original changes made for this portfolio should be documented below as they are implemented and tested.

## Overview

The application provides a web interface for authenticated users to manage files and share them through controlled links. It uses a React client, an Express API, MongoDB for application data, and Amazon S3 for file storage.

## Current Codebase Features

- Account registration and login
- Protected file-management routes
- File upload, listing, download, preview, and deletion
- File-type and signature validation
- Expiring or revocable file-sharing links
- Audit activity for selected account and file actions
- Security middleware, request validation, rate limiting, and centralized error handling
- Responsive React interface

These describe capabilities present in the inherited codebase; they should not be interpreted as features independently implemented by this repository's owner.

## Technology Stack

| Layer | Technologies |
| --- | --- |
| Frontend | React, React Router, Vite |
| Backend | Node.js, Express |
| Database | MongoDB, Mongoose |
| Object storage | Amazon S3 |
| Validation and security | Zod, Helmet, CORS, rate limiting, Multer |
| Testing | Node.js test runner, Supertest, MongoDB Memory Server |
| Deployment tooling | GitHub Actions, Vercel, AWS EC2 |

## Repository Structure

```text
.
├── client/       # React/Vite frontend
├── server/       # Express API, routes, services, and models
├── docs/         # Architecture, API, security, and deployment notes
├── .github/      # Workflow configuration
├── README.md
├── LICENSE.md
└── SECURITY.md
```

## Prerequisites

- Node.js 22 or newer
- npm
- A MongoDB database or connection string
- An AWS S3 bucket and appropriately scoped credentials for S3-backed file operations

## Local Setup

Clone **this repository**:

```bash
git clone https://github.com/aarzusharma07/cloud-file-storage-system.git
cd cloud-file-storage-system
```

Install the backend dependencies:

```bash
cd server
npm ci
```

Install the frontend dependencies in a separate terminal or after returning to the repository root:

```bash
cd ../client
npm ci
```

Create `server/.env` from `server/.env.example` and fill in the required values for your own development environment. Do not commit real credentials or secret values.

Start the API from the `server` directory:

```bash
npm run dev
```

Start the frontend from the `client` directory in another terminal:

```bash
npm run dev
```

The API defaults to `http://localhost:5000` and Vite normally serves the frontend at `http://localhost:5173`. Check the terminal output and project configuration if your local ports differ.

If needed, configure `VITE_API_URL` in a local client environment file to point to your own API. Keep environment files containing secrets out of version control.

## Configuration and Security Notes

- Use your own MongoDB database and AWS S3 bucket.
- Apply least-privilege permissions to AWS credentials.
- Keep secrets in local environment files or a deployment platform's secret manager.
- Never commit access keys, JWT secrets, database passwords, private user files, or production environment files.
- File-security checks provide indicators, not a guarantee that a file is safe.
- Review the configuration and security documentation before deploying this project publicly.

## Testing and Quality Checks

Run commands from the relevant package directory.

Frontend:

```bash
npm run format:check
npm run lint
npm run build
```

Backend:

```bash
npm run format:check
npm test
```

Some integration tests may require test database configuration or S3-compatible test infrastructure. Review the test setup and error output before interpreting a test failure.

## Deployment

Deployment is **not claimed as complete by this README**. To deploy your own instance, follow the documentation in `docs/deployment/`, configure your own infrastructure and secrets, and verify the frontend, API, database, and S3 integration end to end. Remove any upstream environment references from deployment configuration before using it.

## Portfolio Work and Contributions

This repository is being used to study and adapt a cloud file-storage application. Add a dated entry here for each change you personally make and test—for example, a new feature, a security improvement, a deployment you configured, or tests you added. Do not list planned work as completed work.

## Attribution and License

- **Upstream project:** [SecureShare by srikesav09](https://github.com/srikesav09/SecureShare)
- Review the included `LICENSE.md` and preserve its required copyright and license notices.
- Changes made in this repository should be documented separately from the upstream implementation.
