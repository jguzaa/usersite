# CrowdAnalysis
#Duc contribution
- Set up and develop Django framework for the web application
- Design the users, videos database and user interface
- Techonology research and consultants for intergrating the ML model and Django web application
- User authentication and registration
- Video upload functions 

#Jongjet contribution
- Integrate the previous implementation to Django web application
- rabittMQ server and celery asyncronus task management implementation
- Video processing status checking implementation
- CSV file databse generating and managing
- Graph plotting with plotly on Django project

#Set up to run the project. Please follow the instructions

- First you have to create a virtual environment in order to run the application. It is recommended to PyCharm as the text editor and run with Python 3.8
- After downloading the the Pycharm editor, you can choose to create a directory and clone the application to that folder or choose to download the zip file from the link provided
- Download and copy yolo-coco model to /usersite/main/ folder: https://drive.google.com/file/d/1NQ7mQOM0zY-c6hX7OBfHU-Uk3_RC2U1k/view?usp=sharing
- install openCV via command 'pip install opencv-contrib-python' in pycharm virtual env terminal
- install celery via command 'pip install Celery' in pycharm virtual env terminal
- install rabbitMQ via command 'brew install rabbitmq' in terminal
- set the global environment for rabbitMQ via 'nano ~/.zshenv' then add 'export PATH=$PATH:/usr/local/opt/rabbitmq/sbin' to the last line

- use the terminal in Pycharm and run 'python manage.py runserver' to run the application
- Open a second terminal in Pycharm and run 'rabbitmq-server' or 'sudo rabbitmq-server' to activate the message broker
- Open a third terminal in Pycharm and run 'celery -A usersite worker -l INFO' to trigger the task assigned for uploading videos
- After that it will create a localhost server on which you can run the application on your web browser
- You will be asked to register and sign in  in order to upload your videos as well as see the generated graphs responding to each video that you uploaded. 
- In order to register, click on the “Register” button on the navigation bar. You will be redirected to the registration page. If you have already registered, you could choose to sign in with your username and password.

#the demo footage file can be download here
https://drive.google.com/file/d/1twa70eMk0FGYZWR7jaWQCQu5FydU8ZOM/view?usp=sharing

Note: this project will find the average people in each 10 minute of the video file. If you want to do the testing, you can edit line 67 of file /main/crowd_counting.py to change the value of 'mod_no'. the mod_no is the number of video frame in 10 minute. 
