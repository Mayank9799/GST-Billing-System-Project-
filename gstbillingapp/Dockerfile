FROM python:3.6-slim

#FROM ubuntu:latest

WORKDIR /home/mayankdevops/GST-Billing-System-Project-

#COPY requirements.txt ./

#RUN apt-get  install python -y

#RUN  apt-get update -y

#RUN  apt-get install -y python


RUN python3 -m  venv /opt/venv 

#RUN pip install pip --upgrade

RUN /opt/venv/bin/python3 -m pip install --upgrade pip

RUN /opt/venv/bin/pip install -r requirements.txt
RUN /opt/venv/bin/pip install uwsgi

CMD python manage.py runserver 0:8001 