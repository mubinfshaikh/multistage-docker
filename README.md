# Multistage Dockerfile Example for Flask Application

This repository demonstrates the use of a multistage Dockerfile to build and package a Flask backend application. Multistage builds are used to optimize the final Docker image size and improve security.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Dockerfile Explanation](#dockerfile-explanation)

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
2. Check the Docker container is Running, if not check the logs from below command on point no. 3:
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

The multistage Dockerfile is divided into two stages, each designed for a specific purpose.

Stage 1: Building the Flask Application In this stage:

* we use a Python base image to build the Flask backend. 
* We copy the source code of the backend and install the required dependencies. 
* Then, we build the Flask application.

Stage 2: Creating the Final Image For the final image:

* we use a minimal Python base image. 
* We copy the built backend from Stage 1 into this image. 
* We expose the necessary port and start the Flask application.

This multistage Dockerfile allows for an optimized and efficient build process, ensuring that the final image is lightweight and contains only the necessary components for running the Flask application.



