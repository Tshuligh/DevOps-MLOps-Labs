
# Use official Python runtime as base image
FROM python:3.9-slim
 #The CI failed because Git inside the Docker build step crashed so we install git inside your Dockerfile to avoid further errors 
RUN apt-get update && apt-get install -y git


# Set the working directory inside the container
WORKDIR /app

# Copy requirements
COPY requirements.txt .

# Install dependencies
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Copy all application code to container
COPY . .

# Create models directory for storing trained models
RUN mkdir -p models

# Run Training
CMD ["python", "src/train.py"]
