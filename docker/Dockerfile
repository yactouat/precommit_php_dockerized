FROM php:8.1.8-fpm
# create system user ("project_name" with uid 1000)
RUN useradd -G www-data,root -u 1000 -d /home/project_name project_name
RUN mkdir /home/project_name && \
    chown -R project_name:project_name /home/project_name
# copy existing application directory contents
RUN mkdir /project_name
WORKDIR /project_name
COPY .. .
# shared PHP conf
RUN mv /project_name/docker/shared.ini /usr/local/etc/php/conf.d/shared.ini
# error reporting is suitable for DEV here
RUN mv /project_name/docker/error-reporting.ini /usr/local/etc/php/conf.d/error_reporting.ini
# copy existing application directory permissions
COPY --chown=project_name:project_name .. /project_name
# changing user (because cannot run Composer as root inside container)
USER project_name

EXPOSE 9000