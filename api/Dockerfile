# Use an official Python runtime as a parent image
FROM python:3.12-slim-bullseye

RUN apt-get update && apt-get install -y curl

# Set the working directory in the container to /app
WORKDIR /app

# Add the current directory contents into the container at /app
ADD main.py /app

# Create a user named tazminia
RUN adduser --disabled-password --gecos '' tazminia

# Switch to the new user
USER tazminia

# Install flask
RUN pip install --no-cache-dir flask --user

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Run main.py when the container launches
CMD ["python", "main.py"]