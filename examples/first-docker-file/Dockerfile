# Use a base Python image
FROM python:3.12-slim

# Install system dependencies
RUN apt-get update && \
    apt-get install -y python3-venv

# Create and activate a virtual environment
RUN python3 -m venv /venv

# Upgrade pip and install requirements
RUN /venv/bin/pip install --upgrade pip
COPY requirements.txt .
RUN /venv/bin/pip install -r requirements.txt

# Set the environment variable to use the virtual environment
ENV PATH="/venv/bin:$PATH"

# Set working directory
WORKDIR /app/devops

