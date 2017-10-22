FROM ansta/apache:latest

# Build Arguments
ARG HOST_IP
ARG GITHUB_ACCESS_TOKEN

# Run init script
CMD ["/sbin/my_init"]


# Create api vhost
ADD app.conf /etc/apache2/sites-available/
RUN a2ensite app

# Setup XDEBUG IP
RUN sed -i s,xdebug.remote_host=10.0.2.2,xdebug.remote_host=$HOST_IP,g /etc/php/5.6/mods-available/xdebug-apache2.ini
RUN sed -i s,xdebug.remote_host=10.0.2.2,xdebug.remote_host=$HOST_IP,g /etc/php/7.1/mods-available/xdebug-apache2.ini
RUN sed -i s,xdebug.remote_host=10.0.2.2,xdebug.remote_host=$HOST_IP,g /etc/php/5.6/mods-available/xdebug-cli.ini
RUN sed -i s,xdebug.remote_host=10.0.2.2,xdebug.remote_host=$HOST_IP,g /etc/php/7.1/mods-available/xdebug-cli.ini

# Set working directory to /var/www
WORKDIR /var/www
