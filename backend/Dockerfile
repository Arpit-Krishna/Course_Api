# Use the official Python image from the Docker Hub
FROM python:3.11-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory
WORKDIR /app

# Copy the requirements file and install dependencies
COPY Courses-API/requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire backend code into the container
COPY Courses-API /app/

# Expose the port Gunicorn will run on
EXPOSE 8000

# Command to run the application
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "courses_api.wsgi:application"]
