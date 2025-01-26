Task 1- Minimalist Application Development / Docker / Kubernetes
 
1. I createad EC2 instance "SimpleTimeService" and using Vim editor I craeted vim service.py file.
   command- Vim service.py

2. Install docker using command-

3. Then created docker file using below steps-
   # Use an official Python runtime as a parent image
   FROM python:3.9-slim
 
  # Set the working directory in the container
   WORKDIR /app
 
  # Copy the current directory contents into the container at /app
   COPY . /app
 
  # Install Flask directly
   RUN pip install Flask
 
  # Make port 5000 available to the world outside this container
   EXPOSE 5000
 
 # Define environment variable for Flask to run in production mode
  ENV FLASK_APP=service.py
  ENV FLASK_RUN_HOST=0.0.0.0
 
 # Run the Flask application
  CMD ["flask", "run"]
