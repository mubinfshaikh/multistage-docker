# Multistage Dockerfile Example for Flask Application

This repository demonstrates the use of a multistage Dockerfile to build and package a Flask backend application. Multistage builds are used to optimize the final Docker image size and improve security.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Dockerfile Explanation](#dockerfile-explanation)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Modern application deployments often involve containerizing both the backend and frontend components. This project focuses on using a multistage Dockerfile to efficiently build a Flask backend application, creating a lightweight and secure Docker image.

## Prerequisites

- Docker: You need to have Docker installed on your machine. Visit [Docker's official website](https://www.docker.com/get-started) to download and install Docker.
- Install Docker on ubuntu - [Install Docker on ubuntu](https://docs.docker.com/engine/install/ubuntu/)

## Getting Started

1. Clone this repository:
   ```sh
   git clone https://github.com/mubinfshaikh/multistage-docker.git
   cd multistage-docker
   ```

2. Build the Docker image:
   ```
   docker build -t demo-app .
   ```

## Usage

1. Run the Docker container with ditached mode:
   ```
   docker run --rm --name demo-app -d -p 5000:5000 -t demo-app 
   ```
2. Check the Docker container is Runing or not:
   ```
   docker ps
   ```
3. Check the Docker container logs:
   ```
   docker logs -f demo-app
   ```
4. 1 Access the Flask application in your web browser at `http://localhost:5000`.  
   2. If you are using AWS EC2 or any other cloud provider server, then expose 5000 port for testing purpose only and the access http://public-ip-address:5000  



## Dockerfile Explanation

The multistage Dockerfile consists of two build stages, each optimized for a specific purpose.

### Stage 1: Build the Flask Application

- Use a Python base image to build the Flask backend.
- Copy the backend source code and install dependencies.
- Build the Flask application.

### Stage 2: Final Image

- Use a minimal Python base image for the final image.
- Copy the built backend from Stage 1.
- Expose the necessary port and start the Flask application.



