# Docker Instructions

I have created the necessary Docker files for the University Course Registration System.

## Files Created

- **Dockerfile**: Defines the image, using `node:18-alpine` as base.
- **.dockerignore**: Excludes `node_modules`, `.git`, etc.

## Prerequisites

- Docker must be installed and running on your machine.

## How to Build and Run

1.  **Build the Image**
    Open a terminal in this directory and run:

    ```bash
    docker build -t university-course-registration .
    ```

2.  **Run the Container**

    ```bash
    docker run -p 5000:5000 university-course-registration
    ```

3.  **Access the Application**
    Go to [http://localhost:5000](http://localhost:5000)

## troubleshooting

If you see an error about `docker` not found, ensure you have Docker Desktop installed and the `docker` command is in your system PATH.
