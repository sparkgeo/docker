FROM ubuntu:17.10

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    python3-dev \
    python3-setuptools \
    python3-pip \
    python3 \
    supervisor \
    vim \
    nginx


RUN mkdir -p /app
RUN mkdir -p /app_logs && chmod 777 /app_logs

RUN groupadd webapps
RUN useradd webapp -G webapps
RUN mkdir -p /run/app/ && chmod -R 777 /run/app/
RUN mkdir -m 777 -p /app_config

# Nginx
RUN rm /etc/nginx/sites-enabled/default && rm /etc/nginx/sites-available/default
ADD ./deploy/webapp.nginxconf /etc/nginx/sites-enabled/

# Supervisor
RUN mkdir -p /var/log/supervisor
ADD ./deploy/supervisor/nginx.conf /etc/supervisor/conf.d/
ADD ./deploy/supervisor/webapp.conf /etc/supervisor/conf.d/

WORKDIR /app/

ADD ./requirements.txt .
ADD ./src .
RUN pip3 install -r requirements.txt
RUN pip3 uninstall -y ujson

EXPOSE 80 443 9000

CMD ["supervisord", "-n", "-c", "/etc/supervisor/supervisord.conf"]