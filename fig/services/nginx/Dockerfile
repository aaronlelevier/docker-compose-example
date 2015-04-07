FROM ubuntu:trusty
ENV PYTHONUNBUFFERED 1
RUN apt-get update

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y build-essential git python libpq-dev python-dev python-setuptools nginx supervisor
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y postgresql postgresql-contrib

RUN easy_install pip
RUN pip install uwsgi

ADD ../../. /opt/django/

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN rm /etc/nginx/sites-enabled/default
RUN ln -s /opt/django/fig/services/nginx/django.conf /etc/nginx/sites-enabled/
RUN ln -s /opt/django/fig/services/nginx/supervisord.conf /etc/supervisor/conf.d/

RUN pip install -r requirements.txt