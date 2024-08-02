# Use an official Ubuntu base image
FROM ubuntu:20.04

# Set working directory
WORKDIR /app

# Install system dependencies and Python
RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*

# Copy application files and dependencies
COPY requirements.txt /app/
COPY devops /app/devops

# Install Python dependencies
RUN pip3 install --no-cache-dir -r requirements.txt

# Set environment variables if needed
# ENV DJANGO_SETTINGS_MODULE=myproject.settings

# Set the working directory to devops if that's where manage.py is
WORKDIR /app/devops

# Default command to run the Django application
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





