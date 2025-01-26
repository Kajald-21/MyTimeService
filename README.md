Task 1- Minimalist Application Development / Docker / Kubernetes
 
1. I createad EC2 instance "MyTimeService" and using Vim editor I craeted vim service.py file.
   Vim service.py

2. Install docker using command-
   yum docker install -y 

4. Then created Docker file using below steps-
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

5. Commands to build a docker image using Dockerfile-
   docker build -t my-time-service
   
7. To Check Dockerfile is created or not-
    docker ps

8. Push Image to Dockerhub-
   docker push kajaldhobale/devops/servcie.py:latest
   
9.  To push service.py code to GitHub-
    For clone the code from GitHub to VsCode-
    git clone https://github.com/Kajald-21/MyTimeService

    For checking the status-
    git status

    For adding file to current repository
    git add .

    For committing the code-
    git commit -m "Service comitted"

    For pushing the code to GitHub-
    git push
    
10. Download Image From DockerHub-
    Commands for build and run the Container-
     docker build -t my-time-service .
     docker run -t my-time-service

    For Test the Servcie-
    docker run -t -p 5000:5000 my-time-service
    
    If you're testing locally, you can access:
    http://127.0.0.1:5000 (if running locally on your machine).
    http://172.17.0.2:5000 (inside the Docker network).

12. URL's for accessing DockerHub and GitHub-
    DockerHub- https://hub.docker.com/repository/docker/kajaldhobale/devops/general
    GitHub- https://github.com/Kajald-21/MyTimeService  
    
