#Base OS Image
FROM ubuntu:14.04

#Create code directory for usage
RUN mkdir /code
RUN mkdir /code/docker-reqs
RUN mkdir /code/app

#Add requirements file to Docker image
ADD requirements.txt /code/docker-reqs/

#Pull updates from repo 
RUN apt-get update

#install python 2.7x, pip, tree and nano
RUN apt-get install -y python-pip

#Use pip to install based on requirements file (requirements.txt)
RUN pip install -r /code/docker-reqs/requirements.txt

#Expose ports
EXPOSE 80 443 5000 8080

#Set volume path for local file system mounting.
VOLUME ["/code/app"]
WORKDIR ["/code/app"]

ENTRYPOINT ["python"]
CMD ["/code/app/app.py"]
