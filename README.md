# Vercel Clone

A clone of Vercel built with Node.js, JavaScript, and Docker. This project includes backend functionality with Express, Redis, AWS SDK, and various AWS services. The backend handles file uploads, status management, and integrates with AWS S3 for storage.

## Features

- **Express Server:** Serves as the backend for the application.
- **Redis Queues:** Manages upload statuses and operations.
- **AWS Integration:** Utilizes AWS SDK, ECS, ECR, IAM, and S3 for cloud services.
- **File Management:** Retrieves file paths and uploads files to AWS S3.
- **Status Endpoint:** Provides an endpoint for polling upload statuses.
- **Frontend:** A user interface for interacting with the backend.

## Technologies Used

- **Node.js** - JavaScript runtime for building the server.
- **Express** - Web framework for Node.js.
- **Redis** - In-memory data structure store used for managing queues.
- **AWS SDK** - Amazon Web Services SDK for integrating with AWS services.
- **AWS ECS** - Elastic Container Service for deploying Docker containers.
- **AWS ECR** - Elastic Container Registry for storing Docker images.
- **AWS IAM** - Identity and Access Management for managing AWS access.
- **AWS S3** - Simple Storage Service for file storage.
- **CORS** - Cross-Origin Resource Sharing for handling cross-origin requests.

## Dependencies

To install the dependencies, use the following command:

```bash
pip install express redis aws-sdk cors


### Setup Guide

This Project contains following services and folders:

- `api-server`: HTTP API Server for REST API's
- `build-server`: Docker Image code which clones, builds and pushes the build to S3
- `s3-reverse-proxy`: Reverse Proxy the subdomains and domains to s3 bucket static assets

### Local Setup

1. Run `npm install` in all the 3 services i.e. `api-server`, `build-server` and `s3-reverse-proxy`
2. Docker build the `build-server` and push the image to AWS ECR.
3. Setup the `api-server` by providing all the required config such as TASK ARN and CLUSTER arn.
4. Run `node index.js` in `api-server` and `s3-reverse-proxy`

At this point following services would be up and running:

| S.No | Service            | PORT    |
| ---- | ------------------ | ------- |
| 1    | `api-server`       | `:9000` |
| 2    | `socket.io-server` | `:9002` |
| 3    | `s3-reverse-proxy` | `:8000` |


