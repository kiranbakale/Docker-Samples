# Dockerfile Configuration for Python Application

This Dockerfile sets up a Python application using Python 3.11 running on Alpine Linux. It copies the application code, installs dependencies from a `requirements.txt` file, exposes port 5000, and specifies the command to run the application.

## Instructions

### Base Image

- **Base Image**: python:3.11-alpine
  - Alpine Linux is a lightweight Linux distribution, making the resulting Docker image small in size.

### Working Directory

- **Working Directory**: `/app`
  - Sets the working directory inside the Docker container to `/app`, where the application code will be copied.

### Copy Application Code and Install Dependencies

- **Copy `requirements.txt`**: Copies the `requirements.txt` file from the host to the working directory in the container.
- **Install Dependencies**: Runs `pip3 install -r requirements.txt` to install Python dependencies listed in `requirements.txt`. This step ensures that the necessary Python packages are installed within the container.

### Copy Application Code

- **Copy Application Code**: Copies the entire application code (including `index.py` and any other files) from the host to the working directory in the container.

### Expose Port

- **Expose Port**: Exposes port 5000 to allow external access to the application running inside the container.

### Command to Run the Application

- **Command**: `CMD ["python", "index.py"]`
  - Specifies the command to run when the container starts. In this case, it runs the `index.py` Python script using the `python` interpreter.

## Usage

1. Ensure Docker is installed on your system.
2. Place the `Dockerfile` and `requirements.txt` files in the root directory of your Python application.
3. Build the Docker image by running the following command in the terminal:
   ```bash
   docker build -t my-python-app .
4. `docker container run -d -p 5000:5000 my-python-app` this command will deploy the container on the port 5000 and will be accessible at your `machinesip:5000`