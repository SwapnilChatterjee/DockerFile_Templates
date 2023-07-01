# Python offcial image based on debian bookworm distro
FROM python:latest
# copying the contents from .(current directory) to /cli(cli directory inside container)
COPY . /cli
#making the default working directory to be /cli
WORKDIR /cli
#ALL THE RUN COMMANDS ARE EXCEUTED DURING THE BUILD OF DOCKER IMAGE
RUN apt update
#ESSENTIAL DEPENDENCY FOR mysqlclient
RUN apt-get install pkg-config -y
#INSTALLING OVS IN THE CONTAINER
RUN apt install openvswitch-switch -y
#INSTALLING REQUIRED DEPENDENCIES FOR mysqlclient and OVS
RUN apt-get install python3-dev default-libmysqlclient-dev build-essential -y
#INSTALLING ALL THE REQUIRED PACKAGES FROM requirement.txt which is present in /cli and our default work directory is also /cli
RUN pip install -r requirement.txt
#This command runs when we run the docker container form the image, it basically runs the python application and echo e present to enter a newline
CMD python main.py && echo
