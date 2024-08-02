# Use an official Python base image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Install system dependencies and clean up
RUN apt-get update && \
    apt-get install -y \
    build-essential \
    libpq-dev && \
    rm -rf /var/lib/apt/lists/*

# Create a virtual environment
RUN python3 -m venv /opt/venv

# Ensure virtual environment is used
ENV PATH="/opt/venv/bin:$PATH"

# Upgrade pip and install dependencies
COPY requirements.txt /app/
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Copy application files
COPY devops /app/devops

# Set the working directory to where manage.py is
WORKDIR /app/devops

# Define the command to run the application
ENTRYPOINT ["python"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]






