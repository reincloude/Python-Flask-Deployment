About the Application:-
-----------------------
The application used is a simple python Machine Learning web app trained to predict the expence based on the age and salary inputs.
The application contains the pre-trained model (model.pql) and the supporting files.



Steps to run application locally:-
---------------------------------
1) Clone the application files into your local machine inside a directory.
2) Download python3, Anaconda Navigator and launch the ananconda prompt.
3) Go to the location where the application code is cloned and get inside the directory where application files are present.
4) Run the application using the command :-> python3 app.py
5) Open the web browzer and hit the url :->  http://localhost:8080                                                                    // In the application code port 8080 is hard coded for the application


Steps to deploy application on VM on AWS:-
------------------------------------------
1) Create an public AWS EC2 instance with UBUNTU image and the free tier machine type.
2) Allow port 8080 in the inbound rules of security group as the application is using it to expose.
3) Install python3, pip3 and git in the ec2. To verify the installation use the following commands:
   # python3 --version
   # git --version
4) Clone the application repository into the EC2 instance.
5) Go inside the location of the application files.
6) Install the dependencies in the requirements.txt using following command:
   # pip3 install -r requirements.txt --break-system-packages
7) Run the application usimg the command :-> # python3 app.py
8) Now, use the EC2 instance public ip (x.x.x.x:8080) or the public ipv4 dns (dns:8080) to browse the application using browser.


Setting Up a Virtualized Environment Using Docker:-
---------------------------------------------------
1) We can use the same above application EC2 vm to containerise the application.
2) Install docker inside the EC2 and verify the installation using following command:
   # docker --version
3) Create a dockefile including the base image as python:3.11-slim-buster.
  // This base image contains all the dependencies
  // Dockerfile should be created in the directory containing all the application files.
4) Build the image using the dockerfile using following command:
   # docker build -t reincloude/expence-app-python-flask .                                  
5) Verify the image using the command :-> # docker images
6) Now, create a container using the docker image we have builded.
   # docker run -d -p 8080:8080 reincloude/expence-app-python-flask
7) verify the container creation using the following command:
   # docker ps -a
8) Now, use the EC2 instance public ip (x.x.x.x:8080) or the public ipv4 dns (dns:8080) to browse the application using browser.
