# Use a smaller base image for Python 3.11
FROM python:3.11-slim-buster

# Set working directory inside the container
WORKDIR /app

# Copy all files from the current directory to the container's /app directory
COPY . /app

# Upgrade pip to the latest version
RUN pip install --upgrade pip

# Install dependencies from the requirements.txt file
RUN pip install --no-cache-dir -r requirements.txt --break-system-packages

# Expose port 8080 for the application
EXPOSE 8080

# Define the command to run your application
CMD ["python3", "./app.py"]
