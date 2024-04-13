Download and install python on local machine
create virtual environment
Use following commands to setup virtual environment in windows
https://www.geeksforgeeks.org/creating-python-virtual-environment-windows-linux/
virtualenv <envname>
virtualenv dockerpyenv
.\dockerpyenv\Scripts\activate
install flask using following command

https://medium.com/analytics-vidhya/containerizing-python-flask-application-19faa9db031c

pip install flask
create app.py flask program
create requirements.txt using following command
pip freezee > requirements.txt
create Dockerfile
build docker image
docker build -t dockerpython:01 .
check the images present by using docker images command
use following command to instantiate a container
docker run -d -p 5000:5000 dockerpython:01
check the running containers

docker ps
or 
docker container list
or 
docker container ls
or
docker container ls -a (shows both stopped and running container)

docker stop <imageid>

docker rm <imageid>

docker stop $(docker ps -q)


docker rm $(docker ps -a -q)

https://spacelift.io/blog/docker-stop-container#how-to-start-a-docker-container

docker container ls -n 2

docker build -t raghuprasadkonandur/dockerpython:01 .

docker login

docker push raghuprasadkonandur/dockerpython:01

Deploy it on AWS using EC2 instance


https://docs.docker.com/engine/install/ubuntu/

sudo apt-get update



Running pulling docker image

sudo docker pull raghuprasadkonandur/dockerpython:01
sudo docker images
sudo docker run -p 80:5000 raghuprasadkonandur/dockerpython:01
sudo docker run -d -p 80:5000 raghuprasadkonandur/dockerpython:01

CI-CD with githubactions

https://medium.com/@lyle-okoth/how-to-deploy-a-production-grade-flask-application-to-an-aws-ec2-instance-using-github-actions-6241886b197
