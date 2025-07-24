FROM rabbitmq:3-management

ARG UID
# EXPOSE $UID
RUN usermod -u 1001 ubuntu && \
    groupmod -g 1001 ubuntu

RUN adduser -u ${UID} --disabled-password --gecos "" appuser
RUN mkdir /home/appuser/.ssh
RUN chown -R appuser:appuser /home/appuser/
RUN echo "StrictHostKeyChecking no" >> /home/appuser/.ssh/config
RUN echo "export COLUMNS=300" >> /home/appuser/.bashrc

RUN apt-get update \
    && apt-get install -y vim

USER appuser