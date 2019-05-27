FROM ubuntu:latest

RUN apt-get update && apt-get install -y apt-utils gnupg wget && apt-get install -y python3-pip

RUN apt-get install -y libssl1.0.0 libssl-dev

RUN echo "export LC_ALL=C.UTF-8" >> /root/.bashrc
RUN echo "export LANG=C.UTF-8" >> /root/.bashrc

RUN apt-get install -y vim  && apt-get install -y cron
RUN pip3 install elasticsearch-curator


# Copy hello-cron file to the cron.d directory
COPY cron /etc/cron.d/cron

# Give execution rights on the cron job
RUN chmod 0644 /etc/cron.d/cron

# Apply cron job
RUN crontab /etc/cron.d/cron

# Run the command on container startup
CMD cron -f
