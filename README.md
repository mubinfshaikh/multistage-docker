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

This Dockerfile is structured into two stages, each finely tuned for a specific purpose to ensure efficient and optimized Docker image creation.

Stage 1: Building the Flask Application  

* Leveraging a Python base image, we initiate the construction of our Flask backend.
* We meticulously copy the backend source code and proceed to install all requisite dependencies.
* With precision, we orchestrate the building process of our Flask application, ensuring its robustness and functionality.

Stage 2: Crafting the Final Image  

* Employing a sleek and minimalist Python base image for our final product, we embark on the assembly of the ultimate Docker image.
* Carefully integrating the meticulously crafted backend from Stage 1 into our final image.
* We meticulously expose the necessary port and seamlessly commence the Flask application, ensuring a smooth and effortless deployment experience.



