FROM hipache:0.3.1
MAINTAINER Millisami <millisami@gmail.com>

# Update
RUN apt-get -y update
RUN apt-get -y install wget curl unzip

# RUN curl -sL https://deb.nodesource.com/setup | sudo bash -
# RUN apt-get install -y nodejs

RUN mkdir /app

RUN cd /tmp && \
    wget --no-verbose -O airfield.zip https://github.com/emblica/airfield/archive/master.zip && \
    unzip airfield.zip && cp -r airfield-master/* /app/

# Then install packages
RUN cd /app && /usr/bin/npm install

# This is provisional
ENV NODE_ENV production

# Add supervisor conf
ADD ./supervisord.conf /etc/supervisor/conf.d/airfield.conf

RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Expose airfield
EXPOSE 3000
CMD ["supervisord", "-n"]
