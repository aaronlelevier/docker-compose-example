FROM python:2.7
FROM ubuntu:trusty

ENV PYTHONUNBUFFERED 1

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y build-essential git python libpq-dev python-dev python-setuptools
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y postgresql postgresql-contrib
RUN easy_install pip

ADD ../../. /code
WORKDIR /code
RUN pip install -r requirements.txt