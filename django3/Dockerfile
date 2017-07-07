###############################################################################
# Environment
###############################################################################

FROM sparkgeo/base:python3

##############################################################################
# Application
##############################################################################

# PIP install Django libs
####################################################
ADD ./requirements.txt ./requirements.txt
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt

# Gunicorn
####################################################
RUN groupadd webapps
RUN useradd webapp -G webapps
RUN mkdir -p /var/log/webapp/ && chown -R webapp /var/log/webapp/ && chmod -R u+rX /var/log/webapp/
RUN mkdir -p /var/run/webapp/ && chown -R webapp /var/run/webapp/ && chmod -R u+rX /var/run/webapp/
ADD ./config/gunicorn.conf /

# Nginx
####################################################
RUN rm /etc/nginx/sites-enabled/default && rm /etc/nginx/sites-available/default
ADD ./config/webapp.nginxconf /etc/nginx/sites-enabled/

# Supervisor
####################################################
RUN mkdir -p /var/log/supervisor
ADD ./config/supervisor_conf.d/nginx.conf /etc/supervisor/conf.d/
ADD ./config/supervisor_conf.d/webapp.conf /etc/supervisor/conf.d/

EXPOSE 8000
